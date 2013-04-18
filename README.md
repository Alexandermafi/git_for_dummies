#Git for Dummies, Mac edition
En guide för hur git-kommandon används i Mac’s terminal (Command line). Instruktionerna gäller till största del även för PC. De understrukna orden är git-kommandon och texten under är förklaring på vad kommandona gör. Guiden kommer använda sig av en fabriksmetafor för att ge I:are möjlighet att förstå git utifrån ett mer familjärt perspektiv. 

[1. Fabriksmetafor - en I:ares perspektiv]

[2. Terminal-kommandon (ett urval)]

[3. Git-kommandon]

[4. Importera ett upplagt projekt i Eclipse]

[5. FAQ]

[6. Övrigt - bra att veta + ordlista]

[7. Återstående frågor att utreda]

[8. Androidprogrammering]

[9. Men vad händer om kan kör Windows?]

[10. Pro Tip:]

[11. Ytterligare Dokumentation]

[1. Fabriksmetafor - en I:ares perspektiv]:https://github.com/Alexandermafi/git_for_dummies#1-fabriksmetafor--en-iares-perpektiv
[2. Terminal-kommandon (ett urval)]:https://github.com/Alexandermafi/git_for_dummies#2-terminal-kommandon-ett-urval
[3. Git-kommandon]:https://github.com/Alexandermafi/git_for_dummies#3-git-kommandon
[4. Importera ett upplagt projekt i Eclipse]:https://github.com/Alexandermafi/git_for_dummies#4-importera-ett-upplagt-projekt-i-eclipse
[5. FAQ]:https://github.com/Alexandermafi/git_for_dummies#5-faq
[6. Övrigt - bra att veta + ordlista]:https://github.com/Alexandermafi/git_for_dummies#6-vrigt--bra-att-veta
[7. Återstående frågor att utreda]:https://github.com/Alexandermafi/git_for_dummies#7-terstende-frgor-att-utredas
[8. Androidprogrammering]:https://github.com/Alexandermafi/git_for_dummies#8-androidprogrammering
[9. Men vad händer om kan kör Windows?]:https://github.com/Alexandermafi/git_for_dummies#9-men-vad-hnder-om-kan-kr-windows
[10. Pro Tip:]:https://github.com/Alexandermafi/git_for_dummies#10-pro-tip
[11. Ytterligare Dokumentation]:https://github.com/Alexandermafi/git_for_dummies#11-ytterligare-dokumentation


# 1. Fabriksmetafor - en I:ares perspektiv
- git status -> Låter dig se vilka varor du har i lager
- git add -> Lastar ut varorna på lastbryggan
- git commit -m "meddelande" -> Lastar in varorna i lastbilen. Varorna är markerade med avin ”meddelande”
- git push -> Skickar iväg lastbilen till mottagaren
- git pull -> Tar emot en lastbil fylld med varor som läggs in i lagret
- git fetch -> Tar emot en lastbil fylld med varor men lägger INTE in dessa i lager

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

# 3. Git-kommandon
Alla kommandon som har med git att göra börjar med git, följt av kommandonamnet. Detta säger till terminalen att den ska använda git och köra de efterföljande funktionerna som definierats av git. För att se vanliga funktioner som finns, skriv bara git i terminalen och tryck på enter

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

# 4. Importera ett upplagt projekt i Eclipse
file → import → veckla ut mappen ”android” och tryck på ”Existing Android Code Into Workspace → Välj ”Root Directory”, kryssa i projektet som dyker upp i rutan, tryck finish.

