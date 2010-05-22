-----------------------------------------------------------------
Allgemeines
-----------------------------------------------------------------

LaTeX source of "Snake Wrangling for Kids"

Dieses Werk ist unter einem Creative Commons Namensnennung-Keine kommerzielle Nutzung-Weitergabe 
unter gleichen Bedingungen 3.0 Deutschland Lizenzvertrag lizenziert. Um die Lizenz anzusehen, gehen Sie bitte 
zu http://creativecommons.org/licenses/by-nc-sa/3.0/de/ oder schicken Sie einen Brief an 
Creative Commons, 171 Second Street, Suite 300, San Francisco, California 94105, USA.



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

Verschiedenes
    swfk.tex.pre pdf Titel anpassen                        OK




-----------------------------------------------------------------
Offen
-----------------------------------------------------------------

Farben überprüfen

In Appendix B eine Alternative für die in Python 3 weggefallene cmp Funktion finden

preface: Bilder vom Installieren in den Mac Abschnitt?

als print on demand Buch veröffentlichen?






%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
---------------------------------------------------------------------
Anleitung wie das Buch auf einem Ubuntu 10.04 generiert wird
---------------------------------------------------------------------
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%



---------------------------------------------------------------------
0. Vorbereitung
---------------------------------------------------------------------

sudo apt-get install mercurial python3 python3-tk xz-utils 
eingeben und auch die Abhängigkeiten mit Installieren.


---------------------------------------------------------------------
1. Install Texlive 2009 from ISO 
---------------------------------------------------------------------

Torrent Download von http://www.tug.org/texlive/acquire-iso.html#torrent oder 
einem Mirrow von CTAN http://www.ctan.org/tex-archive/CTAN.sites wie zum Beispiel
http://sunsite.informatik.rwth-aachen.de/ftp/pub/mirror/ctan/systems/texlive/Images/texlive2009-20091107.iso.xz

xz Archiv entpacken
~/ xz --decompress texlive2009-20091107.iso.aachen.xz 



texlive.iso mounten
sudo mount -t iso9660 -o ro,loop,noauto /pfad/zu/texlive2009-20091107.iso /mnt 
cd /mnt

sudo ./install-tl
default Werte lassen bis auf <5> TEXMFHOME und installieren (wichtig für Punkt 3. xelibertine)


Current directories setup:
===============================================================================

 <1> TEXDIR:       /usr/local/texlive/2009
     support tree: /usr/local/texlive/2009/texmf

 <2> TEXMFLOCAL:     /usr/local/texlive/texmf-local
 <3> TEXMFSYSVAR:    /usr/local/texlive/2009/texmf-var
 <4> TEXMFSYSCONFIG: /usr/local/texlive/2009/texmf-config

 <5> TEXMFHOME:      /home/user/Downloads/texmf

 Note: ~ will expand to $HOME (or to %USERPROFILE% on Windows)

Other actions:
 <R> return to main menu
 <Q> quit

---------------------------------------------------------------------
 See
   /usr/local/texlive/2009/index.html
 for links to documentation.  The TeX Live web site (http://tug.org/texlive/)
 contains any updates and corrections.

 TeX Live is a joint project of the TeX user groups around the world;
 please consider supporting it by joining the group best for you. The
 list of groups is available on the web at http://tug.org/usergroups.html.

 Add /usr/local/texlive/2009/texmf/doc/man to MANPATH.
 Add /usr/local/texlive/2009/texmf/doc/info to INFOPATH.
 Most importantly, add /usr/local/texlive/2009/bin/i386-linux
 to your PATH for current and future sessions.

 Welcome to TeX Live!
---------------------------------------------------------------------



---------------------------------------------------------------------
2. Umgebungsvariablen setzen
---------------------------------------------------------------------

gedit /home/user/.profile
ganz unten dazuhängen

# new PATH für Latex
PATH=$PATH:/usr/local/texlive/2009/bin/i386-linux
export PATH 

----------
damit es gleich gültig ist ein 
source ~/.profile 
ausführen um die Umgebunsvariblen zu aktualisieren.

$ exec bash 

überprüfen mit 
echo $PATH



---------------------------------------------------------------------
3. XELibertine bereitstellen
--------------------------------------------------------------------
http://mirror.ctan.org/systems/win32/miktex/tm/packages/xelibertine.tar.lzma
xelibertine.tar.lzma entpacken nach /home/user/Downloads/texmf



---------------------------------------------------------------------
4. Schrift nachinstallieren
---------------------------------------------------------------------

Download Linux Libertine Fonts von http://sourceforge.net/projects/linuxlibertine/files/
mkdir /home/user/.fonts
LinLibertineFont-4.4.1.tgz entpacken und Ordner nach /home/user/.fonts kopieren
sudo fc-cache -f -v



---------------------------------------------------------------------
5. Anleitung zum PDF's generieren
---------------------------------------------------------------------

python  setup.py build   
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








