Program Astraada HMI do wizualizacji danych z czujników firmy ELA Innovatio (Blue PUCK RHT) odbiera wiadomości za pośrednictwem protokołu MQTT z gatewaya Cassia X2000. Program:

  - odbiera dane wysyłane protokołem MQTT
  - wyświetla dane pomiarowe czujników w zależności od nazwy
  - wyświetla stan połączenia MQTT
  - możliwość przesłania danych innymi protokołami, np. Modbus TCP/IP

Po pobraniu, należy w ustawieniach "MQTT Client" zmienić adres IP brokera oraz port, a także określić temat subskrypcji w sekcji „Text Format Table”.
![353809651-114be716-f898-4425-abe8-692d7816eca2](https://github.com/user-attachments/assets/b07fc669-38a3-4204-abfc-5dc5136c7702)

DOMYŚLNIE PROGRAM JEST DLA DWÓCH CZUJNIKÓW RHT Z MOŻLIWOŚCIĄ DODANIA WIĘKSZEJ ILOŚCI CZUJNIKÓW

ABY DODAĆ NASTĘPNY CZUJNIK NALEŻY:
∙ W ZAKŁADCE 'Tags -> Data Types -> Array Dimensions and Ranges -> High Bound -> Dim. 1' ZWIĘKSZYĆ TABLICE DLA ZMIENNYCH:
	∙ czujnik; wynik_n; wynik_t; wynik_h; porownanie

∙ DODAĆ DO 'Macros -> Native Scripts -> STALE' NASTĘPNĄ NAZWE CZUJNIKA: 0\czujnik[x] = "NAZWA CZUJNIKA

∙ DODAĆ DO 'Macros -> Native Scripts -> CONVERT' NASTĘPNĄ PĘTLE 'IF' I 'porownanie', ODPOWIEDNIO WSTAWIAJĄC NUMER NASTĘPNEGO CZUJNIKA W MIEJSCE '[x]'

∙ DODAĆ DO 'Screen 1 (#1)' MIEJSCA DO WYŚIETLANIA DANYCH Z NOWEGO CZUJNIKA
