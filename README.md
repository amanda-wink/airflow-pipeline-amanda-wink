# Women's Ice Hockey Airflow Pipeline

### Uses Airflow to ingest, clean, and combine the statistics from the two profession women's ice hockey leagues (NWHL and CWHL) in their 2017 season.



The pipeline is composed of five Python operators. The first two operators create dataframes of the statistics for each league from two seperate excel files. Once the data is in a dataframe, it is cleaned using pandas. The cleaning process includes droping columns, adding columns, renaming columns, rearranging the order of columns, and filling nulls to create a consistent format between the two dataframes. Once both dataframes are cleaned, they are written to seperate csv files. The third operator creates a dataframe from each cleaned csv and concatinates them into one dataframe that is written to a new csv file. After the dataframes are combined, the fourth operator creates a dataframe from the combined csv and writes it to a MySQL table. The final operator queries the table and prints the top five players by points from both the NWHL and CWHL. It also prints the top 20 overal players.

### Technologies/Languages
* Python
* Airflow
* Pandas
