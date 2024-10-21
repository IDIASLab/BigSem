
# 🛠️ Setup Directions for BigSem Tutorial

To get started with the BigSem tutorial, you'll need to set up a few essential tools and libraries. Follow the instructions below to ensure your environment is ready for hands-on exercises.

## Step 1: Install Python and Required Libraries

1. **Install Python**: Make sure you have Python installed on your system (version 3.7 or higher is recommended). You can download Python from the [official website](https://www.python.org/downloads/).

2. **Install Required Python Libraries**:
   Open a terminal and run the following command to install the necessary Python packages:
   ```bash
   pip install numpy pandas scikit-learn rdflib SPARQLWrapper sparql-dataframe pyspark
   ```

   This command installs:
   - **Numpy**: For numerical computations
   - **Pandas**: For data manipulation and analysis
   - **Scikit-Learn**: For machine learning and data processing
   - **RDFLib**: For working with RDF data
   - **SPARQLWrapper**: For querying RDF data via SPARQL
   - **sparql-dataframe**: For converting SPARQL results to pandas DataFrames
   - **PySpark**: For distributed computing with Apache Spark

## Step 2: Install Apache Spark

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

## Step 3: Set Up SANSA Stack on Databricks

1. **Create a Databricks Account**:
   - Visit the [Databricks website](https://databricks.com/).
   - Sign up for a free account or log in if you already have one.

2. **Create a Databricks Cluster**:
   - After logging in, navigate to the **Clusters** section.
   - Click on **Create Cluster** and configure your cluster settings (e.g., choose a Spark version compatible with SANSA Stack).

3. **Attach SANSA Stack Libraries**:
   - Open the cluster configuration and go to the **Libraries** tab.
   - Click **Install New** and choose **Maven**.
   - Add the following coordinates for SANSA Stack:
     ```
     net.sansa-stack:sansa-rdf-spark_2.11:0.7.2
     net.sansa-stack:sansa-query-spark_2.11:0.7.2
     net.sansa-stack:sansa-ml-spark_2.11:0.7.2
     ```
   - This will download and attach the SANSA libraries to your Databricks cluster, enabling scalable RDF data processing.

4. **Upload Datasets to Databricks**:
   - Navigate to **Data** in the Databricks interface.
   - Click **Add Data** and upload your datasets (e.g., `linked_movie_db.csv` and `recipe_kg.csv`).

5. **Create a Notebook on Databricks**:
   - Go to the **Workspace** section and click **Create** -> **Notebook**.
   - Choose Python as the language and attach it to your configured cluster.
   - You can now start running Spark and SANSA code directly within the notebook.

## Alternative Setup: Using Google Colab

For an easier and smoother setup, you can run all examples on **Google Colab**. Here are the benefits:
- No need to install Spark locally. Simply install PySpark directly in the Colab environment using:
  ```bash
  !pip install pyspark
  ```
- All Python dependencies can also be installed using the pip commands in a Colab notebook.
- Quick setup, ideal for users who want to skip local configurations.

To get started:
1. Open [Google Colab](https://colab.research.google.com/).
2. Create a new notebook and follow the instructions for installing required libraries using pip.
3. Run all examples smoothly without needing a local Spark installation.

## SANSA Stack Installation

We recommend creating a Databricks account beforehand to make it easier to follow along during the tutorial. If you'd like to set up SANSA Stack locally instead, please refer to the official SANSA Databricks setup guide [here](https://github.com/SANSA-Stack/SANSA-Databricks/blob/main/SANSA%20through%20Databricks.pdf).

## Final Check

---

By following these instructions, you'll have all the necessary tools installed and configured for a smooth experience during the tutorial. Happy coding!
