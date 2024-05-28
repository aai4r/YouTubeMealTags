# YouTubeMealTags Dataset
> 본 데이터셋은 음식점에서 식사가 이루어지는 테이블 위 이미지와 그와 관련된 태깅 정보를 포함하고 있습니다.
> 데이터셋에는 식사 테이블 위 이미지(직접 수집한 경우) 혹은 관련 유튜브의 주소가 있습니다.
> 태깅 정보는 물체의 위치, 음식의 남은 양, 식사 중 필요한 서비스의 종류가 있습니다.
> 저작권 및 개인 정보로 인해 유튜브 이미지의 경우 이미지 대신 동영상의 주소가 포함되어있고, 자체 수집 이미지의 경우에는 천장에서 촬영한 테이블 이미지가 있습니다.
> 본 데이터셋은 [Cloud Robot 과제](https://aai4r.github.io)의 일환으로 수집하였습니다.
 
## Table of Contents
- [Introduction](#introduction)
- [Dataset Description](#dataset-description)
- [Data Structure](#data-structure)
- [Annotations](#annotations)
- [Contact](#Contact)
- [Acknowledgements](#Acknowledgements)

## Introduction
YouTubeMealTags dataset은 음식점에서 식사를 하는 이미지와 이와 관련된 다양한 정보를 제공하여 관련된 인공지능 모델의 개발에 도움을 주고자 합니다.
포함된 정보는 다음과 같습니다:
- 객체의 종류와 위치 (e.g., dish, cup, food, drink)
- 음식의 종류와 남은 양 (e.g., 치킨, 콜라)
- 필요한 서비스 (e.g., 휴지 제공, 쓰레기 치우기, 접시 치우기)

## Dataset Description
데이터셋은 음식점에서 식사를 하는 이미지를 포함하고 있으며 크게 다음과 같이 구성되어있습니다.
- 유튜브 비디오의 링크
- 자체 수집한 천장에서 촬영한 식사 이미지와 비디오

## Data Structure
데이터셋은 다음과 같이 구성됩니다.

```bash
/location
  /images
  /annotations
```
* 'location': 촬영 소스
* 'images': 이미지 혹은 URL
* 'annotations': 태깅 정보

## Annotations
데이터셋 내의 각 이미지 혹은 비디오는 관련 태깅 정보를 xml 포맷으로 저장하고 있습니다. 
이러한 태깅 정보는 다음 정보들이 포함되어있습니다:
* 객체의 종류와 위치: food, dish와 같은 객체의 종류(영어)와 좌표값(xmin, ymin, xmax, ymax 픽셀값)
* 음식의 종류와 남은 양: 음식 메뉴명(한글)과 남은 양(0 ~ 100)
* 필요한 서비스 정보: 식사 중 필요했던 혹은 요청한 서비스와 그 시점을 기록

```xml
<object>
 <name>food</name>
 <bndbox>
  <xmin>1304</xmin>
  <ymin>215</ymin>
  <xmax>1435</xmax>
  <ymax>346</ymax>
 </bndbox>
 <attributes>
  <food>
   <category/>
   <name>케챱</name>
   <quantity>30</quantity>
  </food>
 </attributes>
</object>
<object>
 <name>dish</name>
 <pose>unspecified</pose>
 <truncated>0</truncated>
 <difficult>0</difficult>
 <bndbox>
  <xmin>2249</xmin>
  <ymin>205</ymin>
  <xmax>2547</xmax>
  <ymax>494</ymax>
 </bndbox>
</object>
```

## Contact
* [담당자](yochin@etri.re.kr)에게 메일을 보내 요청

## Acknowledgements
> This work was supported by the Institute of Information & communications Technology Planning & Evaluation(IITP) grant funded by the Korea government(MSIT) (No.2020-0-00842, Development of Cloud Robot Intelligence for Continual Adaptation to User Reactions in Real Service Environments)
