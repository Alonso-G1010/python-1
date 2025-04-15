from dotenv import load_dotenv
import os
import logging
from typing import List,Dict,Optional 
import requests
from requests.exceptions import

#----configurar logging----
logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s- %(levelname)s-%(menssage)s')

load_dotenv()
api_key=os.getenv("API_KEY")
logging.info("api key cargada correctamente")

#----cargar variabls de entorno 
def load_env()->Optional[dict[str,str]]:
    load_dotenv()
    api_key=os.getenv("API_KEY")
    search_engine_id=os.getenv("SEARCH_ENGINE_ID")

    if not api_key or not search_engine_id:
        logging.error("api_key o search_ingenie_id no estan cargados")
        return None 
    return{
        'api_key':api_key,
        'search_ingenie_id':search_engine_id
    }

def perform_google_search(
        api_key:str,
        serach_ingenie_id:str
        query:str
        start:int=1
        lang:str="lang_es"
        )->Optional[List[Dict]]:
        base_url="https://www.googleapis.com/customsearch/vl"
        param={
             "key":api_key;
             "cx":search_ingine_id,
             "q":query,
             "start":start,
             "lr":lang
        }
try:
     

#---------------------------------------------------------------
def main():
    env_vars=load_env()
    logging.info(f"variables cargadas{env_vars}")

if __name__ == "__main__":
    main()

