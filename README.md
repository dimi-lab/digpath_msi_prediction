# digpath_msi_prediction

### Steps for getting patch embeddings
1. get_filenames.sh
    - Set TOP_LEVEL_DIR to the directory containing the slide-specific subdirectories
    - run with `./get_filenames.sh <label>` replacing "label" with 0 or 1 (usually MSS=0, MSI=1)

2. get_features_CTransPath.py
   - Fill in line 51 with your path to ctranspath.pth
   - Run with `python get_features_CTransPath.py <filenames.csv>" replacing filenames.csv with the output csv of get_filenames.sh
   - May want to write a shell script to run for all slides' csv files

3. make_h5.py
   - Set `directory` to the path to the directory containing the embedding CSVs
   - Set `out_directory` to the desired output directory for the h5 files
   - Set `output_csv` to the desired output file for the slide.csv file (an input to HistoBistro)