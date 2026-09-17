# **Git** är ett **(version control system)**  
### *Git* gör gruppsarbete lättare och hjälper dig med att spara dina versioner av din kod, Exempelvis: version 1, version 2,version 3  osv...  
  
- Du kan när som helst gå tillbaka till vilken version du vill.  
- Sålänge du har en sparad version, då vågar du ändra din code och sen ångra.  
- Flera personer kan jobba på samma projekt utan att skriva på varandra. 
*** 

### Steg 1: Skapa ett GitHub konto
1. **Gå till** [Gihub.com](https://github.com)  
1. Klick **Sign up**, fyll i din mail och lösenordet och Skapa ett Konto om du inte redan har det, eller **logga in.**   
1. Bekräfta koden som kommer till din gmail.
***


### Steg 2: Installera **git** på din maskin
#### **⬇️Välj din opperativsystem⬇️**  Sedan följ insturktioner på sidan.  
>- **[**Windows** ](https://git-scm.com/install/windows)**  
>- **[**macOS** ](https://git-scm.com/install/mac)**  
>- **[**Linux** ](https://git-scm.com/install/linux)**


### Steg 2.5: ⬇️Installera⬇️ **VS-Code**  
>- **[**Windows,Linux,macOS** ](https://code.visualstudio.com/download?_exp_download=fb315fc982)**  
***  


### Steg 3: Berätta för git **vem du är**  
```Bash   
git config --global user.name "Milo"               #(Du kan skriva vilket namn du vill)  (Milo är min katt 🐈😁)
git config --global user.email "Meaw@gmail.com"    #(Din e-mail som är kopplad till ditt github)  
```  
***  


### Steg 4: Berätta för git vad din **(Huvud-Tidslinje)** ska heta    
Git har en tidslinje som förr i tiden hette **`master`**, men programmerare tyckte att det är bäst att döpa det till **`main`** för bättre matchning med github.  

- Varje projekt har sin egen tidslinje som heter **`main`** så att dina projekt inte krokar ihop.  
- Det som vi ska göra nu i nästa kommando är att ändra namnet från **`master`** till **`main`**.  
```Bash  
git config --global init.defaultBranch main  
git config --list    #(för att kontrollera att uppgifter du gav stämmer).  
```  
***  


### Steg 5: Skapa Projektes **`map`** på din PC, sedan öppna mappen i VS-Code.  
```Bash  
mkdir Projekt1  #(Skapar fil med namn Projekt1)  
```

```Bash
# (Bash)
cd Projekt1/  #(kommer in i Projekt1 filen) 
touch Projekt1.md  #(skapar en .md-fil. Du kan skapa vilken fil-typ du vill.)

code .    #(Öppnar VS-Code direkt från terminalen.)  
```  
```Bash  
#(Powershell)  
cd .\Projekt1\  #(kommer in i Projekt1 filen)
type null > Projekt1.md #(skapar en .md-fil. Du kan skapa vilken fil-typ du vill.)  

code .    #(Öppnar VS-Code direkt från terminalen.)
```  
***  

### Steg 6: Lägg till git i projektets map och aktivera main där  
**Stå i (`Projektsts mapp`) öppna terminalen och skriv...**  
```Bash
git init      #(nu finns git i mapp som heter bilalgit)

git status    #(Kontrollera att git kom in i mapp bilalgit)

git add .     #(git lägg till alla ändringar, snart ska allt sparas)  

git commit -m "Jag ändrade är.."  #(git spara allt nu och skriv ett meddelande “ändrade ..”)

git log --oneline #(visar maintidlinje ID och medeladne på versionen du sparade.)
```  
***  
### Steg 7:<span style="color: red; font-weight: bold;"> SUPER VIKTIGT</span> FÖR SÄKERHET (`.gitignorer`).  
Vissa saker som `lösenord` och `API-nycklar` ska **absolut aldrig sparas** sådär eller komma ut på nätet.  
Därför lägger vi ett spärr på vissa filtyper som `.env` så att git låtsas som att dom inte finns.  
Den anpassas bara på den mapp/projekt du vill anpassa det på, (`skriver igen för varje projekt`)  

**1: Skapa filen i projektets map, det är en dold fil.**  

```Bash
touch .gitignore  (skapar en tom fil som heetr .gitignore i projektets fil)
ls -a             (kontrollerar att filen finns, ls -a visar dolda filer)
```  
**2: Öppna `.gitignore` filen och skriv in vad git ska ignorera**
```Bash  
nano .gitignore
```  

**(⬇️Kopiera allt nedan och klistra in i `.gitignore` filen⬇️)**  
```          
# / på slutet betyder "hela mappen" alltså att den inte ska läsa något i hela mappen
# * betyder "vad som helst" alltså *.key = vad som helst som slutar på .key ska inte läsas
# ! “ignorera inte denna”

#Filer som aldrig får komma till github (säkerhet)

hemlighet/
hemligt/
*.env*
!.env.example
*.key
*.pem
*.p12
*.pfx
*.crt
*.jks
*.keystore
*secret*
*password*
*credential*
*token*
id_rsa
id_ed25519
*.ppk
.npmrc
.pypirc
.netrc

# Cloud och Infrastruktur
.terraform/
*.tfstate
*.tfstate.*
*.tfvars
!*.tfvars.example
.aws/
kubeconfig
*.kubeconfig
*.ovpn
serviceAccount*.json

#Riktig viktig databaser data

*.sqlite
*.sqlite3
db.sqlite3-journal
*.db
*.rdb
*.dump

# onödiga stora  mappar som inte behövs

node_modules/
venv/
.venv/
env/
ENV/
__pycache__/
*.py[codz]
*.so
build/
dist/
*.egg-info
.eggs/
wheels/
__pypackages__/

#test,cache och typkontroll

.pytest_cache/
.ruff_cache/
.mypy_cache/
.tox/
.nox/
.coverage
.coverage.*
htmlcov/
coverage.xml
.cache
.ipynb_checkpoints

# Skräp filer

*.log
*.bak
Thumbs.db
desktop.ini
.idea/
.DS_Store
.vscode/
*.swp
*~ 
```
**(⬆️Kopiera och klistra in i `.gitignore`⬆️)**

Tryck (CRTL + o) för att spara  
Tryck (CRTL + x) för exit  
** Skapa en `.env` fil och sen testa om den kommer med när du skriver `ls -a` **  
***  

### Steg 8: Skapa repository (Repo) på **[Gihub.com](https://github.com)**  
1. Logga in på [Gihub.com](https://github.com) >> **`New repository`**  
1. Döp den till projektets namn  
1. >**VIKTIG: Bocka inte i** Add a `README` eller Add `.gitignore`, Vi lägger till en bättre  `.gitignore` senare.  
1. Klicka på `Create repository`.  
***  


### Steg 9: Koppla din dator med [Gihub.com](https://github.com)  
**Två `Metoder` att (`Koppla`) din dator till [Gihub.com](https://github.com) välj en av metoderna!** 

- `Metod 1`: Med Personal Access Token (PAT) via HTTPS, har utgångsdatum på 90 dagar.**  

**Öppna din [Gihub.com](https://github.com), `Setting > Developer setting > Personal access Tokens > Token (classic) > Create`**

Verifiera med gmail, och du får engångs användnings Token  
Bra att veta, origin är smeknamn för din sida på GitHub

```Bash 
git remote add origin https://github.com/ ditt anavädnarenamn på git  
git push -u origin main

#Username: Skriv in ditt användarnamn 
#Password: Klistra in Personal Access Token (PAT) här.

#För att slippa klistra in varje gång du använder appen…

git config --global credential.helper cache #(lagrar din Token i 15min)
git config --global credential.helper `cache --timeout=28800` 
(Efter 8 Timmar rensas Token från din RAM minne)
```  

- `Metod 2`: Skapar SSH 🔑 (Public och Private),Public delar med GitHub, och private stannar hos på PC.**  

```Bash
ssh-keygen -t ed25519 -C “meaw@gmail.com” #Du skriver din e-mail där.
 
#Här kan du välja att lägga till lösenord så det är bara du som kan komma åt filerna, annars kan vem som helst ta din nycklar och pusha hur de vill. Men här kommer jag inte sätta lösenord.

#Tryck Enter 2 gånger. 
```  
**Kopiera din publika nyckel den slutar med `.pub`, Om du inte hittar den (följ instruktionerna nedan⬇️)**  

>**- Windows: `Öpnna din C-drive > users > Din profil > du kommer hitta en (.ssh) fil öppna den, din Publica key där (.pub).`**  

>**- Bash: `öppna home/ > Din profil > du kommer hitta en (.ssh) fil öppna den, din Publica key där (.pub).`**  

**Öppna din [Gihub](https://github.com), Setting > SSH and GPG keys > New SSH key >Klistra in din SSH Publica key här**  
```Bash  
ssh -T git@github.com #(Verfiera anslutningen)
#Tryck Enter tills det kommer upp (Hi … ! You´ve successfull …)
```
***  

### Steg 10: Daglig ändringar och uppladdningar till **[Github](https://github.com)**  
> <span style="color: red; font-weight: bold;"> SUPER VIKTIGT:</span> När du har ändrat i filen, du måste spara den antigen `file > save` eller `CTRL + S`.  

> **⬇️ Senario 1 ⬇️** : Laddar upp **alla** filer i mappen som `.git` lever i. ⬇️ 
1. Du öppnar din projekt, ändrar skriver nått nytt code ( i olika filer )
2. Du  vill nu spara alla dina nya ändringar i alla filerna  
3. **Detta anvädner du när du ska ladda upp hela mappen som, `git lever i`**. Det kan vara att du ändrade på alla fielrna (Bulk uppload).
```Bash
git status   #(kollar vad som hände)
git add .     #(git packa ner alla ändringar i mappen som du är registerat i, och lägg dom i lådan för snart ska allt sparas)
git commit -m "Jag ändrade är fil2-VB f3-kommand... "  #(Döp lådan till ...)
git push          #git lägg lådan i garaget(github), så att personer med rätt behörighet kan se innehåll. 
```  
> **⬇️Senario 2 ⬇️** : Laddar upp **Specefik** fil av mappen som `.git` lever i. ⬇️

**Vi säger att du har en mapp där det finns olika filer, `( milo.md & eko.md )` Du vill specefik ladda upp bara filen `milo.md` till [Github](https://github.com)**  
```Bash  
git add "milo.md" #packa ner denna filen i lådan, vi ska snart ladda upp det till gihub.  
git status #filen milo.md ska visas med grönt text, det betyder att filen finns i lådan.  
git commit -m "v2_ändrade..." #Döp lådan till ...  
git push origin main #git lägg lådan i garaget(github), så att personer med rätt behörighet kan se innehåll.  
``` 

**Tack För Din Tid**  
**Skriven av Bilal**