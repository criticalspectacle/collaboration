A. 인스톨
========================

준비물 : 라즈베리파이4, 5v전원, microSD카드, SD카드 리더기
--------------------------


1. 빈 microSD카드 컴에 연결해서 Raspberry Pi Imager 열기<br>
   ![RasberryPiImagerIcon](https://github.com/criticalspectacle/collaboration/blob/JISU/RasberryInstallSetup/img/A_01.png?raw=true)

2. microSD카드 포멧 후 os 설치<br>
   ![RasberryInstallSetup](https://github.com/criticalspectacle/collaboration/blob/JISU/RasberryInstallSetup/img/A_02.png?raw=true)

3. (1) microSD카드 boot 파일에 ssh파일 / conf파일 추가<br>
    ![Addssh&confFiles](https://github.com/criticalspectacle/collaboration/blob/JISU/RasberryInstallSetup/img/A_03-1.png?raw=true)

    (2) conf 파일 이름은 wpa_supplicant.conf 로 저장하고 내용은 다음과 같이 설정<br>
    

```javascript
        country=KR // 🔥대한민국으로 설정하는 것 중요함🔥 
        ctrl_interface=DIR=/var/run/wpa_supplicant
        GROUP=netdev 
        update_config=1 
        network={ 
        ssid="와이파이이름" 
        psk="와이파이비밀번호" 
        scan_ssid=1 
        }
```
<br>

![ConfFileText](https://github.com/criticalspectacle/collaboration/blob/JISU/RasberryInstallSetup/img/A_03-2.png?raw=true)


4. microSD카드를 라즈베리파이에 옮기고 라즈베리파이에 전원을 넣은 뒤, 무선 공유기나 라우터에 접속하여 와이파이가 연결되었는지 확인한다.<br>


    (1) 무선 공유기, 라우터 접속은 내부 네트워크에서 [세자리.세자리.0.1] 또는 [세자리.세자리.219.1]로 접속할 수 있다.<br>

    ![WifiSetup](https://github.com/criticalspectacle/collaboration/blob/JISU/RasberryInstallSetup/img/A_04.png?raw=true)

    (2) 무선 공유기나 라우터에 여러 기기가 접속할 수 있기때문에 라즈베리파이 전원을 켜기전 미리 무선 연결되어 있는 기기 리스트를 확인해두는 편이 좋다.<br>

    (3) os 설치 후 최초 연결된 라즈베리 파이이름은 _raspberryPI_로 설정되어 있음<br>


5. VScode 에서 라즈베리파이에 할당된 주소로 ssh 원격 접속<br>
   ![VScodeSSH01](https://github.com/criticalspectacle/collaboration/blob/JISU/RasberryInstallSetup/img/A_05-1.png?raw=true)


   ![VScodeSSH02](https://github.com/criticalspectacle/collaboration/blob/JISU/RasberryInstallSetup/img/A_05-2.png?raw=true)