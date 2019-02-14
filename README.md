# op-song-analyzer-java

### Описание процесса сборки приложения:

1. Для сборки приложения необходимо чтобы на вашем ПК был установлен [фреймворк Maven](http://maven.apache.org/download.cgi).
2. Со страницы [проекта](https://github.com/OSLL/op-song-analyzer-java) необходимо скачать zip-архив, содержащий исходные коды приложения и распаковать его.
3. В командной строке нужно перейти в каталог с исходниками и выполнить команду "mvn package".
4. В появившемся, после выполнения команды, каталоге "target" находится целевой файл "LyricsAnalyzer-1.0".

### Системный тестер программы "LyricsAnalyzer-1.0":

В проекте присутствует каталог "system_test", в котором находятся исходные коды программы-тестера для приложения. Собирается программа-тестер так-же как и программа "LyricsAnalyzer-1.0".

Для того, чтобы выполнить 15 системных тестов, заложенных в программу-тестер, необходимо чтобы программа "LyricsAnalyzer-1.0" находилась в одной директории с программой-тестером. Также в этой директории должна находится поддиректория "resources", в которой должны быть файлы "testsongdata.csv"и "logging.properties". Данные файлы находятся в каталоге "resources" проекта. После того, как вышеуказанные условия будут обеспечены, необходимо выполнить в командной строке команду `java -jar test-1.0.jar` и дождаться сообщения об успешном выполнении всех системных тестов.

### Примеры работы с программой "LyricsAnalyzer-1.0":

Для работы с программой "LyricsAnalyzer-1.0" необходим [файл базы данных](https://www.kaggle.com/mousehead/songlyrics). Данный файл нужно скачать и распаковать в каталог с именем "resources", который, в свою очередь, должен располагаться в одном каталоге с файлом программы. Кроме этого в данном каталоге должен располагаться файл "logging.properties", который находится в одноимённом каталоге проекта. Файл "logging.properties" необходим для работы логгера, который, в случае возникновения ошибки, создаст в каталоге "resources" файл log.txt и запишет в него информацию о ней.

1. `java -jar LyricsAnalyzer-1.0.jar --list_bands` - Выводит список всех исполнителей из файла БД.
2. `java -jar LyricsAnalyzer-1.0.jar --list_bands X` - Выводит список всех исполнителей из файла БД, имя которых содержит "X".
3. `java -jar LyricsAnalyzer-1.0.jar --list_songs` - Выводит список всех песен из файла БД.
4. `java -jar LyricsAnalyzer-1.0.jar --list_songs X` - Выводит список всех песен из файла БД, имя которых содержит "X".
5. `java -jar LyricsAnalyzer-1.0.jar --artist_uniq_words "Deep Purple"` - Выводит список уникальных слов исполнителя, отсортированный по убыванию популярности в текстах песен.
6. `java -jar LyricsAnalyzer-1.0.jar --song_uniq_words "Soldier Of Fortune"` - Выводит список уникальных слов песни "Soldier Of Fortune", отсортированный по убыванию популярности в тексте.
7.  `java -jar LyricsAnalyzer-1.0.jar --artist_word_rating` - Выводит список всех исполнителей в порядке убывания количества уникальных слов в их песнях.
8. `java -jar LyricsAnalyzer-1.0.jar --similar_artists` - Выводит список исполнителей, чей словарный запас пересекается со словарным запасом исполнителя, указанного в данном флаге. Рядом с названием исполнителя выводится количество общих слов.
9. `java -jar LyricsAnalyzer-1.0.jar --similar_songs` - Выводит список песен, чей словарный запас пересекается со словарным запасом песни, указанной в данном флаге. Рядом с названием песни выводится количество общих слов.
10. `java -jar LyricsAnalyzer-1.0.jar --truly_uniq_words` - Выводит список слов, которые встречаются только в одной песне.
