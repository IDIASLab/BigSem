
# 🛠️ Setup Directions for BigSem Tutorial

To get started with the BigSem tutorial, you'll need to set up a few essential tools and libraries. We have mainly two required setup 1) Python and Spark and 2) SANSA Stack. Follow the instructions below to ensure your environment is ready for hands-on exercises.

# 1) Python and Spark Setup

## Recommended Setup - Google Colab

For an easier and smoother setup, you can run all python examples on **Google Colab**. If you do so you can directly jump to SANSA Setup below. 
Here are the benefits:

- No need to install Spark locally. Simply install PySpark directly in the Colab environment using:
  ```bash
  !pip install pyspark
  ```
- All Python dependencies can also be installed using the pip commands in a Colab notebook.
  ```bash
   !pip install numpy pandas scikit-learn rdflib SPARQLWrapper sparql-dataframe pyspark
   ```
- Quick setup, ideal for users who want to skip local configurations.

To get started:
1. Open [Google Colab](https://colab.research.google.com/).
2. Create a new notebook and follow the instructions for installing required libraries using pip.
3. Run all examples smoothly without needing a local Spark installation.

## Local Setup
### Step 1: Install Python and Required Libraries

1. **Install Python**: Make sure you have Python installed on your system (version 3.7 or higher is recommended). You can download Python from the [official website](https://www.python.org/downloads/).

2. **Install Required Python Libraries**:
   Open a terminal and run the following command to install the necessary Python packages:
   ```bash
   pip install numpy pandas scikit-learn rdflib SPARQLWrapper sparql-dataframe pyspark
   ```
   
### Step 2: Install Apache Spark

1. **Download Apache Spark**:
   - Go to the [Apache Spark download page](https://spark.apache.org/downloads.html).
   - Select the latest stable release, choose a package type (e.g., "Pre-built for Apache Hadoop"), and click "Download".

2. **Extract and Set Up Spark**:
   - Extract the downloaded file to a suitable location on your system.
   - Set the `SPARK_HOME` environment variable to point to the extracted directory:
     ```bash
     export SPARK_HOME=/path/to/spark-directory
     export PATH=$PATH:$SPARK_HOME/bin
     ```
   - To ensure Spark is set up correctly, you can verify the installation by running:
     ```bash
     spark-shell
     ```

3. **Ensure PySpark is Available**:
   PySpark should already be installed from the earlier step. You can check if it's working by running:
   ```bash
   python -m pyspark
   ```

# 2) SANSA Stack Setup

## Recommended Setup - Databricks 

We recommend creating a Databricks account beforehand to make it easier to follow along during the tutorial. 

1. **Create a Databricks Account**:
   - Visit the [Databricks website](https://databricks.com/).
   - Sign up for a free account or log in if you already have one.
   - For a free tier, you can check the [Databricks Community Edition](https://databricks.com/try-databricks) which offers 15GB RAM and 2-core clusters.

2. **Download the Latest SANSA Stack JAR**:
   - Download the most recent SANSA release JAR from the [SANSA Stack GitHub releases](https://github.com/SANSA-Stack/SANSA-Stack/releases).
   - Direct download link (recommended): [sansa-stack-spark_2.12-0.8.0-RC1-jar-with-dependencies.jar](https://github.com/SANSA-Stack/SANSA-Stack/releases/download/v0.8.0-RC1/sansa-stack-spark_2.12-0.8.0-RC1-jar-with-dependencies.jar).

3. **Create a Databricks Cluster**:
   - Navigate to **Clusters** on your Databricks account.
   - Click **Create Cluster** and provide the configuration (e.g., Spark 3.x version, appropriate node sizes).
   - Go to **Advanced Options** and set the following Spark configurations:
     ```bash
     spark.databricks.delta.preview.enabled true
     spark.serializer org.apache.spark.serializer.KryoSerializer
     spark.kryo.registrator net.sansa_stack.rdf.spark.io.JenaKryoRegistrator,net.sansa_stack.query.spark.sparqlify.KryoRegistratorSparqlify
     ```

4. **Upload SANSA JAR to Your Cluster**:
   - Go to your cluster's **Libraries** tab, click **Install New**, and choose **Upload**.
   - Upload the SANSA JAR file you downloaded earlier.
   - Make sure the JAR is attached and loaded into the cluster for use in your notebooks.

5. **Create a Notebook on Databricks**:
   - Go to the **Workspace** section and click **Create** -> **Notebook**.
   - Choose Python or Scala as the language, and attach it to your configured cluster.
   - You can now start running Spark and SANSA code directly within the notebook.

4. **Upload Datasets to Databricks**:
   - Navigate to **Data** in the Databricks interface.
   - Click **Add Data** and upload your datasets (e.g., `linked_movie_db.csv` and `recipe_kg.csv`).

Please refer to the official SANSA Databricks setup guide for further details [here](https://project-lambda.org/sites/default/files/2019-06/BDA_2019_Lecture_6_Tutorial.pdf).

## Local Setup

If you'd like to set up SANSA Stack locally instead, please refer to the official SANSA Databricks setup guide [here](https://project-lambda.org/sites/default/files/2019-06/BDA_2019_Lecture_6_Tutorial.pdf).

---

By following these instructions, you'll have all the necessary tools installed and configured for a smooth experience during the tutorial. Happy coding!
