LaTeX source of "Snake Wrangling for Kids"

Dieses Werk ist unter einem Creative Commons Namensnennung-Keine kommerzielle Nutzung-Weitergabe 
unter gleichen Bedingungen 3.0 Deutschland Lizenzvertrag lizenziert. Um die Lizenz anzusehen, gehen Sie bitte 
zu http://creativecommons.org/licenses/by-nc-sa/3.0/de/ oder schicken Sie einen Brief an 
Creative Commons, 171 Second Street, Suite 300, San Francisco, California 94105, USA.

To build, you'll need latex, and dvipdf



Anleitung zum PDF's generieren


Auf Linux oder Mac kann man alle gezippten Bilder folgendermaßen entpacken

for x in `ls -1 *.zip`; do unzip $x; done

Nach dem entpacken aller Bilder, den folgenden Befehl aufrufen

python setup.py build

Nach ein paar Minuten sind die PDF's für Linux, Windows und Mac im target Verzeichnis fertig.
