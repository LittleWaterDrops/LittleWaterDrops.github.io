---
title: ProjectData
description: 실내 측위를 위한 각종 데이터를 수집하여 추출하는 어플리케이션을 제작했습니다.
image: projectdata_launch_screen.png
date: 2020-08-10
---

React-Native를 이용해서 제작하였으며, 안드로이드 디바이스를 기준으로 영상 정보를 포함한 가속도, 지자기, 자이로, 비콘, 와이파이 등의 (블루투스도 가능) 데이터를 실시간으로 수집합니다.

csv 혹은 txt 파일로 정렬된 형식을 갖춘 데이터로 추출할 수 있습니다. 이는 odject 순서, 혹은 시간 순서로 정렬 가능하며, client의 order에 따라 여러 방면으로 수집 가능하게끔 구현하였습니다.

모든 데이터는 realm으로 구현한 database에 저장되어 재활용이 가능합니다.

영상 정보도 함께 저장이 되며, 영상도 Movie 폴더의 project_data 폴더에 저장이 됩니다.

[csvToCsv](https://github.com/LittleWaterDrops/csvToCsv.git)를 함께 사용한다면, Slam으로 구한 시간에 따른 좌표값을 csv에 대입할 수 있으며, 실내 측위 향상에 더욱 도움을 줍니다.

GitHub 저장소: <https://github.com/LittleWaterDrops/Project_Data.git>