Kodningen sker i Eclipse men all kontakt med repot på servern ska ske genom Terminalen (command line).


 
# 5. FAQ
Varför ska jag inte använda Githubs GUI (Graphic User Interface)?
- För att det inte funkar. Den hittar inte förändringar. Fyra av fem problem som dyker upp beror på att man försöker göra något i GUI:t som inte fungerar. GUI:t är endast utformad efter de vanligaste funktionerna och kan krångla om vissa kommandon används. 
- FÖr att terminalen är mycket coolare
Varför behöver jag en .gitignore?
- En .gitignore-fil säger till git vilka filer som INTE ska spåras av systemet. Det kan vara bra att ta bort binära filer, som till exempel bilder eller word-dokument (den sista går dock att tracka med lite jobb). Binära filer är något som git inte kan hantera på samma sätt som rena textdokument - för varje gång filen sparas och commitas till systemet kommer det skapas en kopia av filen i fråga: om man har stora filer (.psd, .tif etc.) kan det göra att ens git-projekt tar väldigt mycket plats på datorn (det tar också mycket längre tid att ladda ner projektet). För ett javaprojekt är det till exempel lämpligt att ta bort alla .class filer. Det görs genom att lägga till *.class i .gitignore-filen. Det finns standarduppsättningar av dessa filer på github som är rätt så bra.
Vart ska jag lägga en .gitignore-fil?
- En .gitignore-fil kommer att påverka alla filer och mappar som ligger i den mapp där .gitignore-filen finns. Lägg alltså den filen i den översta mappen i ert projekt! En .gitignore-fil som syftar att ta bort en filtyp som läggs till efter att sådana filer redan spårats av systemet kommer inte att ha någon effekt - man måste då manuellt säga till git att sluta spåra de filerna. [Läs mer om att avgryta språning här].

[Läs mer om att avgryta språning här]:http://stackoverflow.com/questions/4124792/remove-an-existing-file-from-a-git-repo

# 6. Övrigt – bra att veta
| Term | Beskrivning |
| ------ | ------ |
| AHEAD | du har en eller flera commit som servern inte har (du ligger före) |
| BEHIND | servern har en/flera commit som du inte har (du ligger efter) |
| DIVERGE | du har en commit som servern inte har och servern har en commit som du inte har |
| HEAD | Pekar mot den nuvarande positionen i databasen |
| Dirty Workspace | du har gjort ändringar som inte ännu commitats till git-databasen |
| Working Tree | Den version av filer som är laddade just nu |
| .gitignore | En fil som anger vilka filer eller filtyper som inte ska spåras av git |

# 7. Återstående frågor att utredas
- [ ] 1. När behöver man trycka på q? Ibland låser sig terminalen och då är lösningen att trycka q, men när?

# 8. Androidprogrammering
- Du får inte skapa en ny mapp i res-mappen. 
- Ladda ner en lämplig .gitignore-fil och lägg den i rooten av ditt android-projekt

# 9. Men vad händer om kan kör Windows?
Går du mot strömmen? Är du lite coolare än alla andra? Kör du Windows? Svara du ja på någon (eller alla) av de frågorna (speciellt sista frågan), läs följande:
## Använd inte kommandotolken
Eftersom kommandotolken inte har någon inbyggd git-funktionalitet är det inte så lämpligt att använda den. Det är också lite annorlunda kommandon för att navigera i kommandotolken jämfört med terminalen etc.
## Använd Git Bash
Följer med git-installationen och är som en terminal för windows. De flesta Unix-kommandon fungerar (man kan skriva över ännu fler), men den är ganska långsam att använda, vilket är lite tråkigt.
## Använd powershell
Du har säkert hört talas om kommandotolken (kör: cmd). Det finns en bättre ”version”: (kör: powershell). Powershell är ännu kraftfullare än terminalen; powershell kan göra allt som .NET kan göra – dvs. ganska mycket.

Det finns ett ”plugin” till powershell som gör att git integreras. Kolla [HÄR] för att få det att fungera. Behöver du hjälp? Fråga Anton.

# 10. Pro Tip:
- Sublime text 2 är en helt fantastisk texteditor – [check it out!]
- Om du använder Mac eller Linux, fixa Zsh och byt ut den gamla tråkiga terminalen. Länk och lite förklaring [finns här].
- Lägg till aliases i terminalen för kommandon du använder ofta – sparar tid!

# 11. Ytterligare Dokumentation
- http://git-scm.org: officiella hemsidan för .git
- http://gitref.org: referens för vanliga kommandon (ganska enkelt förklarat)
- Intro till .git som gjorts av en av grundarna till github: [youtube]


[här]:http://haacked.com/archive/2011/12/13/better-git-with-powershell.aspx
[youtube]:http://www.youtube.com/watch?feature=player_detailpage&v=ZDR433b0HJY#t=2791s
[check it out!]:http://www.sublimetext.com/2
[finns här]:http://www.maclife.com/article/columns/terminal_101_better_shell_zsh