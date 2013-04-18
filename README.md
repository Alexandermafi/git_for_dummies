#Git for Dummies, Mac edition
En guide för hur git-kommandon används i Mac’s terminal (Command line). Instruktionerna gäller till största del även för PC.Orden tabellen är terminal- och git-kommandon med  förklaring av vad de gör. Guiden kommer använda sig av en fabriksmetafor för att ge I:are möjlighet att förstå git utifrån ett mer familjärt perspektiv. 

1.	Fabriksmetafor - en I:ares perspektiv
2.	Terminal-kommandon (ett urval)
3.	Git-kommandon
4.	Importera ett upplagt projekt i Eclipse
5.	FAQ
6.	Övreigt - bra att veta + ordlista
7.	Återstående frågor att utreda
8.	Androidprogrammering
9.	Men vad händer om kan kör Windows?
		- Använd Git Bash
		- Används powershell
10.	Pro Tip:
11. Ytterligare Dokumentation

# 1. Fabriksmetafor – en I:ares perpektiv
git status → Låter dig se vilka varor du har i lager
git add → Lastar ut varorna på lastbryggan
git commit -m "meddelande" → 	Lastar in varorna i lastbilen. Varorna är markerade med avin ”meddelande”
git push → Skickar iväg lastbilen till mottagaren
git pull → Tar emot en lastbil fylld med varor som läggs in i lagret
git fetch → Tar emot en lastbil fylld med varor men lägger INTE in dessa i lager


# 2. Terminal-kommandon (ett urval)
Det här är alla de kommandon som fungerar i terminalen.

| Kommando | Funktion |
| ------ | ------ |
| cd | Change directory – byt map |
| cd .  |  |
| cd .. |  |
| cd ~ | byter map till din hemmapp (användare) |
| cd folder1/folder2/folder3 | Byter till folder 3, som ligger I folder2 etc |
| touch filnamn | Skapar en ny fil med namnet filnamn |
| ls | Visar synliga filer och mappar på den nuvarande platsen |
| ls –a | Visar alla (även dolda) filer och mappar på den nuvarande platsen: -a kallas för en flagga till ls |
| rm filnamn | tar bort filen filnamn. Fungerar inte med mappar |
| rm –r mappnamn | Tar rekursivt bort allt innehåll i en mapp  |
| rm –rf mappnamn | Tar rekursivt bort mappen som heter mappnamn. rf står för recursive force vilket innebär att den inte frågar om lov när den är osäker vilket den kan vara om det händer något den inte förväntar sig. Exempelvis att det finns filer i undermappar. Detta kommando är specifikt för Mac (egentligen unix), på pc är det: rm mappnamn. VÄLDIGT KRAFTFULLT, så var försiktig. Ex kommer rm-rf * ta bort ALLT… |
| nano README.md | Öppnar filen README.md i terminalen med editorn nano. Det går då att ändra innehållet direkt i terminalen. Gäller endast UNIX-system. |
| vim README.md | Öppnar filen README.md i vim. Vim är coolt (streetcred i IT-världen – ungefär som att köra Aston Martin bland I:are). |
| man kommando | Får upp en detaljerad beskrivning av kommandot. EX: man cd |
| kommando --help | Får upp en kortare hjälp för ett kommando |
| ctrl + c | Avbryter nuvarande kommando |
| grep –r searchterm | Söker rekursive I ALLA FILER efter söktermen. Mycket kraftfullt! Går att använda med wildcard (*) |
| EXTREMT MYCKET MER | Googla |

