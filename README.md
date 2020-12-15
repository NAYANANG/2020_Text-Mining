# Project : 뉴스 기사의 정치 성향 분류 모델

이 프로젝트는 뉴스 기사의 정치적 성향을 분류해 보기 위한 것으로, 특정 키워드(ex.'코로나방역','의료정책','부동산정책')에 대한 뉴스 기사들을 수집하여 분류기준>에 맞추어 분류하고자 합니다.

* 선정 언론사
    * 정치적 성향 분류 기준 : KTV국민방송
    * 그 외 분류 대상 언론사 :  '한국경제TV', 'CHANNELA', '한겨례', 연합뉴스', '세계일보', '문화일보', '국민일보', 'TV조선', 'SBSCNBC', 'SBS', 'news1', 'MBN>뉴스', 'mbc'

* step index
  1. 데이터 수집 (크롤링)
  2. 데이터 전처리 (POS Tag 등)
  3. TF-IDF
  4. cosine similarity ('KTV국민방송'과 각 언론사들의 유사도)
  5. COVID 데이터 추가 수집 및 전처리 (및 2~4단계 함께 진행)
  6. 데이터 라벨링 ('KTV국민방송'과의 유사도를 기준으로 '친정부'/'반정부'/'중립')
  7. 모델링 사용 데이터 준비(라벨링 끝난 언론사별 데이터를 combine, shuffling, padding) 
  8. 모델적용 (성능평가 포함)

      ※ step1~4 진행 후 KTV와의 cosine similarity를 진행 한 결과, '코로나방역'키워드 기사에 대하여 언론사 cosine similarity(유사도 점수 분포 0.2이상 0.7으로>서 분류에 적합한 결과였다고 판단.)결과가 추후 기사의 정치 성향 분류에 있어서 가장 적합하게 나올 것이라 판단하여 step5에서 '코로나방역'에 대한 데이터를 각 언>론사 마다 60개 데이터에서 100개로 늘려 수집하기로 결정하였습니다. 데이터 재 수집 후에는 step2~4를 다시 진행하였습니다.



# Getting started
## Install dependencies
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
    5. (1과 동일)
     
    6.  Labeling
 
    7.  Data-Ready

    8. 

## Project 실행
※ master branch 기준, `폴더`/.../`코드파일명.ipynb` 입니다.
  1. `Crawling`/`Crawling_code`/`KTV.ipynb` (KTV국민방송 이하 모든 언론사에 대하여 실행)
  2. `POS_Tag`/`POS_Tagging_코로나방역.ipynb` (KTV국민방송 이하 모든 언론사에 대하여 실행)
  3. `TF_IDF`/`TF-IDF.ipynb` (KTV국민방송 이하 모든 언론사에 대하여 실행)
  4. `Cosine_Similarity`/`cosine_similarity.ipynb`
  5. `COVID_Crawling`/`COVID_KTV국민방송.ipynb` (KTV국민방송 이하 모든 언론사에 대하여 실행)
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
                                                                         