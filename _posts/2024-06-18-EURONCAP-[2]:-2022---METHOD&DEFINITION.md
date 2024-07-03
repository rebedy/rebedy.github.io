---
layout: post
date: 2024-06-18
title: "EURONCAP [2]: 2022 - METHOD&DEFINITION"
tags: [assessment, EURONCAP, EURONCAP22, ]
categories: [Guideline/Assessment, ]
math: false
---



## **Prerequisites**


---

- [EURONCAP-1-Roadmap-(2022~2030)](https://rebedy.github.io/posts/EURONCAP-1-Roadmap-(2022~2030)/)


## **EURO NCAP 2022 🇪🇺**


---


Version 10.4 February 2024


Euro NCAP Assessment Protocol - SA Safe Driving - v10.4


ASSESSMENT PROTOCOL – SAFETY ASSIST
SAFE DRIVING


Implementation 2023


---



### **1. METHOD OF ASSESSMENT 평가 방법**

- 인적 요인은 차량 사고의 흔한 원인으로 그 중에서도 **과속과 음주 또는 약물**이 큰 문제가 됨.
- human “errors”; 부주의, 피로, 주의 산만 및 경험 부족.
- 이미 SAS(Speed Assistance Systems) 및 Attention Assist(Attention Assist)와 같은 운전자 자문 시스템은 위험 상황에서 운전자에게 경고하고 궁극적으로 운전자가 행동을 개선할 수 있도록 지원함으로써 충돌 시 인적 요소를 목표로 한다.
- <u>Euro NCAP는 driver monitoring system이 손상되거나 주의 산만한 운전을 효과적으로 detect하고 적절한 경고를 제공하고 효과적인 조치를 취하길 기대한다.</u>
- 운전자 모니터링 시스템이 손상되고 주의가 산만한 운전을 효과적으로 감지하고 적절한 경고를 제공하며 ADAS 시스템의 민감도를 높이거나 안전한 회피 기동을 개시하는 등의 효과적인 조치를 취할 수 있는 인센티브를 기대한다.
- 운전자의 상태를 얼마나 신뢰성 있고 정확하게 감지하고 그 정보를 바탕으로 차량이 어떤 조치를 취하는지를 중심으로 평가가 전개될 것이다.
- 충돌 시 제공되는 보호 기능에 대한 평가와는 달리, Safety Assist 기능 평가에는 차량에 대한 파괴 테스트가 필요하지 않다.


### **2. DEFINITION**


terms used.



#### **DSM; Driver State Monitoring 운전자 상태 모니터링**


Driver State Monitoring system that is able to (in)directly determine the state of the driver



#### **Direct monitoring 직접 모니터링**


Where driver state determination is supported by sensor(s) directly observing the driver.


센서가 운전자를 직접 관찰함으로써 운전자 상태 판단을 지원하는 경우.



#### **Indirect monitoring 간접 모니터링**


Where driver state determination is achieved indirectly through means other than sensor(s) directly observing the driver (e.g steering input).


운전자 상태 판단이 센서 이외의 수단을 통해 간접적으로 운전자를 직접 관찰하는 경우.



#### **Impaired driving 손상된 운전**


A driver who is disconnected from the driving task or not in a physical state that is sufficient for safe driving, either due to distraction, fatigue or sickness.


주의 산만, 피로 또는 질병으로 인해 운전과 단절되거나 안전한 운전을 위해 충분한 신체적 상태에 있지 않은 운전자.



#### **Distraction 주의 산만**


Anything (e.g. secondary tasks) that reduces the driver’s focus on the primary task of driving/controlling the vehicle.

- **Long distraction** – A single long duration distraction which takes the driver’s gaze away from the forward road view.
- **Short distraction / Visual Attention Time Sharing (VATS)** – Repeated short duration gazes away from the forward road view, which cumulatively reduce the driver’s awareness of the driving situation, until their attention returns to the driving task for long enough for them to
fully assess the driving situation.
- **Phone use** – A subset of short distraction (Visual Attention Time Sharing, VATS) where the object the driver’s attention is shared with is their mobile phone.


#### **Fatigue 피로**


State of the driver where the driver is not awake enough to properly perform the driving task.


운전자가 운전 업무를 제대로 수행할 수 있을 정도로 충분히 깨어있지 않은 운전자의 상태.

- **Drowsy** – State of the driver where tiredness has an adverse effect of the driver’s ability to focus on the driving task.
- **Microsleep** – A microsleep is a temporary episode of sleep which may last up to several seconds.
- **Sleep** – In this assessment sleep is considered as when a driver has been in a state of unconsciousness due to fatigue for a period of greater than a few seconds.


#### **Unresponsive Driver 응답 없는 운전자**


Where a driver becomes unresponsive during driving, likely due to an onset of sudden sickness or extreme fatigue. 


운전자가 운전 중에 반응이 없는 경우(갑작스러운 질병이나 극심한 피로로 인한 경우).



#### **Impaired driving vehicle response 손상된 주행 차량 반응**


Warning and/or adapted vehicle mode after an impaired driving has been detected.

- **Impaired driving warning** **손상된 운전 경고**
	- Warning issued in case the system determines an impaired driver
- **High sensitivity mode 고감도 모드**
	- A more sensitive and earlier warning and/or intervention of Safety Assist systems to compensate for the driver state
- **Minimum Risk Manoeuvre (MRM) 최소 위험 기동**
	- Emergency manoeuvre where the vehicle will either come to a controlled stop or speed of <10km/h without input from the driver.


#### **Owl** **type movement**


A shifting of visual attention away from the road and forward-facing position that is primarily achieved by head rotation followed by the eyes.


머리 회전과 눈에 의해 주로 달성되는 정면을 향한 자세와 도로에서 멀리 떨어진 시각적 주의의 전환



#### **Lizard** **type movement**


A movement in which the driver focuses on a task by moving primarily their eyeline away from the road with their head/face remaining in the forward-facing position.


운전자가 머리/얼굴이 전방을 향하는 자세로 유지된 채 주로 시선을 도로에서 멀리 이동시켜 작업에 집중하는 움직임.



#### **Degraded system 퇴화된 시스템**


A direct driver monitoring system is considered degraded in this assessment when an entire subsystem becomes fully unavailable. E.g. A direct driver monitoring system which uses head pose tracking and eye tracking would be considered degraded if eye tracking became fully unavailable therefore preventing the system identifying any lizard type movements.


전체 하위 시스템을 완전히 사용할 수 없게 될 경우 직접 운전자 모니터링 시스템은 저하된 것으로 간주된다. 예를 들어, 머리 자세 및 눈 추적을 사용하는 직접 운전자 모니터링 시스템은 눈 추적을 완전히 사용할 수 없게 되면 저하된 것으로 간주되어 어떠한 Lizard type movement을 식별하는 시스템을 방지한다.



#### **Eyelid aperture 눈꺼풀 틈**


Distance between the point where the straight line drawn in the y-axis direction from the midpoint of line segment connecting the outer and inner corners of the driver’s eye overlaps the lower edge of the upper eyelid and upper edge of the lower eyelid. Measured when driver is awake and attentive.


운전자의 눈의 외 측 모서리와 내 측 모서리를 연결하는 선분의 중점으로부터 y 축 방향으로 그려진 직선이 상안검의 하측 모서리와 하측 눈꺼풀의 상측 모서리와 중첩되는 지점 사이의 거리. 운전자가 깨어 주의를 기울일 때 측정된다.


![0](/assets/img/2024-06-18-EURONCAP-[2]:-2022---METHOD&DEFINITION.md/0.png)



#### **In-vehicle infotainment (IVI) system 차량 내 인포테인먼트 시스템**


The area containing the infotainment system and/or vehicle controls, typically located centrally ahead of the front row seating in the conventional passenger car layout. 


인포테인먼트 시스템 및/또는 차량 제어 장치를 포함하는 영역으로서, 통상적으로 종래의 승용차 레이아웃에서 앞 열 시트의 중앙 전방에 위치한다.


* 인포테인먼트: 정보와 오락을 함께 제공하는 TV 프로그램



#### **Adaptive Cruise Control (ACC)**


Cruise control that adjusts vehicle speed adaptively to a forward vehicle by using information regarding distance to forward vehicle, motion of the subject vehicle, and driver commands.


전방 차량까지의 거리 정보, 주체 차량의 움직임 정보 및 운전자 명령을 이용하여 전방 차량에 적응적으로 차속을 조절하는 크루즈 컨트롤.



#### **Forward Collision Warning (FCW) 전방 충돌 경고**


an audio-visual warning that is provided automatically by the vehicle in response to the detection of a likely collision to alert the driver.


충돌 가능성이 있는 것을 감지하여 운전자에게 경고하기 위해 차량이 자동으로 제공하는 시청각 경고.



#### **Lane Departure Warning (LDW) 차선 이탈 경고**


A warning that is provided automatically by the vehicle response to the vehicle that is about to drift beyond a delineated edge line of the current travel lane.


현재 주행 차선의 표시된 에지 라인을 넘어 표류하려는 차량에 대한 차량의 반응에 의해 자동으로 제공되는 경고.



#### **Seat Belt Reminder (SBR) 안전 벨트 알림**


Seat Belt Reminder that indicates the status of the seatbelt whether it is in use or not in use.


안전 벨트가 사용 중인지 아닌지 안전 벨트의 상태를 나타내는 안전 벨트 알림.



## **References**


---

- [euro-ncap-assessment-protocol-sa-safe-driving-v104.pdf](https://www.euroncap.com/media/80158/euro-ncap-assessment-protocol-sa-safe-driving-v104.pdf)
