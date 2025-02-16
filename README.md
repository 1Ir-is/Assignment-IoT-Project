# Car Parking System.
This is source code for IoT Project in Visual Studio Code.\
If you want to use this code just copy the source code in `src` to the IDE you want.
## Available Scripts.
In this project, if you use Arduino IDE for this you must install those libraries that are not available in the IDE you need for the project.\
Some additional libraries you must install for this project are:
- [RFID - RC522](https://codeload.github.com/miguelbalboa/rfid/zip/refs/heads/master).
* [LiquidCrystal_I2C](https://doc-80-7g-drive-data-export.googleusercontent.com/download/pq7bjic1mp1trfhsr7iv03j5fak19v58/me18qcme6uphfcdl6qk2oc2769c5ih30/1671259500000/e9d3db57-6c0d-49eb-85be-084c7fefb490/109330935972450210669/ADt3v-Mu2uTemKuwP29ONgV0VfsnPfhx9VsdY1yyYf_oY3TJySYnzXL3BZhpwG-AJDI5WhMvAIpo1rIZpO_7tAnt3pF73Kh7EQObojn-L5MQTQk7OxOYcQF1ScBV1i7rBms7fHYD3u5vR6IVRVrcCyQvhQBbClV3JQJR31oLVzzcTa-YOZqMSsx0PCUYmrxKYIYEFZwS4wGktBwDRVxT0Gno8jwuEAloFWg2KEBeTq1bP6rXWBBJboBfHBIJ4uR_EeRqiyZRlH_o1tF3WZiSU_134QbG3PEJKo-us6AdYcf2aWBJm62QwEU3dzi66edwOscP_15p8hFX?authuser=0&nonce=hnqrtq6q2eg7g&user=109330935972450210669&hash=4vcmlq0qq3pmfbq1jd9avn3f70qemudo).
- [Blynk-IoT](https://objects.githubusercontent.com/github-production-release-asset-2e65be/32791821/f3513eaa-1373-411b-a42d-9456a9a83087?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20221221%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20221221T143722Z&X-Amz-Expires=300&X-Amz-Signature=ea5a9ff090aa395f8adc28d34c0c3f8003d507b30a7f833d965185248153f543&X-Amz-SignedHeaders=host&actor_id=93533202&key_id=0&repo_id=32791821&response-content-disposition=attachment%3B%20filename%3DBlynk_Release_v1.1.0.zip&response-content-type=application%2Foctet-stream).
* [SimpleTimer](https://www.electroniclinic.com/wp-content/uploads/2019/08/SimpleTimer.zip).
- [Firebase Database](https://codeload.github.com/mobizt/Firebase-ESP-Client/zip/refs/heads/main).

This project has LCD I2C and you will probably have different LCD type than the one I used in the project.\
So you need to check the address of your LCD I2C through this [LCD I2C Scanner Source Code](https://download-files.wixmp.com/archives/c901e7_7d5bfbbe9d1d43858662ab7bbb46b56e.zip?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ1cm46YXBwOmU2NjYzMGU3MTRmMDQ5MGFhZWExZjE0OWIzYjY5ZTMyIiwic3ViIjoidXJuOmFwcDplNjY2MzBlNzE0ZjA0OTBhYWVhMWYxNDliM2I2OWUzMiIsImF1ZCI6WyJ1cm46c2VydmljZTpmaWxlLmRvd25sb2FkIl0sImlhdCI6MTY3MTE4MTczMiwiZXhwIjoxNjcxMjE3NzQyLCJqdGkiOiI1OGU3NmQ3YzY0MWUiLCJvYmoiOltbeyJwYXRoIjoiL2FyY2hpdmVzL2M5MDFlN183ZDViZmJiZTlkMWQ0Mzg1ODY2MmFiN2JiYjQ2YjU2ZS56aXAifV1dLCJhdHRhY2htZW50Ijp7ImZpbGVuYW1lIjoiTENEMTZ4Ml9JMkNfU2Nhbm5lci56aXAifX0.6Oli_jcW0DOiM9VcffCIpS1BTMH0TZzZx79b0y6MooY).

Upload this source code to your Arduino board and turn on the Serial Monitor (Ctrl + Shift + M) to see the address of your LCD I2C.\
When you know your address of your LCD I2C, you just change this line in the source code.
```C
LiquidCrystal_I2C lcd(0x27,16,2); 
```
If your LCD I2C address is also `0x27`, keep it the same, but if your address is different from mine such as "0x3F", ... \
You just need to change `0x27` to the address you have scanned from [LCD I2C Scanner Source Code](https://download-files.wixmp.com/archives/c901e7_7d5bfbbe9d1d43858662ab7bbb46b56e.zip?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ1cm46YXBwOmU2NjYzMGU3MTRmMDQ5MGFhZWExZjE0OWIzYjY5ZTMyIiwic3ViIjoidXJuOmFwcDplNjY2MzBlNzE0ZjA0OTBhYWVhMWYxNDliM2I2OWUzMiIsImF1ZCI6WyJ1cm46c2VydmljZTpmaWxlLmRvd25sb2FkIl0sImlhdCI6MTY3MTE4MTczMiwiZXhwIjoxNjcxMjE3NzQyLCJqdGkiOiI1OGU3NmQ3YzY0MWUiLCJvYmoiOltbeyJwYXRoIjoiL2FyY2hpdmVzL2M5MDFlN183ZDViZmJiZTlkMWQ0Mzg1ODY2MmFiN2JiYjQ2YjU2ZS56aXAifV1dLCJhdHRhY2htZW50Ijp7ImZpbGVuYW1lIjoiTENEMTZ4Ml9JMkNfU2Nhbm5lci56aXAifX0.6Oli_jcW0DOiM9VcffCIpS1BTMH0TZzZx79b0y6MooY).

## Diagram for the project.
- Gate.\
![alt text](https://github.com/1Ir-is/Internet-Of-Thing-Assignment-Project/blob/main/diagrams/gate%20for%20car%20parking%20diagram/Schematic%20For%20Gate.png?raw=true)

![alt text](https://github.com/1Ir-is/Internet-Of-Thing-Assignment-Project/blob/main/diagrams/gate%20for%20car%20parking%20diagram/Circuit%20diagram%20For%20Gate.png?raw=true)

* Car Parking.
![alt text](https://github.com/1Ir-is/Internet-Of-Thing-Assignment-Project/blob/main/diagrams/based%20car%20parking%20diagram/Based%20Car%20Parking%20Schematic%20Diagram.png?raw=true)

![alt text](https://github.com/1Ir-is/Internet-Of-Thing-Assignment-Project/blob/main/diagrams/based%20car%20parking%20diagram/Based%20Car%20Parking%20Circut%20Diagram.png?raw=true)

## Have any problem just contact to me.
Facebook: [Huỳnh Minh Huy](https://www.facebook.com/minhhuy.huynh.5076). \
Student Email: huyhmgcd210173@fpt.edu.vn. \
Personal Email: mhuynk1005@gmail.com.
