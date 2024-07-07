-相關-  
https://www.raspberrypi.com/software/  
https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html  
https://www.realvnc.com/en/connect/download/viewer/?lai_sr=0-4&lai_sl=l  
https://images.theengineeringprojects.com/image/webp/2021/03/raspberry-pi-4.png.webp?ssl=1  


sudo apt update  
sudo apt upgrade  
sudo raspi-config  
ifconfig  
sudo reboot  

git clone https://github.com/miyachun/raspberry  


 -Virtualenv-  
python -m venv myenv  
source myenv/bin/activate  

-DHT11 DHT22-  
Python Setup  
https://learn.adafruit.com/dht-humidity-sensing-on-raspberry-pi-with-gdocs-logging/python-setup  
Installing the CircuitPython-DHT Library  
https://learn.adafruit.com/circuitpython-on-raspberrypi-linux/installing-circuitpython-on-raspberry-pi  

-MQTT Pi4-  
sudo apt-get install mosquitto mosquitto-clients  
sudo systemctl enable mosquitto.service  
sudo nano /etc/mosquitto/mosquitto.conf  
listener 1883  
allow_anonymous true  
sudo reboot  
ifconfig  
pip install 'paho-mqtt<2.0.0'  
pip install rpi.gpio  


-開通win防火牆1883埠-
設定/隱私權與安全性/Windows安全性/開啟windows安全性/防火牆與網路保護/進階設定/點左方輸入規則/再點右方的新增規則/選擇[連接埠]/下一步/選擇[TCP]/選擇[特定本機連接埠]/輸入1883/下一步/允許連線/下一步接續完成。

-MQTT Window Server-
1->下載 mqtt window server
2->開啟工作管理員/服務/mosquitto(右鍵啟動)，狀態(執行中)
3->修改 config 檔案
位置 : C:\Program Files\mosquitto\mosquitto.conf
加入 :
allow_anonymous true
listener 1883 172.20.10.2 # ip address

在當地目錄下開啟cmd並輸入以下
mosquitto -c mosquitto.conf -v

pip install "paho-mqtt<2.0.0"
  
