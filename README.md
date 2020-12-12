# Project : 뉴스 기사의 정치 성향 분류 모델

이 프로젝트는 뉴스 기사의 정치적 성향을 분류해 보기 위한 것으로, 특정 키워드(ex.'코로나 방역')에 대한 뉴스 기사들을 수집하여 분류기준에 맞추어 분류하고자 합니다.

* 선정 언론사
    * 정치적 성향 분류 기준 : KTV국민방송 
    * 그 외 분류 대상 언론사 :  '한국경제TV', 'CHANNELA', '한겨례', 연합뉴스', '세계일보', '문화일보', '국민일보', 'TV조선', 'SBSCNBC', 'SBS', 'news1', 'MBN뉴스', 'mbc'

* 진행 순서
  1. 데이터 수집 (크롤링)
  2. 데이터 전처리 (POS Tag 등)
  3. TF-IDF
  4. cosin similarity ('KTV국민방송'과의 유사도)
  5. 데이터 라벨링 ('KTV국민방송'과의 유사도를 기준으로 '친정부'/'반정부'/'중립')
  6. 모델링
  7. 테스트


## Project Requirement 
※ 위의 '진행 순서'의 순서에 따라서 확인하실 수 있습니다.
(실행 환경 :  jupyter notebook)

    1.  
        from selenium import webdriver
        import os
        from bs4 import BeautifulSoup
        import pandas as pd
        import time
        import csv
        import urllib.request as ur

     2.  
        from konlpy.tag import Komoran
        import pandas as pd
        import os
        import numpy as np

     3. 
        import pandas as pd
        import numpy as np
        import pickle
        from sklearn.feature_extraction.text import TfidfVectorizer

     4. 
        from sklearn.feature_extraction.text import TfidfVectorizer
        from sklearn.metrics.pairwise import cosine_similarity
   
## Project 실행 
※ master branch 기준, `폴더`/`코드파일` 입니다.
  1. `COVID_Crawling`/`COVID_KTV국민방송.ipynb` (KTV국민방송 이하 모든 언론사에 대하여 실행)
  2. `POS_Tag`/`POS_Tagging_코로나방역.ipynb` (KTV국민방송 이하 모든 언론사에 대하여 실행)
  3. `TF_IDF`/`TF-IDF.ipynb` (KTV국민방송 이하 모든 언론사에 대하여 실행)
  4. `Cosine_Similarity`/`cosine_similarity.ipynb` 
  5. 
  6.
  7.

## Author
    오서연 
    - E-mail : SYO99@gmail.com
    이상민
    - E-mail : dsp12357@gmail.com
    김주현  
    - E-mail : jjjuhyun4502@gmail.com

## License
 본 프로젝트에 사용된 코드들은 google 검색을 통해 인용한 코드들로서 온전한 라이센스가 본 저자들에게 있지 않음을 밝힙니다.




