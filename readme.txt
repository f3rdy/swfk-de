-----------------------------------------------------------------
Allgemeines
-----------------------------------------------------------------

LaTeX source of "Snake Wrangling for Kids"

Dieses Werk ist unter einem Creative Commons Namensnennung-Keine kommerzielle Nutzung-Weitergabe 
unter gleichen Bedingungen 3.0 Deutschland Lizenzvertrag lizenziert. Um die Lizenz anzusehen, gehen Sie bitte 
zu http://creativecommons.org/licenses/by-nc-sa/3.0/de/ oder schicken Sie einen Brief an 
Creative Commons, 171 Second Street, Suite 300, San Francisco, California 94105, USA.



Auf einem frischen Ubuntu sollten diese Pakete installiert sein, damit das Generieren der pdf's gleich klappt.
Am besten gleich in der Konsole
sudo apt-get mercurial python3 python3-tk texmaker texlive-full ttf-linux-libertine
eingeben und auch die Abhängigkeiten mit Installieren.


Nachdem das fncychap Makro noch von 2005 war:
von http://www.ctan.org/tex-archive/macros/latex/contrib/fncychap/
das fncychap.sty holen und nach /usr/share/texmf-texlive/tex/latex/fncychap/fncychap.sty kopieren.


Anleitung zum PDF's generieren


python setup.py build
oder auch
python3 setup.py build

Nach ein paar Minuten sind die PDF's für Linux, Windows und Mac im target Verzeichnis fertig.

P.s. in diesen Files wird die Generierung des pdf eingetellt
+ in setup.py auf Zeile 19 oder 20 ob nur ein pdf oder drei pdf rauskommen (für Mac, Linux, Windows)
+ in swfk.tex.pre von Zeile 130 bis Zeile 162 welche Kapitel dabei sind und welche nicht.
+ auf frontmatter.tex auf Zeile 74 welche Version im Dateinamen des pdf stehen wird.


P.p.s.: damit beim hg push auch der richtige Benutzer mitkommt, in die 
.hg/hgrc Datei
den Abschnitt hinzufügen
[ui]
username = Vorname Nachname <vorname.nachname@gmail.com> 



-----------------------------------------------------------------
Offen
-----------------------------------------------------------------

Farben überprüfen


In Appendix A das Bild der Wunschliste anpassen
In Appendix B eine Alternative für die in Python 3 weggefallene cmp Funktion finden

testen ob hg clone und bauen mit latex nach frischem checkout funktioniert
und dazuschreiben, welche Pakete auf Ubuntu installiert sein müssen

in appendix d bei Übungen Links einfügen zu Übung 1, Übung 2 der einzelnen Kapitel



swfk.tex.pre pdf Titel anpassen                            OK
preface: Bilder vom Installieren in den Mac Abschnitt?



-----------------------------------------------------------------
Fertig
-----------------------------------------------------------------

Übersetzen
    Titel anpassen (frontmatter.tex)                       OK   
    Kapitel  1                                             OK
    Kapitel  2                                             OK
    Kapitel  3                                             OK
    Kapitel  4                                             OK
    Kapitel  5                                             OK
    Kapitel  6                                             OK
    Kapitel  7                                             OK
    Kapitel  8                                             OK
    Kapitel  9                                             OK
    Kapitel 10                                             OK

    Appendix A                                             OK
    Appendix B                                             OK
    Appendix C                                             OK
    Appendix D                                             OK


Layout wie französische Version
    Kapiteldesign \usepackage[Bjornstrup]{fncychap}        OK
    Rahmen um Codebeispiele mit \usepackage{fancyvrb}      OK
    Schriften Linux Libertine einbauen                     OK
    Umstieg von latex auf xelatex                          OK
    Bilder von eps ins pdf wandeln (mit Inkscape)          OK


Build Prozess
    setup.py anpassen damit der Dateiname richtig          OK
    Stickwortverzeichnis mit makeindex dabei               OK




