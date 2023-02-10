# DESIGN LAB

XBOX 360 KINECT SENSOR 
version 1

# Week 1:

Po próbie pobrania najnowszych sterowników prez system Windows 10, okazało się, że są one kompatybilne tylko z Kinectem v.2 i nasze urządzenie nie działało.
Po zlokalizowaniu problemu, pobraliśmy starsze wersje sterowników, udało się uruchomić narzędzie deweleporskie do Kinecta.


![gitara](https://user-images.githubusercontent.com/56031092/196038105-5cd8dd3e-1c14-40d2-9b04-cf1c2a7d052f.png)


Żeby upewnić się czy wszystko jest odpowiednio skonfigurowane, uruchomiliśmy jedno z narzędzi deweloperskich tj. Background Removal Basics i uzyskaliśmy pożądany efekt.

# Week 2


W tym tygodniu szukaliśmy w internecie informacji jak wygląda podłączenia Kinecta 360 do OS Linxa oraz do Raspberry pi 3.
Po zapoznaniu się z materiałami źródłowymi, zdecydowaliśmy na wybór platformy Raspberry pi. To rozwiązanie umożliwi łatwe zaimplementowanie skaneru głębi.
Póki nie mamy fizycznego sprzętu, zapoznaliśmy się z oficjalną dokumentacją Raspberry pi'a dotyczącej wprowadzenia do korzystania z niego.     

https://www.raspberrypi.com/documentation/computers/getting-started.html


# Week 3 


Zdecydowaliśmy na połączenie sensora Kinect z Linuxem przy użyciu Oracle VM VirtualBox:


![image](https://user-images.githubusercontent.com/56031092/200191153-a53335f4-f0d5-4e17-8e47-6b111dc9b19a.png)

Na ten moment podążamy wg instrukcji znajdującym się pod adresem:
- https://www.instructables.com/Hooking-up-a-Kinect-to-your-Computer-Using-Ubuntu/

# Week 4

SYSTEM
Aby połączenie sensora przebiegło pomyślnie, upewniamy się że nasz system jest odpowiedni do kalibracji (Ubuntu 10.10 32/64 bit), a następnie aktualizujemy system - w szczególności zwracamy uwagę czy posiadamy wymagane sterowniki graficzne dla naszej karty graficznej.

![sys](https://user-images.githubusercontent.com/56031092/207823155-b6fd1351-47e5-431b-a868-de91d20637d3.png)

TERMINAL
Przed zbudowaniem naszej aplikacji, przygotujemy nasze środowisko Linuxa, instalując zestawy pakietów przy pomocy następujących komend:

$ sudo apt-get update - aktualizuje nasze środowisko repozytorium

$ sudo apt-get install build-essential - instaluje zestaw aplikacji niezbędny do zbudowania/skompilowania programów napisanych w języku C/C++

$ sudo apt-get install zlib1g-dev mesa-common-dev libgl1-mesa-dev libglu1-mesa-dev - instaluje potrzebne biblioteki(dla zainteresowanch - linki do nich poniżej)
$ sudo apt-get install libpng12-dev libjpeg62-dev libtiff4-dev libasound2-dev libdc1394-22-dev
$ sudo apt-get install libspeex-dev libogg-dev libtheora-dev libbluetooth-dev libopenal-dev
$ sudo apt-get install libglu-dev

VRUI
Następnie, wypkowujemy, instalujemy i uruchamiamy zestaw narzędzi Vrui, które będzie nam służyć jako swego rodzaju podłoże środowiska sensora Kinect

![image](https://user-images.githubusercontent.com/56031092/207828837-114238f1-5286-4acf-b549-bb958b348f69.png)
http://idav.ucdavis.edu/~okreylos/ResDev/Vrui/Download.html

W lokalizacji plików Vrui, instalujemy wszystkie zbudowane pakiety:

$ make
$ make install

Po aplikacji Vrui poruszamy się przy pomocy następujących kombinacji klawiszów:

LMB - obraca obiektem
z - panoramizowanie
z + LMB - oddalanie
z + LMB + shift - przybliżanie/oddalanie

KINECT
Nareszcie, z przygotowanym środowiskiem pod sensor, instalujemy aplikacje The Kinect 3D Video Capture Project w wersji 1.2 
https://web.cs.ucdavis.edu/~okreylos/ResDev/Kinect/Download.html
i wypakowujemy do źródłowego folderu jak w przypadku bibliotek/Vrui:
$ make
$ sudo ./bin/RawKinectViewer > CalibrationData.csv

pozostała jedynie kalibracja środowiska tj. w filmie instruktażowym w poniższym linku:
https://www.youtube.com/watch?v=7TGF30-5KuQ

# Music tiles

We managed to design a music tiles program which operates using the Kinect in Java programming  language. We started with installing Microsoft SDK which is a program that contains all necessary drivers needed for the Kinect to work properly with Windows. The main program we used was Processing software.

Working project presentation:
https://youtu.be/wprBt0xUN9M












