# NBA DevOps Challenge 

This application fetches weather app data from the OpenWeather API and saves it to AWS S3 Bucket. The application. The application is containerized using Docker.

## Prerequisites

- Docker installed on your machine
- AWS account with access keys
- OpenWeather API key

## Setup

1. Clone this repository:
    ```sh
    git clone https://github.com/Rene-Mayhrem/aws-weather-app.git
    cd weather-dashboard
    ```

2. Create a [.env](https://dotenvx.com/docs/env-file) file in the root directory with the following content:

    ```properties
      OPENWEATHER_API_KEY=your_openweather_api_key
      AWS_BUCKET_NAME=weather-dashboard-${RANDOM}
      # AWS CREDENTIALS
      AWS_ACCESS_KEY_ID=your_aws_secret_key_id
      AWS_SECRET_ACCESS_KEY=your_aws-secret_access_key
      AWS_DEFAULT_REGION=your_aws_default_region
    ```

3. Build the docker image:

    ```sh
    docker build -t weather-dashboard .
    ```
4. Run the docker container:

    ```sh
    docker run weather-dashboard --name aws-app
    ```

## Usage 

The application will fetch weather data fro the following cities:
  - Philadelphia
  - Seattle
  - New York

The weather data will be saved to the specified AWS S3 bucket.

## AWS Configuration

The application uses the AWS CLI to interact with the S3. Ensure your AWS credentials are correctly set in the **.env** file.

## Resources

- [Docker Installation Guide](https://docs.docker.com/get-docker/): Follow this guide to install Docker on your machine.
- [OpenWeather API Documentation](https://openweathermap.org/api): Learn more about the OpenWeather API.
- [AWS S3 Documentation](https://docs.aws.amazon.com/s3/index.html): Comprehensive guide to using AWS S3.
- [AWS CLI Configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html): Guide to configuring the AWS CLI.

## License 

This project is licensed under the MIT License.