Alla kommandon som har med git att göra börjar med git, följt av kommandonamnet. Detta säger till terminalen att den ska använda git och köra de efterföljande funktionerna som definierats av git.
# 3. Git-kommandon
| Kommando | Funktion |
| ------ | ------ |
| git clone | Skapar en mapp med samman namn som repot (repository) och kopierar innehållet i repot dit. Sätter även upp inställningar för att pusha och pulla till remoten (servern). |
| git status | Detta är våra ögon. Ger en överblick på vilka filer som är modifierade. Ser vilka varor som ligger i lager. Finns även en hel del tips på kommandon som man kan använda här. |
| git add filnamn | Lastar ut filen filnamn på lastbryggan. Används också för att säga till git att spåra nya filer eller mappar.  |
| git add . | Lastar ut alla modiferade filer (i den aktuella mappen?) på lastbryggan |
| git commit –m ”meddelande” | Lastar in det i lastbilen med avin ”meddelande” |
| git commit –am ”meddelande” | För dig som är lite lat och lastar lastbilen utan lastbrygga |
| git push | Skickar iväg lastbilen till repository i molnet (på internet/gihub). SKICKA BARA IVÄG FUNGERANDE KOD! |
| git pull | Drar ner ändringar från centrala repository (från internet/github). Marge:ar ditt lokala repository med centrala repository i molnet. |
| git fetch | Drar ner ändringar från centrala repository men utan att merge:a. Läggs under branch origin/master, som man sen kan merge:a med. Man måste göra en pull eller fetch för att kunna hämta hem ändringar som andra personer commit:at. |
| git diff | Jämför olika versioner av filer. Se exempel nedan. |
| git diff HEAD~ | Jämför HEAD (din senaste commit) med föregående commit (~ uttalas och heter ”Tilde”) |
| git diff HEAD~~ | Jämför HEAD (din senaste commit) med den dubbelt föregående commit:en. Ju fler ~, desto tidigare |
| git diff HEAD^5 | jämför HEAD med den commit för fem gånger sen |
| git diff branch1 branch2 file | Jämför file mellan två olika branches |
| git reset | Git reset är motsatsen till git add, dvs den berövar en fil dess stage:ade tillstånd till skillnad från git add som ger ett stage:at tillstånd”. När du har ställt ut varor på lastkajen men ångrar dig och vill ta tillbaka dom så anropar du git reset. Detta för att du ska kunna göra ändringar på varorna du trodde var redo att skickas, men inte var det.  |
| git reset --hard | Kommer att ångra allt som gjorts, dvs återställa alla ändrade filer till senaste commit. |
| git reset --hard HEAD^ | Återställer den senaste commiten och återställer working tree och alla pekare (VARNING!) |
| git log | Listar alla tidigare commits och visare vem som postat dem i ordningen; senaste först |
| git branch | listar alla branches som finns |
| git branch branchnamn | Skapar en ny branch kallad branchname |
| git checkout branchname | Byter från nuvarande branch till branchname |
| git checkout –b branchname | Skapar en ny branch kallad branchname och byter till den |
| git merge branchname | Marge nuvarande branch med branchname |

4. Importera ett upplagt projekt i Eclipse
5. FAQ
6. Övrigt - bra att veta + ordlista
7. Återstående frågor att utreda
8. Androidprogrammering
9. Men vad händer om kan kör Windows?
	- Använd Git Bash
	- Används powershell
10. Pro Tip:
11. Ytterligare Dokumentation

# 3. Importera ett upplagt projekt i Eclipse
file → import → veckla ut mappen ”android” och tryck på ”Existing Android Code Into Workspace → Välj ”Root Directory”, kryssa i projektet som dyker upp i rutan, tryck finish.

Kodningen sker i Eclipse men all kontakt med repot på servern ska ske genom Terminalen (command line).
 
4. FAQ
Varför ska jag inte använda Githubs GUI (Graphic User Interface)?
- För att det inte funkar. Den hittar inte förändringar. Fyra av fem problem som dyker upp beror på att man försöker göra något i GUI:t som inte fungerar. GUI:t är endast utformad efter de vanligaste funktionerna och kan krångla om vissa kommandon används. 

5. Övrigt – bra att veta
HEAD – du har en commit som servern inte har
BEHINDE – servern har en commit som du inte har
DIVERGE – du har en commit som servern inte har och servern har en commit som du inte har

Conflict uppstår när två oberoende ändringar har justerad samma rad i en fil.
6. Återstående frågor att utredas
Fortsatta frågor:
1.	Vad gör ctrl + c och när ska man använda detta i terminalen?
2.	När behöver man trycka på q? Ibland låser sig terminalen och då är lösningen att trycka q, men när?
3.	Dirty workspace?

7. Androidprogrammering
•	Du får inte skapa en ny mapp i res-mappen. 