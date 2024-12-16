---
title: "[혼공네] 2-1. 이더넷"
tags: [study, alone-network]
author: 상 한규
---
- 이더넷은 현대 LAN 환경에서 가장 대중적으로 사용되는 기술로, 다양한 통신 매체의 규격들과 송수신되는 프레임의 형태 및 프레임을 주고 받는 방법 등이 정의된 네트워크 기술이다.
<br><br>
- 이더넷 관련 기술은 전기전자공학자협회에서 IEEE 802.3의 이름으로 표준화하였다.
<br><br>
- 이더넷 표준 규격에 따라 구현된 통신 매체는 한눈에 파악하기 쉽도록 일정한 형태로 표기한다. [전송 속도 BASE - 추가 특성][100BASE-SX 등] ⇒ 물리 계층과 관련
    - 전송 속도는 Mbps를 기본으로 표현하며, Gbps는 기가bps를 의미한다. 100Base → 100Mbps
    - BASE는 베이스밴드의 약자로, 변조 타입을 의미한다. 변조 타입은 비트 신호로 변환된 데이터를 통신 매체로 전송하는 방법을 의미한다. 일반적인 LAN 환경에서는 대부분 디지털 신호를 송수신하는 베이스밴드 방식을 사용한다.
    - 추가 특성에는 통신 매체의 특성을 명시하는데, 전송 가능한 최대 거리, 물리 계층 인코딩 방식, 레인 수 등이 명시된다.
<br><br>
- 통신 매체의 종류로는 CTSL가 있고, 각각 동축, 트위스티드 페어, 단파장 광섬유, 장파장 광섬유 케이블을 의미한다.
<br><br>
- 이더넷 프레임은 이더넷 네트워크에서 주고 받는 프레임이다. ⇒ 데이터 링크 계층과 관련
    - 이더넷 프레임은 상위 계층으로부터 받아들인 정보에 헤더와 트레일러를 추가하는 캡슐화 과정을 통해 만들어지며, 수신자는 역캡슐화 과정을 거친다.
    - 이더넷 프레임 헤더는 프리앰블, 수신지 MAC 주소, 타입/길이 등으로 구성되며, 페이로드는 데이터로, 트레일러는 FCS로 구성된다.
    - 프리앰블이란 이더넷 프레임의 시작을 알리는 8바이트 크기의 정보다. 첫 7바이트는 10101010, 마지막 바이트는 10101011을 가진다.
    - MAC 주소는 네트워크 인터페이스마다 부여되는 6바이트 길이의 주소로, 물리적 주소라고도 불린다. ‘일반적으로’ 고유하고 변경되지 않는 주소다.
    - 일반적으로 NIC 장치가 네트워크 인터페이스 역할을 담당하므로, NIC가 여러 개 있다면 MAC 주소가 여러 개 있을 수 있다.
    - 타입은 프레임이 어떤 정보를 캡슐화했는지 나타내는 이더타입이며 길이는 프레임의 크기(길이)를 나타낸다. 16진수 이하인 경우 길이, 이상인 경우 타입을 나타낸다.
    - 데이터는 상위 계층으로 전달해야할 내용이며, 반드시 46바이트 이상이어야한다. 나머지 데이터의 자리는 패딩이라는 정보가 채워진다.
    - FCS는 수신한 이더넷 프레임이 오류가 있는지 확인하기 위한 필드로, 데이터 링크 계층에서 오류 검출을 맡고 있다. CRC (순환 중복 검사)라고 불리는 오류 검출용 값이 들어간다.
    송수신자는 각각 CRC 값을 구한 뒤 FCS 필드에 대입 혹은 비교하여 프레임 오류를 판단한다.
<br><br>
- LAN 기술에는 이더넷 외에 토큰 링 방식이 존재한다. 토큰 링 네트워크에서는 호스트들이 링 형태로 연결되어 토큰을 주고 받는데, 해당 토큰을 가지고 있어야만 메시지 송신이 가능하다.

문제 1. 이더넷 표준 규격에 따라 구현된 통신 매체는 한눈에 파악하기 쉽도록 일정한 형태로 표기하는데, 해당 형태의 구조를 서술하고 각각의 의미를 작성하시오.

→ 이더넷 표준 규격은 [전송 속도][BASE]-[추가 특성]의 형태로 표기한다.

전송 속도는 데이터 전송 속도를 의미하며 기본적으로 Mbps 단위를 따른다. Gbps의 경우에는 100G처럼 G를 붙인다.

BASE는 베이스밴드의 약자로 변조 타입을 의미한다. 변조 타입은 비트 신호로 변환된 데이터를 통신 매체로 전송하는 방법을 의미하며 일반적인 LAN의 경우 대부분 디지털 신호를 송수신하는 베이스밴드 방식을 사용한다.

추가 특성은 통신 매체의 특성을 명시한다. 전송 가능한 최대 거리, 물리 계층 인코딩 방식, 레인 수 등이 명시된다.

문제 2. 이더넷 프레임의 트레일러는 FCS로 구성되어있다. FCS는 수신한 이더넷 프레임이 오류가 있는지 확인하기 위한 필드다. 이 때 오류 검출을 위해 사용하는 검사를 약어 및 한국어로 작성하시오

→CRC (순환 중복 검사)