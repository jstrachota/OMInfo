# OMInfo
OMI === Projekt pro vytvoreni databaze IND-Ex v nejnovejsi verzi. Nasazuje se do schemat &amp;&amp;ARCHIV, &amp;&amp;KONFIG, &amp;&amp;LOADER, &amp;&amp;READER, &amp;&amp;TEST_KONFIG, &amp;&amp;ARCHIVE_MGMT. Tato schemata nemusi byt ruzna. (Celou databazi IND-Ex lze umistit treba do jedineho schematu - nevhodne pro produkci!)
!!! vzdy ZKONTROLOVAT: "Find in Files [áčďéěíňóřšťúůýž] Look in Entire Solution,  Use Regular Expressions"
			Nechceme zadnou diakritiku, protoze jinak se texty pri nejakych prenosech urcite zmrsi...

Toto reseni (solution) slouzi k podpore zivotniho cyklu soustavy aplikaci zalozenych na schematu IND-Ex		(shrnuti IND-Exu cti az dole)
*******************************************************************************************************

reseni obsahuje nasledujici projekty typu Oracle DB :
													(projekty jsou pripraveny pro nasazeni jako adresare s instrukcemi ve svem __README, staci mit libovolne prostredi pro spousteni skriptu SQL, napr. SQL*Plus, SQL Developer, ...)

OMI
===
Projekt pro vytvoreni databaze IND-Ex v nejnovejsi verzi.
Nasazuje se do schemat &&ARCHIV, &&KONFIG, &&LOADER, &&READER, &&TEST_KONFIG, &&ARCHIVE_MGMT. Tato schemata nemusi byt ruzna. (Celou databazi IND-Ex lze umistit treba do jedineho schematu - nevhodne pro produkci!)

OMI_Tests
=========
Projekt pro instalaci databazovych objektu potrebnych k provadeni testovacich skriptu.
Testovaci skripty.
Nasazuje se do libovolneho schematu.


rady projektu upgrade<VERZE>_<casovaZnacka>
===========================================
Slouzi pro zmenu databaze <VERZE> na stav dosazeny k casove znacce.
Pro bezvadnou zmenu produkcni databaze je nutno provest vsechny zmenove projekty v posloupnosti casovych znacek az do te nejnovejsi. POZOR: pokud reseni uz obsahuje novejsi casovou znacku, mohou byt chyby kompilace PL/SQL pro starsi casove znacky.
(Alternativne je mozne vytvorit nejnovejsi verzi databaze s prenosem dat.)

OMI_Applications
================
TODO: Projekt pro instalaci databazovych objektu potrebnych pro pouziti API IND-Ex.
Nasazuje se do libovolneho schematu.


---------------------------------------------------------

IND-Ex je aplikacne neutralni semanticke informacni schema (RDBMS) slouzici jako infobaze = "staj" pro objektove modely libovolne casti naseho sveta/vesmiru/multivesmiru/...
**********************************************************						 **************************************

Vychazi z nazoru, ze zijeme ve svete/... objektu, ktere jsou instancemi sveho typu. Typy maji asociacni veliciny, instance se mohou agregovat a mohou mit rozhrani libovolneho typu.

Schema IND-Ex ma semanticke dimenze (tabulky RDBMS) ve sve KONFIGURACI. Konfigurace je oblast, kde vlastnik ROZHODUJE, nastavuje.
Pro archivaci hodnot velicin libovolneho objektu, ktere vlastnik infobaze jen POZORUJE (nerozhoduje), slouzi oblast ARCHIVU. (Archiv je tabulka pro dany typ hodnoty a klice atomu.)

CHOVANI TYPU OBJEKTU je deklarovano (pripadne i implementovano) jako STEJNOJMENNY package Oracle.

---------------------------------------------
DOKUMENTACE IND-Ex:
*******************
Primarni dokumentace je primo ve schematu IND-Ex jako KOMENTARE u VSECH databazovych objektu (Table, Package), pripadne skriptu.
Tato forma dokumentace nema byt nejdokonalejsi, ale je VZDY PO RUCE A MUSI BYT VZDY PLATNA = UP TO DATE!!! (Historie je zachycena v Source Control.)

