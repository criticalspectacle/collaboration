<<<<<<< HEAD
# B1. 라즈베리 파이 로컬 셋업
--------------
1. 패스워드 바꾸기 (1. system option-> 3. Password) - 1234
2. 와이파이 셋팅하기 (1. System option -> 1. Wireless LAN -> 연결되어 있는 wifi이름입력) 
  https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md

    * 접속가능한 와이파이 체크  
       `$ sudo iwlist wlan0 scan`

    * 국가 설정해주기 (5. Localisations on Options -> L4. WLAN Country → 한국으로 해줘야됨 ! 1-4 KR korea(South) )
   ![b1_01_country](img/b1_01_country.png)
    * SSID(ex.iptime) / SSID PW 설정하기
    ![b1_02_ssid](img/b1_02_ssid.png)
    * 셋팅 됐는지 확인해주기(연결된 와이파이체크)  
       `$ sudo nano /etc/wpa_supplicant/wpa_supplicant.conf`
    * 와이파이 연결 테스트하기  
       `$ ping 8.8.8.8`
    * 안되면 reboot 하기  
       `$ sudo reboot`
    * 내 ip 확인  
       `$ ifconfig`  
       ssh server(3. Interface Option -> P2. SSH -> enabled (독일에 있음(원격이 되는 최소한의 조건 완성))-> 서버 열어주기

--------------
# B2. 라즈베리 파이 원격 셋업
--------------
 Terminal 열어서 
1. ssh 라즈베리파이 아이디+라즈베리파이 local주소  
         ex) ssh pi@192.168.0.155
2. 엔터 → 라즈베리 파이 비밀번호 치기 (원격이 되는 최소한의 조건 완성, 내컴에서 ssh 서버로 들어간 거)  
   * 에러 발생 가능성
   ![b2_01_error](img/b2_01_error.png)

   * 해결  
  `$ ssh-keygen -R 서버이름 또는 IP주소`
3. 구성되어 있는 리눅스 업데이트 해주기  
   https://www.raspberrypi.org/documentation/raspbian/updating.md  
   `sudo apt update`
4. 업그레이드  
    `sudo apt full-upgrade`
=======
Raspberry Pi Install & Setup
============================

C1. 라즈베리파이에 최신 nodejs 설치하기
--------------------------------
* 참고 : <https://github.com/nodesource/distributions>

1. 앞선단계에서 한 OS 최신 업데이트 중요 
   * ```$ sudo apt update``` & ```$ sudo apt full-upgrade```
2. node js 깔아주기
   * ```$ curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo bash -```
   * ```sudo apt install -y nodejs```
3. node js, npm 버전 확인하기
   * ```node -v```
   * ```npm -v```

C2. Node http 서버 띄우기
-----------------------
1. 디렉토리 만들기
   * ```$ kdir httpserver```
   * ```$ cd httpserver```
2. ```$ npm init```(opt.실행파일 이름은 server.js로)
3. ```$ npm i express```
4. ```$ sudo nano server.js``` 
   * sudo nano 수정하려는 파일명
   * server.js 코드 작성
<pre>
<code>
const express = require('express')
const app = express()
const port = 3000
app.get('/', (req, res) => {
res.send('Hello World!')
})
app.listen(port, () => {
console.log(`Example app listening at http://localhost:${port}`)
})
</code>
</pre>
5. 실행  ```$ node server.js```
  
C3. VS 코드로 라즈베리 파이에 연결하기
------------------------------
* 참고: <https://code.visualstudio.com/docs/remote/ssh>
1. vs code 에서 remote development 익스텐션 깔아준다.
2. f1 -> Remote-SSH: Connect to Host 선택
* > <img width="300" alt="c_3_4" src="https://user-images.githubusercontent.com/34053864/115983393-c109d500-a5db-11eb-8cdb-8a27d9dcb449.png">
3. piUsername@ipAdress (예.pi@192.168.0.155)치고 엔터
4. rasberry pi의 password 입력-> 접속
* (참고 : vscode terminal = terminal)
* > <img width="400" alt="c_3_2" src="https://user-images.githubusercontent.com/34053864/115983392-bfd8a800-a5db-11eb-9b82-baae2620db51.png">
  
- vscode 수정권한요청 ```$ sudo chown -R username  *```
  + VSCode에서 ssh로 rasberryPi 연결하고 vscode에 파일 내용 변경저장시,
  + 권한 없다고 한다면, username으로 소유자를 변경해주기 


>>>>>>> origin/main
