# OCR-D Empfehlungen Volltextdigitalisierung

- [Volltextdigitalisierung](#volltextdigitalisierung)
  - [Technische Parameter der digitalen Reproduktion](#technische-parameter-der-digitalen-reproduktion)
    - [Allgemeine Erläuterungen und Parameter](#allgemeine-erläuterungen-und-parameter)
      - [Textgenauigkeit](#textgenauigkeit)
      - [Textstruktur](#textstruktur)
      - [Zeichenkodierung](#zeichenkodierung)
      - [Dateiformate (Markup von Volltexten)](#dateiformate-markup-von-volltexten)
      - [Metadaten](#metadaten)
        - [Erschließung, deskriptive Metadaten](#erschließung-deskriptive-metadaten)
        - [Strukturelle Metadaten](#strukturelle-metadaten)
    - [Bereitstellung der Volltexte](#bereitstellung-der-volltexte)
    - [Technische Verfahren der Volltexterfassung bzw. -digitalisierung](#technische-verfahren-der-volltexterfassung-bzw--digitalisierung)
      - [Manuelle Erfassung (double keying)](#manuelle-erfassung-double-keying)
        - [Texterfassung](#texterfassung)
        - [Strukturerfassung](#strukturerfassung)
        - [Erfassungs-Dateiformate](#erfassungs-dateiformate)
      - [Automatische Erfassung (OCR)](#automatische-erfassung-ocr)
        - [Ground Truth](#ground-truth)
          - [GT-Richtlinien (OCR-D-Ground-Truth-Guidelines)](#gt-richtlinien-ocr-d-ground-truth-guidelines)
        - [Bildvorverarbeitung](#bildvorverarbeitung)
        - [Texterkennung](#texterkennung)
        - [Strukturerkennung](#strukturerkennung)
        - [Erfassungs-Dateiformate](#erfassungs-dateiformate-1)


# Volltextdigitalisierung
Die Volldigitalisierung kann grundsätzlich durch manuelle oder automatische Methoden erfolgen. Mit beiden Methoden werden wissenschaftlich nachnutzbare Forschungsdaten erzeugt, die in unterschiedlichen Bereichen genutzt und ausgewertet werden können. 
Welche Methode verwendet wird, ist im Einzelfall mit Blick auf die jeweiligen Anforderungen zu entscheiden. 
Die Methoden unterscheiden sich sowohl in der Vorgehensweise als auch in weiteren Bereichen wie bspw. Format und Qualität des Ergebnisses. 

Bei der **manuellen Texterfassung** kann das einfache und das double key-Verfahren unterschieden werden. 
Durch das zweifache Abschreiben und dem anschließenden Vergleich der Versionen können sehr hohe Genauigkeiten erreicht werden. 
Bei Anwendung von entsprechenden Transkriptionsregeln können auch das Layout bzw. besondere semantische Strukturen auf Grundlage von deren spezifischer typografischer Gestaltung erfasst werden. 

Das **automatische Verfahren** umfasst verschiedene technische Stufen, die aufeinander aufbauen können.
Grob unterscheiden kann man das Preprocessing, in dem das digitale Bild vorbearbeitet wird (binarisation, cropping, despeckling, deskewing, dewarping), die Optical Layout Recognition (OLR) (Segmentierung bzw. Identifikation von Bild- und Textregionen, Strukturanalyse), Optical Character Recognition (OCR) (eigentliche Texterkennung) und Postprocessing (Textkorrektur). 
Die Qualität des Ausgangsbilds hat einen entscheidenden Einfluss, bspw. auf den Prozess der Binarisierung und dieser wiederum auf das Erkennungsergebnis. 
Daher sollten nur digitale Vorlagen mit ausreichender Bildqualität (mind. 300 dpi, tiff) einer OCR-Bearbeitung unterzogen werden. 
Problematisch sind in diesem Zusammenhang auch intrinsische Phänomene wie Verschmutzungen, Widerdruck, manuelle Unterstreichungen oder Annotationen u.ä., die sich nachteilig auf den OCR-Prozess auswirken. 
Ebenfalls schwierig sind Marginalien in älteren Drucken oder auch Zeitungen mit komplexem Layout. Diese werden in der Layoutanalyse oft nicht korrekt erkannt, sodass die nachfolgende Texterkennung scheitert.

Um Daten aus der OCR nachnutzen zu können, wird die Verwendung der folgenden Formate empfohlen: 
* PAGE XML (Page Analysis and Ground truth elements) - empfohlen werden Version 2019-07-15 oder neuer
* ALTO XML (Analyzed Layout and Text Object) -  empfohlen werden Version 4.0 oder neuer
* TEI (Text Encoding Initiative) 

Darüber hinaus verwenden OCR-Programme auch interne Formate, die XML-basiert sind. Es wird empfohlen, diese ebenfalls zu speichern und für die weitere Nutzung zur Verfügung zu stellen.


## Technische Parameter der digitalen Reproduktion

Ziel der Volltextdigitalisierung ist die digitale Wiedergabe eines Textdokumentes nach Maßgabe wissenschaftlicher Erfordernisse. Die folgenden Empfehlungen für die Mindestanforderungen an die Volltextdigitalisierung beziehen sich ausschließlich auf den digitalen Volltext-Master.
* Definition des digitalen Volltext-Master
    * Format: XML entsprechend den Spezifikationen:
        * PAGE XML, ALTO XML, TEI
* Die Erkennung des Layouts mit seinen typographischen Strukturen ist weitestgehend sicherzustellen. Die Erkennung der textuellen Daten muss den wissenschaftlichen Erfordernisse entsprechen.
* Es ist sicherzustellen, dass die Metadaten (Provenienzdaten) sowohl der Volltexterfassung als auch des digitalen Masters (Digitalisat) in den entsprechenden Formaten gespeichert und zur Verfügung gestellt werden.

### Allgemeine Erläuterungen und Parameter

#### Textgenauigkeit

Unabhängig davon, ob ein Text durch manuell oder automatisch transkribiert wurde, stellt sich die Frage, in welcher Qualität die erfassten Texte vorliegen. Ziel der Volltextdigitalisierung ist es, nachnutzbare Forschungsdaten zu gewinnen. Um dies zu erreichen sollte den Empfehlungen im Bereich der technischen Formatvorgaben gefolgt werden.


#### Textstruktur

Neben der Textrepräsentation ist die Erfassung der Textstruktur der Vorlage wichtig und langfristig zu sichern. Die Textstruktur ist eine Abstraktion des Layouts. Es wird empfohlen folgende Formate für die Speicherung der Textstruktur:

* manuelle Verfahren:
    * TEI
    
* automatische Verfahren:
    * PAGE XML
    * ALTO XML

Die Textstruktur beinhaltet verschiedene Regionen der Vorlagenseite. Auf einer Seite können sich mehrere strukturell sowie inhaltlich verschiedene Regionen befinden. Die Textregion gliedert sich in weitere Unterspezifikationen, die näher zu bezeichnen sind. Auf struktureller Ebene gehören dazu u.a. Kolumnentitel, Überschriften, Absatzregionen, auf inhaltlicher Ebene bspw. Abbildungen, Buchschmuck, Tabellen sowie semantisch zu unterscheidende Regionen wie die lexikalische Beschreibung eines Lemma in einem Wörterbuch oder spezifische Abschnitte eines Briefs, bspw. Anrede oder abschließender Gruß. 

Es reicht nicht aus, den kompletten Satzspiegel als eine Textregion zu identifizieren. Stattdessen sind einzeln abgrenzbare Regionen zu lokalisieren, wodurch auch textuelle und nicht-textuelle Segmente klar voneinander getrennt werden.
Eine sogenannte Reading-Order ist anzugeben. Diese kann sich entweder aus der Aufeinanderfolge der Regionen ergeben oder explizit im jeweiligen Format angegeben werden.

Eine ausschließliche Speicherung des erfassten Textes in einer PDF-Datei mit eingebettetem Text-Ergebnis wird nicht empfohlen. Die PDF-Datei kann dem Erfassungs-Ergebnis zusätzlich hinzugefügt werden. Die PDF-Datei sollte der ISO-Norm 19005-1 entsprechen.


#### Zeichenkodierung
Alle verbreiteten Betriebssysteme unterstützen Unicode. Das Zeichenkodierungsformat von XML, das die Grundlage für die wichtigsten Strukturdatenauszeichnungssysteme darstellt, ist ebenfalls Unicode. Daher wird empfohlen, die Texte in Unicode abzuspeichern. Zu verwenden ist UTF-8 ohne Byte-Order Mark (BOM).

Für die Codierung von Zeichen, die nicht im Unicode-Standard enthalten sind, wird vorrangig die Nutzung der communitynormierten Codierungen MUFI (Medieval Unicode Font Initiative MUFI) empfohlen. Sind Zeichen auch in diesen Codierungstabellen nicht enthalten, ist eine innerhalb der jeweiligen Community abgestimmte Codierung zu verwenden. Diese individuelle Codierung ist entsprechend zu dokumentieren.

#### Dateiformate (Markup von Volltexten)
Die Verwendung von spezifischen Dateiformaten ist abhängig von der Erfassungsmethode. Es ist zwischen dem Erfassungsformat und dem Ergebnisformat zu unterscheiden. Als Erfassungsformat kann das XML-Format genutzt werden. Es ist zu gewährleisten, dass sowohl die textuellen als auch die struktur-typografischen Informationen bei der Erfassung beachtet und erfasst werden. Die Wahl des Markups unterliegt in der Regel projektspezifischen Besonderheiten. Daneben ist die Austauschbarkeit und Nachnutzbarkeit von auf diese Weise mit Markup versehenen Volltexten sicherzustellen. Dies wird gewährleistet durch die Beschreibung des Formates und die Bereitstellung des Schemas oder der Dokumenttypdefinition (siehe z.B. die Dokumentation des DTA-Basisformates (http://www.deutschestextarchiv.de/doku/basisformat/index.html).

Bei der Kodierung von XML-Strukturen muss zunächst entschieden werden, wie und in welchem Umfang textsortenspezifische Strukturen (Gliederungen) wie z. B. Kapitel, Unterkapitel, Jahresbände, Aufsätze etc. berücksichtigt werden sollen. Hinzu kommen weitere denkbare Strukturmerkmale, z. B. Inhaltsverzeichnisse, Register, Zeilenumbruch, Spaltenumbruch, Seitenumbruch, Kopfzeile/Fußzeile/Kolumnentitel, Seitenzahl, Bilder oder bildähnliche Elemente, Bildunterschriften, Marginalien, Schriftwechsel, z. B. der Wechsel von Fraktur zu Antiqua (etwa für fremdsprachige Zitate), der Wechsel der Schriftgröße, Wechsel der Schriftart (recte, kursiv, fett usw.) u. a. m., Formeln, z. B. mathematische (MathML) oder chemische (CML) Formeln, Fortsetzungsmarkierungen (Kustoden) am Fußende von Seiten (für Anschlussseiten) etc.

Die Entscheidungen sind in Transkriptionsrichtlinien zu dokumentieren, die sich an Richtlinien des Deutschen Textarchivs oder den OCR-D-Ground-Truth-Richtlinien orientieren. Die Dokumentationsmöglichkeiten der verwendeten XML-Elemente und Attribute im TEI-Header zu beschreiben, sind zu nutzen. 
Bei der Auswahl von geeigneten Schemata oder Dokumenttypdefinitionen sind die Text Encoding Initiative (TEI), das DTA-Basisformat (DTABf) und bibliothekarische Standards wie ALTO zu berücksichtigen.

Beim PDF handelt es sich um ein Präsentationsformat. Dieses Format ist als Ergebnisformat ungeeignet. Es ist lediglich zur Darstellung in Viewern bzw. zum Druck vorgesehen. Für eine  Nachnutzung gerade durch die digital arbeitenden Geistes- und Kulturwissenschaften ist dieses ungeeignet, da es an struktureller Auszeichnung mangelt und die automatische Weiterverarbeitung erschwert ist.
Für die Veranschaulichung der Erfassungsergebnisse sind projektspezifische Lösungen zu wählen. Diese können u.a. eine Text-Bild-Präsentation und eine dynamisch generierte Lesefassung umfassen, die als Download (PDF) oder im Browser (HTML) neben dem Ergebnisformat angeboten werden.

* Beim manuellen Verfahren

    | Erfassungsformat  | Ergebnisformat |
    | --------          | --------       |
    | XML               | TEI            |



* Beim automatischen Verfahren

    | Erfassungsformat  | Ergebnisformat |
    | --------          | --------       |
    | XML, PAGE         | ALTO, TEI      |


#### Metadaten

Die vorhandenen Metadatensätze (METS/MODS) des Digitalisates sind während des Prozesses der Volltextdigitalisierung um die einzelnen Etappen des Workflows sowie eine Referenz (URI) auf die OCR-Ergebnisse zu ergänzen.
Der erstellte Metadatendsatz ist grundsätzlich in von der Software unabhängiger und standardkonformer Form (METS/MODS) bereitzustellen.
Für Details zum METS/MODS Metadatensatz siehe: Requirements on handling METS/PAGE: https://ocr-d.de/en/spec/mets

##### Erschließung, deskriptive Metadaten
Die Erschließung mit deskriptiven Metadaten kann bei der Volltextdigitalisierung zum einen den Volltext, zum anderen bestimmte Merkmale des Bilddigitalisates betreffen, bspw. Gebrauchsspuren wie Stempel oder Annotationen. Im Volltext können diese exemplarspezifischen Merkmale mit erfasst sein. Jedoch ist zu gewährleisten, dass diese Informationen eindeutig vom Text der Publikation zu unterscheiden sind. 
Über die deskriptiven Metadaten werden bestimmte Inhalte gezielt durch eine Recherche auffindbar. Im Idealfall bieten die deskriptiven Metadaten Anknüpfungspunkte für unterschiedliche Fachdisziplinen und Fragestellungen. 

Für die Erschließung von deskriptiven Metadaten wird das Format METS/MODS empfohlen. Zusätzlich empfiehlt sich das OCR-D-Labelling nutzen. Diese Ontologie ermöglicht es einzelne Spezifika normiert zu beschreiben und zu erfassen. Die bereitgestellten Metadaten müssen gegen das jeweilige XML Schema valide sein und sind darüber hinaus auf semantische Korrektheit zu überprüfen. 
* METS/MODS
* OCR-D-Labelling : Labeling OCR ground truth data with special METS-Profile: https://github.com/OCR-D/gt-labelling


##### Strukturelle Metadaten
Es ist davon auszugehen, dass die strukturellen Metadaten im Zuge der Bilddigitalisierung im METS/MODS Datensatz erfasst wurden. Wird im Zuge der Volltexterfassung eine weitere Strukturerfassung vorgenommen, ist diese zusätzlich zur ursprünglichen Erfassung und von dieser klar unterscheidbar im Metadatensatz zu speichern.
Die strukturellen Metadaten können Textregionen wie z. B. Widmung, Vorwort, Kapitel, Illustration oder auch spezifische Textsorten wie Lexikoneinträge umfassen. Bei manchen Fragestellungen sind strukturelle Metadaten auch für die Recherche interessant. Die Entscheidung über die Erstellung struktureller Metadaten ist daher immer mit Blick auf die Anforderungen des spezifischen Materials und Projekts zu treffen.
Für Details zum METS/MODS Metadatensatz siehe: Requirements on handling METS/PAGE: https://ocr-d.de/en/spec/mets 



| Format     | Spezifikation                                                                            | 
| -----------| --------                                                                                 |
| PAGE XML   | https://www.primaresearch.org/schema/PAGE/gts/pagecontent/2019-07-15/pagecontent.xsd     | 
| ALTO XML   | https://www.loc.gov/standards/alto/                                                      | 
| TEI        | https://tei-c.org/                                                                       |


### Bereitstellung der Volltexte
Die Bereitstellung von Volltexten soll sowohl für die maschinelle als auch die menschliche Nutzung geeignet sein. In beiden Fällen ist der Volltext in Verbindung mit seinen Metadaten in einem entsprechenden Bereitstellungssystem zur Verfügung zu stellen. Der Volltext liegt in einem strukturierten Format (ALTO XML, PAGE XML oder TEI) vor.

Um die maschinelle Nutzung zu erleichtern wird empfohlen standardisierte Schnittstellen wie REST anzubieten. Der automatisierte Zugriff auf den Volltext soll u.a. Harvesting, Textmining, automatisierte Übersetzung, Normalisierung/Korrektur, linguistische Analysen sowie korpusbasierte Analyse ermöglichen.

Die Formate ALTO XML, PAGE XML oder TEI können durch Transformation oder Konvertierung zweckgebunden umgewandelt werden. 
Für die Präsentation sollten Formate wie (X)HTML/EPUB oder Druckformate wie PDF genutzt werden. 


### Technische Verfahren der Volltexterfassung bzw. -digitalisierung

#### Manuelle Erfassung (double keying)
Man unterscheidet bei der Direkterfassung – dem Abschreiben – von Texten zwei Verfahren, das einfache und das double key-Verfahren. Bei Letzterem wird ein Text zweimal erfasst und die Abweichungen beider Versionen durch automatischen Textabgleich herausgefiltert. Auf diese Weise sind Erfassungsgenauigkeiten von 99,97 % erreichbar, also ein praktisch fehlerfreier Text. 

Sollte die Erfassung durch einen Dienstleister vorgenommen werden, so muss eine brauchbare Textgenauigkeit als Zielvorgabe auch vertraglich fixiert werden. Diese Vorgabe ist an Stichproben des digitalisierten Texts zu überprüfen (s.o.). Eine Genauigkeit von 99,5 % ist bei manueller Erfassung als ungenügend einzuschätzen. 

Es ist zu berücksichtigen, dass die Transkription auch für die Herstellung von Ground Truth genutzt werden kann. Aus diesem Grund ist im Projekt einzuplanen, diese Transkriptionen als Forschungsdaten in einem entsprechenden Bereitstellungssystem (z.B. Zenodo, NFDI) mit den dafür notwendigen Metadaten zur Verfügung zu stellen.

##### Texterfassung
Manuelles Erfassen bietet zwar eine hohe Genauigkeit, ist aber arbeitsintensiv und organisatorisch vorzubereiten. Es ist einzuplanen, dass die eigentliche Texterfassung im Ausland vorgenommen wird; der Kontakt mit einer Digitalisierungsfirma sollte jedoch über einen Ansprechpartner in Deutschland erfolgen, da in der Regel eine enge Kooperation und Absprache zu den Erfassungsdetails erforderlich ist. Eine starker interpretatorischer Eingriff bei der Transkription (wie Normalisierungen, Zeichenersetzung (I/J; langes-s/normales s)) sowie die Löschung des Zeilenfalles ist zu unterlassen. Die Zeichenkodierung des Textes erfolgt nach Unicode (siehe 3.2.2.1.3 Zeichenkodierung (MB).



##### Strukturerfassung
Das Digitalisierungsprojekt hat festzulegen, welche Eigenschaften der Vorlage mittels eines strukturellen Markups erfasst werden sollen. Hierbei können nur solche Eigenschaften ausgezeichnet werden, die typografisch und gegebenenfalls durch spezifische Hinweise im Text erkennbar sind. Einfache Strukturen können vom Dienstleister automatisch erkannt werden, bei weitergehenden Angaben müssen diese im Bild vor der Übergabe an den Dienstleister entsprechend markiert werden. 

Dies verursacht einen entsprechenden Personalaufwand und muss bei der Kalkulation des Projekts berücksichtigt werden. Da die meisten Dienstleister den Text nach Zeichenmenge inklusive des Markups berechnen, ist es ratsam, für diese Zwecke eine zeichenarme Auszeichnungsvariante zu verwenden.

Die Strukturerfassung sollte in einem strukturierten Format (siehe 3.2.2.1.4 Dateiformate (Markup von Volltexten) (MB) erfolgen sowie dem Forschungszweck entsprechen. 

##### Erfassungs-Dateiformate
Folgende Dateiformate sind für die manuelle Erfassung zu verwenden. Wenn nicht triftige Gründe dagegen sprechen, müssen Volltexte nach dem Modell der TEI kodiert bzw. mit Markup versehen werden. Bei der Spezifizierung eines Schemas nach den Guidelines for Electronic Text Encoding and Interchange (TEI) sollte man sich am DTA-Basisformat orientieren oder dieses anwenden.

Zusätzlich können die Formate TXT (Textformat) oder XML auf Basis eines alternativen Schemas oder Dokumenttypdefinition verwendet werden. Bei TXT ist die Zeichencodierung auf Basis von Unicode zu beachten.
* TEI (https://github.com/TEIC/TEI)
* Richtlinien (DTABf http://deutschestextarchiv.de/doku/basisformat/transkription.html)
* TXT, XML

#### Automatische Erfassung (OCR)
Für die Volltextdigitalisierung stehen eine Vielzahl von Programmen zur Verfügung. Bei der Programmwahl sollten folgende Aspekte bzw. Fragen beachtet und geprüft werden:
*  In welcher Erschließungstiefe können die vorliegenenden Digitalisate erfasst werden.
    *  Erfassungsart (Text- und Struktur)
*  Welche Dateiformate werden angeboten und können diese in andere Formate transformiert werden.
    *  Dateiformat
* Kann das Programm gegebenenfalls für den Verwendungszweck erweitert und angepasst werden?
* Können neben den generischen Erkennungsmodellen auch werkspezifische oder projektspezifische Modelle trainiert oder verwendet werden?
* Kann das Programm in den eigenen Digitalisierungsworkflow integriert werden?
* Sind Lizenzkosten, Wartungskosten einzuplanen?

##### Ground Truth
Ground Truth (GT) ist die digitale, korrekte Wiedergabe der Druckvorlage sowohl auf der Ebene der Zeichen als auch der typografischen Struktur. Aus GT können Trainingsdaten erstellt werden, die grundlegend für die Erstellung neuer oder verbesserter Modelle zur automatischen Text- und Strukturerkennung sind. Daneben kann GT zur Evaluation der automatischen Erfassung genutzt werden. 

Die GT ist im Format PAGE XML zu speichern, das auf einem XML-Schema basiert. Dieses Schema legt fest, wie graphematische und strukturelle Phänomene, beispielsweise Seitenzahlen, Kolumnentitel, Marginalien, Fußnoten, Abbildungen, Überschriften und Absätze, in diesem Format kodiert werden. Auf Grundlage dieser technisch-formalen Ebene ist es möglich, die Korrektheit der GT zu validieren. 

Für die Erstellung sind Transkriptionsrichtlinien anzuwenden und zu dokumentieren. Es wird empfohlen die OCR-D-Ground-Truth-Richtlinien zu verwenden.

Folgende Grundsätze sind bei der GT-Transkription zu beachten:
* Die Erfassung der Texte erfolgt nach den Prinzipien der Wahrung des historischen Sprachstandes des Textes und der größtmöglichen Bewahrung des   Vorlagentextes unter Beachtung der lexikalischen Gegebenheiten.
* Aufgrund dieser Zielsetzung wird darauf geachtet, bei der Texterfassung die Zahl der (unvermeidbaren) Interpretationen typographischer Gegebenheiten gering zu halten. Die Lösungsmöglichkeiten zur Interpretation spezifischer Phänomene wurden in drei abgestuften Leveln festgelegt. 
* Es erfolgt keine Druckfehlerkorrektur.

Sowohl bei der Transkription als auch bei der Nachnutzung von erfassten Texten als GT, ist im ersten Schritt das entsprechende Erfassungs-Level (Level der vorlagengetreuen Wiedergabe) auszuwählen. Diese Entscheidung ist in den dafür vorgesehenen Metadaten zu dokumentieren.  
 
* Richtlinien zur Transkription für Ground Truth: https://ocr-d.de/de/gt-guidelines/trans/transkription.html


Wird GT im Projektkontext erstellt, ist diese öffentlich und mit einer frei zugänglichen Lizenz zur Verfügung zu stellen.

###### GT-Richtlinien (OCR-D-Ground-Truth-Guidelines)
Die OCR-D-Ground-Truth-Guidelines dokumentieren zum einen das Ground-Truth-Format und zum anderen geben sie Nutzenden Handlungsanweisungen für die Ground-Truth-Erstellung. Darüber hinaus können vorhandene Transkriptionen auf Grundlage dieses Regelwerkes überprüft und gegebenenfalls in Ground-Truth-Daten umgewandelt werden.

* OCR-D-Ground-Truth-Guidelines https://ocr-d.de/en/gt-guidelines/trans/

##### Bildvorverarbeitung
Die Bildvorverarbeitung ist ein Teilschritt der automatischen Volltextdigitalisierung. Diese kann vor der Texterkennung durchgeführt werden. Sie umfasst verschiedene Prozesse der automatischen Bildverarbeitung (Binarization [Umwandlung in ein Schwarz-Weiß-Bild], Cropping [Zuschneiden des Digitalisates oder eines bestimmten Bildausschnittes), Deskewing [Begradiung des Digitalisates]), Dewarping [Entzerrung des Digitalisates] und Despeckling [Reinigung des Digitalisates von Flecken und Artefakten]).

Werden digitale Bilder (Alternativbilder) bei der Bildvorverarbeitung erstellt, wird empfohlen, diese im METS/MODS-Datensatz zu verzeichnen. Dadurch kann zum einen die Volltextdigitalisierung nachverfolgt werden und zum anderen können einzelne Prozessschritte gegebenenfalls wiederholt werden.
* Requirements on handling METS/PAGE: https://ocr-d.de/en/spec/mets  
   
##### Texterkennung
Bei der Texterkennung werden die Zeichen der digitalen Vorlage identifiziert und als digitale Zeichen (Text) gespeichert. Die Texterkennung ist grundsätzlich vom Erkennungsmodell des OCR-Programms abhängig. Es ist zu überprüfen, ob das Erkennungsmodell die gewünschten Vorgaben des Digitalisierungsvorhabens (korrekte Übertragung der Zeichen) erfüllt. In den meisten Fällen liegen den OCR-Programmen umfangreiche generische Erkennungsmodelle für mehrere Sprachen bei. 


##### Strukturerkennung
Die Erfassung der Struktur eines Dokumentes (im folgenden Optical Layout Recognition, OLR, in der wissenschaftlichen Literatur auch Segmentierung oder Zoning genannt) stellt neben der Texterkennung die wichtigste Komponente der Volltextdigitalisierung dar: Sie beeinflusst die Qualität des Textergebnisses maßgeblich und ist ein wesentlicher Faktor für die wissenschaftliche Nachnutzbarkeit des digitalen Volltextes.

Die Layouterkennung kann mehrere Erkennungsschritte umfassen. In der Regel wird mit der Seitensegmentierung begonnen. Dabei wird eine Lokalisierung der bedruckten, abgrenzbaren Bereiche einer Seite sowie deren Unterteilung in Text und Nichttextzonen (z.B. Abbildungen, Grafiken) vorgenommen. Es folgt die Zeilensegmentierung, bei der die Textzeilen der einzelnen Textbereiche identifiziert werden. Daran anschließen können die Segmentklassifizierung und Dokumentanalyse. Bei der Klassifizierung der Segmente werden den einzelne Textbereichen auf der Seite entsprechend ihrer Funktion Informationen im Page-Format hinterlegt. Beispielsweise wird dem Textbereich, der die Seitenzahl beinhaltet, die Information “pagenumber” zugewiesen. Auf ähnliche Weise können auch Seitenbereiche wie Spalten, Überschriften oder Fußnoten klassifiziert werden. Diese Informationen können sowohl der Rekonstruktion des korrekten Textflusses (Reading Order), als auch der darauf aufbauenden Dokumentanalyse dienen. In dieser Analyse wird die innere Struktur des gesamten Druckwerkes erfasst. Dabei können u.a. die erkannten Überschriften der einzelnen Seiten hierarchisiert werden. 

Die Strukturerkennung ist abhängig vom gewählten Erkennungsmodell und dem Erkennungsalgorithmus. Es ist zu überprüfen, ob das Erkennungsmodell die jeweiligen Vorgaben des Digitalisierungsvorhabens erfüllt. Das Erkennungsmodell muss mindestens folgende Bereiche erkennen:
* (reiner) Textbereich mit Textzeilen
* Abbildung 
* Tabelle 
* Separator
* Sonstiges
Für die VD-Volltextdigitalisierung sind nur solche Erkennungsmodelle zu nutzen, bei denen die Strukturerkennung die oben genannten und folgenden Parameter erfüllt: 

Alle Regionen einer Seite sind zu erkennen und entsprechend der unten stehenden beispielhaft aufgeführten Typologie zu kennzeichnen. Es reicht nicht aus, den kompletten Satzspiegel als einen Textblock zu identifizieren. Stattdessen müssen einzeln abgrenzbare Blöcke lokalisiert werden. Übergeordnetes Ziel ist die Trennung von textuellen und nicht-textuellen Segmenten. Über die angeführten Anforderungen hinaus, die jedes verwendete Erkennungsmodell erfüllen muss, können manche Erkennungsmodelle weitere Bereiche erfassen. Ein maximales Erfassungsergebnisse liegt vor, wenn die folgenden Regionen wie folgt feintypisiert werden: 
* Text 
* Abbildung (Zeichnung, Grafik) 
* Vignette (Buchschmuck) 
* Tabelle 
* Diagramm 
* Separator 
* Mathematische Formel 
* Chemische Formel 
* Noten 
* Werbung 
* Rauschen (u.a. Verschmutzungen, Stempel) 
* Handschriftliche Anmerkungen 
* Sonstiges

##### Erfassungs-Dateiformate
Folgende Dateiformate sind für die Volltextdigitalisierung zu verwenden. Volltexte sind mit Markup nach dem XML Standard zu versehen. Das Format hat sowohl den Text als auch die Strukturinformationen der Vorlage zu umfassen. Die Speicherung des Volltextes im Format ALTO XML (Version 4.0) ist mindestens zu erfüllen.

Zusätzlich können die Formate PAGE XML, ABBYY XML, und TEI verwendet werden. Bei der Verwendung von TEI ist den Guidelines for Electronic Text Encoding and Interchange (TEI) sowie bei der Spezifizierung eines Schemas dem DTA-Basisformat zu folgen.
* ALTO XML (http://www.loc.gov/standards/alto/)
* PAGE XML https://ocr-d.github.io/page, https://github.com/PRImA-Research-Lab/PAGE-XML)
* ABBYY XML (https://www.ocrsdk.com/documentation/specifications/xml-scheme-recognized-document/)
* TEI (https://github.com/TEIC/TEI)
* DTA-Basisformat  (http://deutschestextarchiv.de/doku/basisformat)







