# OGG VORBIS

#### ВЕРСИЯ

5
  
#### АВТОР

Семен Вяцков
    
#### ОПИСАНИЕ   

Данное приложение пишет подробную информацию об ogg vorbis аудио файле 
(консольный запуск) или воспроизводит его, показывая амплитуды (графическая 
версия).

#### ТРЕБОВАНИЯ

- Python 3.7.4+
- Windows 10
- Установленная аудио библиотека ffmpeg или libav. Добавить в PATH
путь к exe-файлу билиотеки для Windows. На Linux:
```
# libav
apt-get install libav-tools libavcodec-extra

# ffmpeg
apt-get install ffmpeg libavcodec-extra
```
#### СОСТАВ

- **vorbis**
    
    Вся логика обработки ogg vorbis файлов содержится здесь
    
    - **\_\_init\_\_.py** 
        
    - **decoders.py** 
    
        Все декодирование аудиопотока происходит здесь 
        
    - **helper_funcs.py** 
    
        Содержит вспомогательные функции различных назначений. (Эти функции
        выделены непосредственно в документации формата Vorbis I.)
        
    - **ogg.py** 
        
        Декодирует vorbis-пакеты из ogg-контейнера
        
    - **vorbis_main.py** 
    
        Главный кодовый файл модуля vorbis. Непосредственно обрабатывает 
        vorbis-пакеты
        
- **resources**

    Папка для различных данных, которые могут быть извлечены из ogg-vorbis
    файлов. К примеру, здесь лежат изображения, которые могут быть закодированы
    в одном из заголовков файла
    
- **libs**
    
    Папка с библиотеками, использующимися приложением
    
    - **libav-11.3**
    
        Библиотека используется для отрисовки амплитуд аудио
    
- **ui**
    
    Реализация графического и консольного интерфейсов
    
    - **\_\_init\_\_.py**
    
    - **console_ui.py**
    
        Реализация консольного интерфейса
        
    - **graphics_ui.py**
    
        Реализация графического интерфейса

- **tests**

    - **test_audiofiles**
        
        Папка с тестовыми ogg-vorbis аудиофайлами

    - **\_\_init\_\_.py**
        
    - **test_decoders.py**
    
    - **test_helper_funcs.py** 
        
    - **test_ogg.py** 
        
    - **test_vorbis_main.py**
        
- **launcher_console.py** 

    Консольный клиент
    
- **launcher_graphics.py**

    Графический клиент

- **requirements.txt**

    Библиотеки python, необходимые для работы приложения
    
- **config.ini**

    Конфигурационный файл

#### КОНСОЛЬНАЯ ВЕРСИЯ
    
Справка по запуску: launcher_console.py --help

Пример запуска: 
    launcher_console.py -e -i .\tests\test_audiofiles\test_1.ogg 

Справка по командам: --help [аргумент запуска]

#### ГРАФИЧЕСКАЯ ВЕРСИЯ

Справка по запуску: launcher_graphics.py --help

Пример запуска: launcher_graphics.py .\tests\test_audiofiles\test_1.ogg

#### ПОДРОБНОСТИ РЕАЛИЗАЦИИ

Вся логика содержится в следующих кодовых файлах. Покрытие тестами 80% 
или более.
```
Name                     Stmts   Miss  Cover
--------------------------------------------
vorbis\__init__.py           1      0   100%
vorbis\decoders.py         419     40    90%
vorbis\helper_funcs.py      28      0   100%
vorbis\ogg.py              110     16    85%
vorbis\vorbis_main.py      153     23    85%
--------------------------------------------
TOTAL                      711     79    89%
```