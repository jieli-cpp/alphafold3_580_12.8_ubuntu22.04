### how to use alphafold3? ###
1. Run the command `cd ~/alphafold3` to change to the ~/alphafold3 directory
2. (first time)Then run the command `./fetch_databases.sh` to download the databases to the /root/autodl-tmp/databases directory (Note: The data occupies 627 GB; the autodl-tmp mount point must have at least 700 GB of free space available).
3. After downloading the database, run the command ./run_af3_conda_alphafold3.sh to process the JSON files in the af_input directory.
4. `af_input` is the input directory (which can contain multiple JSON files), `af_output` is the output directory (results), `models` are the model parameters, and `run_af3_conda_alphafold3.sh` is the entry point for running the alphafold3 program.