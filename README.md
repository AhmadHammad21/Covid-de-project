# COVID-19 ETL Data Engineering Project

This project was inspired by a YouTube tutorial series on data engineering. You can view the specific video that inspired this work here: [YouTube Video Link](https://www.youtube.com/watch?v=gFWu-SSzRzc&list=PLBJe2dFI4sgvavQzL2Hm5CsnoIWHY5fI3&index=2).

## Data Source

The dataset used in this project is from the AWS COVID-19 Data Lake. More details can be found at: [AWS COVID Data Lake](https://dj2taa9i652rf.cloudfront.net/).

---

## Architecture Diagram

Below is the architecture diagram illustrating the project's workflow:

![Architecture Diagram](image.png)

---

## Steps to Set Up and Execute

1. **Download and Upload Data to S3**  
   Create an S3 bucket named `covid-etl-de-project` and upload the dataset to it.  

   **Command to create the S3 bucket:**
   ```bash
   aws s3 mb s3://covid-etl-de-project
   ```

   **Command to upload data to S3 (example):**
   ```bash
   aws s3 cp {FILE_PATH} s3://{BUCKET_NAME}/{KEY_PATH} --recursive
   ```

   Example uploads for each dataset folder:
   ```bash
   aws s3 cp enigma-jhud s3://covid-etl-de-project/enigma-jhud --recursive
   aws s3 cp enigma-nytimes-data-in-usa s3://covid-etl-de-project/enigma-nytimes-data-in-usa --recursive
   aws s3 cp rearc-covid-19-testing-data s3://covid-etl-de-project/rearc-covid-19-testing-data --recursive
   aws s3 cp rearc-usa-hospital-beds s3://covid-etl-de-project/rearc-usa-hospital-beds --recursive
   aws s3 cp static-datasets s3://covid-etl-de-project/static-datasets --recursive
   ```

2. **Set Up AWS Glue Crawlers**  
   - Create a Glue database to store the metadata.  
   - For each subfolder in the S3 bucket, create a Glue crawler with the same name as the folder.  
   - After running the crawlers, verify the data using AWS Athena.  

   Example:  
   - Folder: `enigma-jhud`  
   - Crawler Name: `enigma-jhud-crawler`  
   - Database Name: `covid-etl-db`

---

## Status

This project is currently **unfinished**. Key components such as data transformation, analytics, and advanced reporting still need to be implemented.

---

Feel free to contribute to the project or use it as a foundation for your own work!
