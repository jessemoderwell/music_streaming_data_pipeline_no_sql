# music_streaming_data_pipeline_no_sql

This project utilizes the NoSQL DBMS Apache Cassandra to house data for a music-streaming startup with analytical purposes in mind. The data is modeled in a denormalized, 'one table per query' approach in order to facilitate fast reads and sidestep Apache Cassandra's inability to do joins.

Following the flow of the Jupyter Notebook, the first part reads the contents of several csv's into a csvreader object, then writes all this data into one csv titled 'event_datafile_new.csv'. In part two, three tables song_library, songplays, and user_songs are created to address the needs of three potential analytical queries of the data. Several cql insert statements are then looped through, reading in data from the event_datafile_new.csv, in order to create a pipeline from our csv to the Cassandra tables. The final step in the process is the verification of our data model, using cql select statements to make sure the data has been correctly inserted.

To end the notebook, we drop all tables and disconnect from the Cassandra cluster
