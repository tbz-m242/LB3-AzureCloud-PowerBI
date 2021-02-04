LB3 - IoTKit - Azure Cloud - PowerPI
====================================

Die nachfolgende Dokumentation basiert auf einer Projektarbeit für das Modul 242 an der Technischen Berufsschule Zürich, von Luca Kiefer, Haris Chandrakumar und Cedric Kupper.

![](images/12.PNG) 

IoTKit 
------ 

* MBED Studio installieren, DOWNLOAD LINK: https://os.mbed.com/studio/
* Das IoT Kit angeschlossen und das [Cloud Programm](https://github.com/iotkitv3/cloud) importiert. 

* Auf "File" klicken und "Import Programm" wählen                                                                                                                                    
![](images/1.png)                                                                                                                                    

* Die Git-Hub URL des "Cloud" Dienstes einfügen und einen Namen vergeben, dann importieren                                                                                                                                    
![](images/2.png)                                                                                                                                    

* Um das IoT Kit anzuhängen, unter "Target", rechts unten auf das blaue Icon klicken                                                                                                                                                
![](images/3.png)                                                                                                                                                

* Dann bei "USB-Device" das Kit auswählen das Build Target überprüfen, wenn alles stimmt, auf "Save All" klicken                                                                                                                                                
![](images/4.png)                                                                                                                                                

* Nun ist das IoT Kit unter "Targets" mitt dem vorhin vergebenen Namen gespeichert. Wählt es aus                                                                                                                                                
![](images/5.png)   


Azure Cloud
-----------

* IoT Hub erstellt:
![](images/Azure_Hub.PNG)

* In IoT Hub ein Device erstellt
![](images/Azure_IoTDevice.PNG)

* "Primary Connection String" kopiert und in [mbed_app.json](link) kopiert 
![](images/Azure_Key.PNG)

### Beispiel Programm abändern 

* Das .json file anpassen, doppelklick und warten bis es sich öffnet
                                                                                                                                                
![](images/6.png)                                                                                                                                                

* Nun die eigenschaften und den AZURE Link einfügen      
                                                                                                                                          
![](images/7.png)                                                                                                                                                
![](images/8.png)                                                                                                                                                

* Zum schluss auf das "Play" Icon klicken und warten bis das Programm fertig Installiert wurde           
                                                                                                                                     
![](images/9.png)                                                                                                                                                


### Beispiel Programm erweitert, z.B. mehr Sensordaten senden oder andere Daten.

* Das gerät Sendet die Temperatur Daten an AZURE
                                                                                                                                                
![](images/10.png)   

Um zu Testen ob die Daten ankommen bitte mit Azure CLI folgende Befehle ausführen:

```
az login
az extension add --name azure-iot
az iot hub monitor-events --hub-name <IoT Hub Name> --props all
```

![](images/11.PNG)  

### Auswertung der Daten in PowerBI

* Consumer Gruppe zu IoT hub hinzufügen
![](images/13.PNG) 

* Stream Analytics Job erstellen
![](images/14.PNG)  

* Input und Output zum Stream Analytics Job hinzufügen
-> verlinkung mit IoT Hub
![](images/15.PNG)  
![](images/16.PNG) 

* Query anpassen
![](images/17.PNG)  

* -> Start des Jobs

* In PowerBi Daten erfassen
* -> Report erstellen (Gelb markiert beachten)

![](images/18.PNG)  

### Ergebniss

![](images/19.PNG)  





