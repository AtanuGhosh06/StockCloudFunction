# StockCloudFunction
This are python scripts which will be executed through Google Cloud Function. The aim of this set of scripts are to download the File from NSE site,Load it to bucket and then Load it to Bigquery
Three function are used for the project. The order of execcution is as follows:
1)atgh-daily-stock-copy- This script will create the list of file to be downloaded for the day . The file name are created day wise along with a Flag .A sample output looks like following
https://www1.nseindia.com/archives/nsccl/volt/CMVOLT_24062020.CSV|D
https://www1.nseindia.com/archives/equities/mto/MTO_24062020.DAT|N
https://www1.nseindia.com/content/historical/EQUITIES/2020/JUN/cm24JUN2020bhav.csv.zip|N

N means data is not loaded to bigquery.D means data is loaded to the bigquery.

2)atgh-daily-stock-day-end -This file is used to download the files to the Google Cloud Storage Bucket.

3)atgh-daily-end-bucket-bq - This function writes data from the bucket to Bigquery.Also once done it sends the file to Archieve bucket .
