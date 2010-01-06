LaTeX source of "Snake Wrangling for Kids"

Dieses Werk ist unter einem Creative Commons Namensnennung-Keine kommerzielle Nutzung-Weitergabe 
unter gleichen Bedingungen 3.0 Deutschland Lizenzvertrag lizenziert. Um die Lizenz anzusehen, gehen Sie bitte 
zu http://creativecommons.org/licenses/by-nc-sa/3.0/de/ oder schicken Sie einen Brief an 
Creative Commons, 171 Second Street, Suite 300, San Francisco, California 94105, USA.

To build, you'll need latex, and dvipdf


Auf einem frischen Ubuntu sollten diese Pakete installiert sein, damit das Generieren der pdf's gleich klappt.
Am besten gleich in der Konsole
sudo apt-get mercurial python3 python3-tk texmaker texlive-full ttf-linux-libertine
eingeben und auch die Abhängigkeiten mit Installieren.


Nachdem das fncychap Makro noch von 2005 war:
von http://www.ctan.org/tex-archive/macros/latex/contrib/fncychap/
das fncychap.sty holen und nach /usr/share/texmf-texlive/tex/latex/fncychap/fncychap.sty kopieren.



Anleitung zum PDF's generieren


Auf Linux oder Mac kann man alle gezippten Bilder folgendermaßen entpacken

for x in `ls -1 *.zip`; do unzip $x; done

Nach dem entpacken aller Bilder, den folgenden Befehl aufrufen

python setup.py build
oder auch
python3 setup.py build

Nach ein paar Minuten sind die PDF's für Linux, Windows und Mac im target Verzeichnis fertig.

P.s. in diesen Files wird die Generierung des pdf eingetellt
+ in setup.py auf Zeile 17 oder 18 ob nur ein pdf oder drei pdf rauskommen (für Mac, Linux, Windows)
+ in swfk.tex.pre von Zeile 53 bis Zeile 75 welche Kapitel dabei sind und welche nicht.
+ auf frontmatter.tex auf Zeile 34 welche Version im Dateinamen des pdf stehen wird.

P.p.s.: damit beim hg push auch der richtige Benutzer mitkommt, in die 
.hg/hgrc Datei
den Abschnitt hinzufügen
[ui]
username = Vorname Nachname <vorname.nachname@gmail.com> 
