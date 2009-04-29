Hinweise
========

Diese Diplomarbeitsvorlage wurde urspr�nglich vom FSR Physik
bereitgestellt und von mir f�r meine Diplomarbeit angepasst.  Ich gebe
hiermit im Prinzip also nur meine Tipps und Tricks weiter, ohne den
Anspruch zu erheben, eine formal und technisch komplette Vorlage
bereitzustellen.


Unterschiede zur FSR-Vorlage
----------------------------

* Zweiseitiger Druck mit entsprechend angepassten R�ndern und
  Kopfzeilen.

* Times statt Computer Modern als Schrift

* Keine Einr�ckung am Anfang eines Absatzes

* Anpassung der Silbentrennungsparameter

* Nummerierung von Tabelle, Abbildungen und Gleichungen nach dem
  Schema ``kapitel.lfd-nr`` statt ``kapitel.abschnitt.lfd-nr``.


dvipdfm als LaTeX-Treiber
-------------------------

Als Kompromiss zwischen dem reinen PDF-Treiber ``pdflatex`` und dem
Umweg �ber PostScript mittels ``dvips`` bzw. ``dvipdf`` (beide sind
nicht zu empfehlen!) empfiehlt sich ``dvipdfm``.  Er wandelt die
DVI-Daten direkt in PDF um.  Damit entstehen qualitativ bessere
PDF-Dateien, in denen z.B. Inhaltsverzeichnis und Querverweise noch
navigierbar sind (dank ``hyperref``-Paket).

dvipdfm kann allerdings keine EPS-Dateien o.�. einbinden.  Bei mir hat
sich als vorteilhaft herausgestellt, s�mtliche Abbildungen als PDF
vorzuhalten.  Gnuplot beispielsweise kann ohne Probleme PDF ausgeben.
Die PDF-Dateien m�ssen in der PDF-Version 1.2 vorliegen, h�here
Versionen kann dvipdfm leider nicht bearbeiten.  Man kann allerdings
"schummeln" und PDF-Dateien einfach nachtr�glich als Version 1.2
deklarieren, indem man den PDF-Header �ndert.  In jedem Fall ben�tigt
dvipdfm Informationen �ber die "bounding box", die sich mit dem
Programm ``ebb`` erzeugen lassen.  Siehe dazu
http://www.tex.ac.uk/cgi-bin/texfaq2html?label=dvipdfmgraphics.


Makefile
--------

Um die verschiedenen Arbeitsschritte beim Generieren des PDFs zu
automatisieren, liegt der Vorlage ein Makefile f�r GNU make bei.
Damit reicht ein Aufruf von ``make`` auf, um LaTeX, BibTeX und dvipdfm
in der richtigen Reihenfolge aufzurufen.
