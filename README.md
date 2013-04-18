
Git for Dummies, Mac edition
En guide för hur git-kommandon används i Mac’s terminal (Command line). Instruktionerna gäller till största del även för PC. De understrukna orden är git-kommandon och texten under är förklaring på vad kommandona gör. Guiden kommer använda sig av en fabriksmetafor för att ge I:are möjlighet att förstå git utifrån ett mer familjärt perspektiv. 

1. Fabriksmetafor – en I:ares perpektiv	1
2. Git-kommandon	1
3. Importera ett upplagt projekt i Eclipse	3
4. FAQ	3
5. Övrigt – bra att veta	3
6. Återstående frågor att utredas	4
7. Androidprogrammering	4

1. Fabriksmetafor – en I:ares perpektiv
git status → Låter dig se vilka varor du har i lager
git add → Lastar ut varorna på lastbryggan
git commit -m "meddelande" → 	Lastar in varorna i lastbilen. Varorna är markerade med avin ”meddelande”
git push → Skickar iväg lastbilen till mottagaren
git pull → Tar emot en lastbil fylld med varor som läggs in i lagret
git fetch → Tar emot en lastbil fylld med varor men lägger INTE in dessa i lager

2. Git-kommandon
cd
Change directory

cd . 
Där jag står just nu (ingenting händer)

cd ..
Change directory to parent

cd mapp1/mapp2/mapp3
Change directory till mapp3

git clone
Skapar en mapp med samman namn som repot (repository) och kopierar innehållet i repot dit. Sätter även upp inställningar för att pusha och pulla till remoten (servern).

git status
Detta är våra ögon. Ger en överblick på vilka filer som är modifierade. Ser vilka varor som ligger i lager.
git add filnamn
Lastar ut filen ”filnamn” det på lastbryggan

git add .
Lastar ut alla modifierade filer på lastbryggan

git commit –m ”meddelande”
Lastar in det i lastbilen med avin ”meddelande”

git push 
Skickar iväg lastbilen till repository i molnet (på internet)

ls
Visar innehållet i en mapp, kan stå för List.

ls –a
Visar alla filer, även dolda (dolda filer är sånt som börjar med . för unixsystem (mac, linux, nästan allt utom windows), exempelvis .gitignore)

rm
Tar bort en fil om du får lov. Står för remove.

rm –r
Får lov att ta bort en mapp utan innehåll (dubbelkolla utifall detta inte stämmer). r står för recursive.

rm –rf mappnamn
Tar rekursivt bort mappen som heter mappnamn. rf står för recursive force vilket innebär att den inte frågar om lov när den är osäker vilket den kan vara om det händer något den inte förväntar sig. Exempelvis att det finns filer i undermappar. Detta kommando är specifikt för Mac (egentligen unix), på pc är det: rm mappnamn

git pull
Drar ner ändringar från centrala repository. Merge:ar ditt lokala repository med centrala repository i molnet.

git fetch
Drar ner ändringar från centrala repository men utan att merge:a.

Man måste göra en pull eller fetch för att kunna hämta hem ändringar som andra personer commit:at.

git diff HEAD~
Jämför HEAD (din senaste commit) med föregående commit. (~ uttalas ”Till de”)

git diff HEAD~~
Jämför HEAD (din senaste commit) med commit:en innan föregående commit. Ju fler ~ desto tidigare commit jämför du med. 

git reset
Git reset är motsatsen till git add, dvs den berövar en fil dess stage:ade tillstånd till skillnad från git add som ger ett stage:at tillstånd”.

När du har ställt ut varor på lastkajen men ångrar dig och vill ta tillbaka dom så anropar du git reset. Detta för att du ska kunna göra ändringar på varorna du trodde var redo att skickas, men inte var det. 

git reset --hard
Kommer att ångra allt som gjorts, dvs återställa alla ändrade filer till senaste commit. 

git log
Listar alla tidigare commits och visar vem som postat dom i ordningen senast först. 

git branch
Listar de de branches som finns i repot. 

git branch branchname
Låter dig byta från nuvarande branch till branch:en som heter branchname.

nano README.md
Öppnar filen README.md i terminalen så att det går att ändra innehållet, gäller endast för UNIX-system.
3. Importera ett upplagt projekt i Eclipse
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



