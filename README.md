<div id="top"></div>

[![LinkedIn][linkedin-shield]][linkedin-url]
![Generic badge](https://img.shields.io/badge/Project-Pass-green.svg)

<!-- PROJECT HEADER -->
<br />
<div align="center">
  <a href="#">
    <img src="images/udacity.svg" alt="Logo" width="200" height="200">
  </a>

  <h3 align="center">Data Modeling with Apache Cassandra using Python & CQL</h3>

  <p align="center">
    Database Schema & ETL pipeline for Song Play Analysis 
    <br />
    <br />
    -----------------------------------------------
    <br />
    <br />
    Data Engineer for AI Applications Nanodegree
    <br />
    Bosch AI Talent Accelerator Scholarship Program
  </p>
</div>

<br />

<!-- TABLE OF CONTENTS -->
<details open>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#file-structure">File Structure</a></li>
    <li><a href="#how-to-run">How To Run</a></li>
    <li><a href="#etl-pipeline">ETL Pipeline</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

<br/>

<!-- ABOUT THE PROJECT -->

## About The Project

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs their users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of CSV files on user activity on their app.

The startup wants their data to be loaded into an Apache Cassandra database designed to optimize queries for song play analysis. This project designs a data model by creating a database schema and an ETL pipeline for this analysis using Python and CQL. The project defines tables to run particular queries and creates an ETL pipeline that transforms data from CSV files present in the local directory into these tables in the Apache Cassandra database for a particular analytic focus.

<p align="right">(<a href="#top">back to top</a>)</p>

### Built With

-   [![Python][python-shield]][python-url]
-   [![Cassandra][cassandra-shield]][cassandra-url]
-   [![Jupyter][jupyter-shield]][jupyter-url]
-   [![VSCode][vscode-shield]][vscode-url]

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- FILE STRUCTURE -->

## File Structure

1.  Dataset (Available in `event_data` folder):

    The directory of CSV files partitioned by date. Here are examples of filepaths to two files in the dataset:

    ```
    event_data/2018-11-08-events.csv
    event_data/2018-11-09-events.csv
    ```

    <br />

2.  `event_datafile_new.csv` contains the pre-processed denormalized dataset which can be generated after running the Part I code section of `etl.ipynb` file.

    The image below is a screenshot of what the denormalized data should appear like in the **event_datafile_new.csv** after running the code:

    ![Event Data][event-dataset]

    <br />

3.  `etl.ipynb` reads and processes all the csv files available in `event_data` folder and generates an `event_datafile_new.csv` file. This notebook contains detailed instructions on the ETL process for each of the queries.

4.  `README.md` provides details on the project.

<p align="right">(<a href="#top">back to top</a>)</p>

## How To Run

### Prerequisite

-   Prepare the Python environment by typing the following command into the Terminal

    ```
    $ pip install -r requirements.txt
    ```

### Running scripts

-   Execute each cell in sequence in `etl.ipynb` file, inside a Jupyter Notebook environment.

<p align="right">(<a href="#top">back to top</a>)</p>

## ETL Pipeline

The ETL pipeline follows the following procedure:

-   Part I. ETL Pipeline for Pre-Processing the Files

    -   Get the absolute path to all the event data CSV files present in the given directory and sub-directories.

    -   Iterate over all the data files and extract each data row by using csv_reader from CSV files and appending it to a list.

    -   Create an event data csv file called `event_datafile_new.csv` which contains all the event data from the appended list. This new file will be used to insert data into the Apache Cassandra tables.

-   Part II. Apache Cassandra Data Model

    -   Establish a connection to a local Cassandra instance and get a session for it.

    -   Create a keyspace and set the current session to it.

    -   From the data, design three different tables and queries to ask the questions.

    -   Select the required data from the `event_datafile_new.csv` file for each of the queries and insert it into the tables in the database.

    -   Do a SELECT for each of the questions from the relevant tables to verify that the data is correct.

    -   Finally, close the connection to the database.

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- ACKNOWLEDGMENTS -->

## Acknowledgments

-   [Udacity](https://www.udacity.com/)
-   [Bosch AI Talent Accelerator](https://www.udacity.com/scholarships/bosch-ai-talent-accelerator)
-   [Img Shields](https://shields.io)
-   [Best README Template](https://github.com/othneildrew/Best-README-Template)

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[linkedin-shield]: https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white
[python-shield]: https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white
[cassandra-shield]: https://img.shields.io/badge/cassandra-%231287B1.svg?style=for-the-badge&logo=apache-cassandra&logoColor=white
[jupyter-shield]: https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter
[vscode-shield]: https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white
[linkedin-url]: https://www.linkedin.com/in/arfat-mateen
[python-url]: https://www.python.org/
[cassandra-url]: https://cassandra.apache.org/
[jupyter-url]: https://jupyter.org/
[vscode-url]: https://code.visualstudio.com/
[event-dataset]: images/image_event_datafile_new.jpg
