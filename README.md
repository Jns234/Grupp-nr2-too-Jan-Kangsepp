# Apache MQ alternatiivid ja nende plussid ja miinused 

## IBM MQ 

### Kirjeldus 

IBM MQ on message broker, mis lihtsustab ja kiirendab erinevate rakenduste ja andmete integreerimist mitmel platvormil. See kasutab teabe vahetamiseks message queue't ja pakub ühtset sõnumsidelahendust pilve-, mobiil- ja IoT-keskkondadele. Ühendades praktiliselt kõik, alates lihtsast rakendusepaarist kuni kõige keerukamate ärikeskkondadeni, parandab see reageerimisvõimet, kontrollib kulusid, vähendab riske ja annab andmetest reaalajas ülevaate. See on saadaval standardväljaandes, täiustatud väljaandes, seadmena ja z/OS-i versioonina.

### Plussid

Kuna IBM MQ on loodud IBM'i poolt on sellel olemas oma ala parim kasutajatugi, mis on alati abivalmis. Koos sellega tuleb väga sõbralik kasutajaliides ja kõrge turbetase millega kaasneb kindel töökindlus. 

### Miinused

IBM MQ kasutamine algajale on väga keeruline ja selle õppimisega kaasneb ka kõva learning curve. Paljud süsteemid ja osad on aegunud ja ebaintuitiivsed kasutuses, näiteks pilve migratsioon nõuab uuendamist, scalability mõttes on kasutaja piiratud serverite juurdetekitamisega ja lakkab konteinerites.  

## RabbitMQ 

### Kirjeldus 

RabbitMQ on populaarne open-source message broker, mis on kasutuses üle maailma idufirmades ja suurettevõtetes. 

### Plussid

RabbitMQ on lightweight ja seda on kerge paigaldada pilves ja füüsilise riistvara peale. See toetab mitut sõnumsideprotokolli. RabbitMQ-d saab kasutada hajutatud ja ühendatud konfiguratsioonides, et täita kõrgetasemelisi ja kõrge kättesaadavuse nõudeid. 
RabbitMQ töötab paljudes operatsioonisüsteemides ja pilvekeskkondades ning pakub laia valikut arendajatööriistu enamiku populaarsete keelte jaoks.

### Miinused 

RabbitMQ monitoorimine ja haldamine võib raskeks muutuda, kuna puudub kindel tarkvara selle jaoks. Kasutajatugi võib puudulikuks ka jääda, kuna tegu ei ole suure firma teenusega. 

## Azure Scheduler 

### Kirjeldus
Azure Scheduler võimaldab käivitada töid, nagu näiteks kutsuda HTTP/S-i end-point'e või postitada sõnumeid Azure Storage'i queue'sse, mis tahes ajakava järgi, mistõttu on see ideaalne korduvate toimingute jaoks, nagu logide puhastamine, varukoopiate käivitamine ja muud hooldustoimingud. 

### Plussid 

Scalability töötab väga hästi, kuna tegu on Microsofti teenusega, sellega kaasneb ka hea integratsioon muude Azure teenustega. Turbe on kõrgetasemeline. 

### Miinused

Kuna tegu on ikka Microsoftiga, siis iga muu platformi mis ei ole windows on paras peavalu selle setupimisega ja crashimisega. Mõned tehnoloogiad mis ei ole Microsofti omad ei taha väga hästi töötada ja jäävad tahaplaanile. 


# RabbitMQ kasutamine

Enda töös ma otsustasin kasutada RabbitMQ kuna see on tasuta ja open-source, lisaks headele review'dele. 
RabbitMQ käivitamiseks mul oli vaja installida dependency mis oli vaja selle käivitamiseks. Erlang, mis on programmeerimiskeel, mida kasutatakse massiliselt skaleeritavate pehmete reaalajas süsteemide ehitamiseks, mis nõuavad kõrget käideldavust. Mõned selle kasutusalad on telekommunikatsioonis, panganduses, e-kaubanduses ja kiirsuhtluses. Erlangi käitusaja süsteemil on sisseehitatud samaaegsuse, jaotuse ja tõrketaluvuse tugi. 

Kasutuskeeleks ma otsustasin võtta puhast Javat ja abiks ma kasutan RabbitMQ dokumentatsiooni, milles sender peab "Hello world!" recieverile edasi andma. Erinevused Apache MQ'st on (vähemalt antud näide) kergem, annotatsioon polnud kasutuses ja dependencied tõmbasin ja panin samasse kasuta käsitsi ka, tõenäoliselt on targem viis selle tegemisesk aga seda ma ei tea. 
