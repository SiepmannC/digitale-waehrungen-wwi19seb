# In Etwa Repräsentativer Klausuraufbau

## Grundlagen zur Blockchaintechnologie

### Distributed Ledgers / Verteilte Logbücher
Unter welchen Umständen ist die Nutzung von verteilten Logbüchern im Vergleich zu zentral verwalteten Logbüchern aus Ihrer Sicht empfehlenswert?
- Daten/Kontrolle werden verteilt und können nicht so leicht missbraucht werden
- Dezentralität bei Transaktionen ermöglicht es niemanden die Zahlungen zu verhindern oder zurückzuverfolgen
- Anonymität
- Übertragbarkeit (Digitales Geld)
- Sicherheit/Transparenz
#### Lösung
1. Digital 
2. Von verschienden Marktteilnehmer mit unterschiedlichen Intressen verwendet
3. Keine Zentrale Instanz realisierbar (sonst eher Zentral)
4. Aufwand für die Blockchain ist geringer als der Nutzen

Was ist für Sie das revolutionär Neue an der Blockchaintechnologie?
- Durch die dezantralität des Systems ist es möglich, die Macht der Internetanbieter wie Meta, Google etc. enzuschränken, weil sichergestellt werden kann, dass nicht jede meiner Anfragen über den Meta-Server geht, welcher Meine Informationen speichert und weiterverkauft (Hierbei besonders auf WEB3 bezogen)
- Durch die Möglichkeit der der Blockchain Technnologie wird das "Internet of Things" ermöglicht, mit welches es möglich sein soll, dass ein Auto mit einer Ladesäule kommuniziert und mit dieser selbständig den Preis für den Strom festlegt 



Inwiefern können wir eine Blockchain als öffentliche, verteilte Datenbank betrachten?
- öffentlich weil jeder Zugriff auf das System hat und die Daten über alle Geräte verteilt abgespeichert werden, es gibt somit keine Zentrale anlaufstelle
- verteilt weil wir die Daten Dezentral abspeichern, rest siehe oben

Inwiefern ermöglicht die Blockchain Technologie Peer 2 Peer Geschäfte ohne zentralisierte Mittelsmänner / Institutionen?  
Hilfestellung / gehen sie dabei vieleicht auf die folgenden Apekte ein...: welches sind die zentralen Institution im oldschool CeFi Sysem? Ohne die BC Technology mussten wir zentralen Instituitonen vertrauen...

- Online kaufen dann ist die Bank (2x) dazwischen, ansosnten könnte das Geld direkt an den Verkäufer gehen.
- Durch Smart Contracts ist es dann möglich ohne die Zentralen Institute Verträge zu erstellen. Statt einen Mittelsmann wie die Webseite Crowdfunding, können die Investoren direkt mit dem Unternehmen den Vertrag erstellen. Wenn das Geld ausreicht wird es ausgezahlt, ansonsten geht es zurück an die Investoren

### Einwegfunktionen

Welche Einwegfunktion spielt im Bitcoin System eine wesentliche Rolle bzw. zwei wesentliche Rollen? Bitte erläutern Sie dies.
- Einwegfunktion ist die Hashfunktion
- Aktuell wird Sha256 hauptsächlich verwednet
- gibt aber auch Sha512 besipielsweise mit einer höheren Sicherheit
- Durch die Hashwerte kann zum einen kryptographisch sichergestellt werden, dass meine Daten nicht im Klartext an dritte gehen
- zum anderen können durch die Hashwerte sogennante Merkle-Trees aufgestellt werden, welche die Integrität des Bitcoin-System sicherstellen 
- Proof of Work (Anzahl an Nullern muss vorne stehen und dafür wird das Gewicht hochgezählt (1,2,3,...))
- Nicht zurück übersetzbar 
- Davits Video hier einfügen (Warum Einweg, zurückrechnen

Bitte nennen Sie 3 Bedingungen, die erfüllt sein müssen, damit eine Hashfunktion aktuell als kryptographisch sicher gilt.
- 256 Bit
- der Endwert für ein Input sollte möglichst nur einmalig vorkommen und es sollte keinen zweiten Input geben, der den gleichen Wert erzeugt 
- Formel muss öffentlich sein(andere müssen diese ausprobieren können)
- Muss eine Einwegfunktion sein

### Asynchrone Verschlüsselung / Public Key Verschlüsselung 
1. Digitale Signaturen (Authentizität)   
2. Verschlüsselung an sich (Privacy)  

Bitte beschreiben Sie ein Szenario welches typisch ist für die Kombination aus 1 & 2 im Detail.
Versenden von Datein
- Signatur um sicherzsutellen, dass ich immer als Author des Dokuments feststehe
- Verschlüsselung um meine Datei nicht für jeden im Internet zugänglich zu machen, sondenr nur der Person der ich die Datei schicke

Inwiefern spielen digitale Signaturen bei Cryptowährungen wie Bitcoin & Ether eine wesentliche Rolle?  
- Integrität der Chain
- Jeder Signiert seine eigene Transaktion

Beschreiben Sie ein Szenario, in welchem Alice an Bob eine vertrauliche Nachricht senden möchte und Bob sicher sein möchte, dass die Nachricht tatsächlich von Alice kommt. Hilfestellung: Was wird wann mit welchem Key verschlüsselt / entschlüsselt? 
1. Alice bittet Bob darum ihm Geld auf ein bestimmtes Konto zu überwisen, um Konzertkarten für beide zu kaufen 
2. Um die digitale signatur durchzuführen, verschlüsselt Alice ihren Text mit ihrem privaten Key. Daurch die verwendeung von Alice public key kann dieser nun wieder entschlüsselt werden, bzw. Danach kann Alice die Nachricht mit Bobs Upblic Key zusätzlich verschlüsseln, um die NAchricht nur für Bob zugänglich zu machen

### Datenstrukturen 
#### Bloomfilter


Angenommen Sie nutzen einen Bloomfilter mit einem Bitset der Länge 11 mit den Bloombits 0 bis 10 sowie den folgenden Einwegfunktionen zur Belegung der Bits:  
h1(x)=(x * 2)%11  
h2(x)=(x * 3)%11  
h3(x)=(x * 4)%11  

Wie sieht das Bitset jeweils nach dem Hinzufügen der folgenden Zahlen aus?  
const exampleArray = [2, 5, 6]

--> Bitset nach dem Hinzufügen der 2:  (0,0,0,0,1,0,1,0,1,0,0)                                         

--> Bitset nach dem Hinzufügen der 5:  (0,0,0,0,1,0,1,0,1,1,1)

--> Bitset nach dem Hinzufügen der 6:  (0,1,1,0,1,0,1,1,1,1,1)
    	                                   

Würde der Bloomfilter für die folgenden Zahlen false positives liefern?  
const entriesToBeValidated = [3, 34]  
Für 3 : (0,1,0,0,0,0,1,0,0,1,0) -> PERHAPS
11: 2,3,3  -> NO

Lösungscheck siehe https://deno.land/x/bloomfilter@v2.2.0#custom-hash-functions  

Welche Vor- und Nachteile hat die Erhöhung der Anzahl an Bits im Bitset & welche Vor- und Nachteile hat die Erhöhung der Anzahl an genutzten Hash Funktionen bei Bloomfilters im Allgemeinen. Warum ist das so?  
(https://hur.st/bloomfilter/?n=100000&p=0.6&m=&k=1)
- Mehr Bits führen dazu, dass es zu weniger Kollisionen kommt, also das zwei Inputs den gleichen Output erzeugen
- Mehr Hash bedeutet mehr Aufwand (mehr Rechenzeit)
- rneut eine höhere Kollisionsresistenz

Bitte erläutern Sie mindestens einen Anwendungsfall von Bloomfilters.    
- Überprüfen ob ein Benutzername schon vergeben ist, oder ob dieser noch Frei ist (Rückgabe der Funktion ist dann "Nein, der Name ist noch nicht vergeben" oder "Name ist vllt. vergeben)

#### Merkletrees
Bitte erstellen Sie einen Merkletree für die Einträge im untenstehenden Beispiel Array unter Nutzung der darunter stehenden Einwegfunktion:   
const exampleArray = [2,7,8,1]  
h(x)=(x * 2)%10  

h(leafNode1)=  4
h(leafNode2)=  4
h(leafNode3)=  6
h(leafNode4)=  2

h(lN12)=  h(44) = 8
h(lN34)=  h(62) = 4
 
h(root)=  h(84) = 6
  
Angenommen jemand behauptet im Beispielarray wäre eine 9 (anstelle der 1) enthalten. Welche Nodes innerhalb des MerkleTrees würden sich dadurch wie ändern?
Lösungscheck siehe merkletrees deno modul.
- leafnode4, h(lN34), h(root)

Bitte erläutern Sie mindestens einen Anwendungsfall von Merkletrees. 
- Bitcoin, um sicherzustellen, dass die Blöcke die gerade gemint werden auch validiert werden können

Wie werden Merkle Trees im Kontext von Kryptowährungen eingesetzt?
- Bitcoin, sicherstellen der Integrität der Blöcke
- (Teil-)Validierung: Es müssen nicht alle Werte gesendet werden, sondern es reicht aus die leafnodes zu erhalten, mit denen ich die zu testenden Werte konkatenieren muss
- 

#### Tries
https://deno.land/x/tries   

Bitte skizzieren Sie einen klassischen Trie sowie einen PATRICIA Trie für die folgenden Buchstabensequenzen: 
ape, apple, organ, organism


<img width="1344" alt="Screenshot 2022-01-20 at 21 46 51" src="https://user-images.githubusercontent.com/43786652/150440646-71d5f137-ab8e-4d42-905d-3dff469827b2.png">



### Konsensalgorithmen 

Bitte erläutern Sie die Notwendigkeit von Konsensalgorithmen in einem verteilten System wie z.B. der Ethereum Blockchain.  
- PoW, PoS
- Methode um alle Partein davon zu überzeugen, das die Blöcke die veröffentlicht werden der Wahrheit entsprechen

Was ist das Kernprinzip hinter Proof of Work?  
- Alle Miner versuchen einen passenden (16 Nuller zu beginn) root Hash zu finden, der den Block beschreibt. Nur einer bekommt den Zuschlag, Wahrscheinlichkeit pro Recheneinheit ist für alle gleich 

Was ist das Kernprinzip hinter Proof of Stake?  
- Nur einer bekommt zuschlag, abhängig von der ANzahl der Währung die eingesetzt werden (Stake), je mehr, desto mehr validierungen kann man durchführen
- Für die Validierung muss im Stake mehr Etherium sein als durch den Block gegeben sein
- Durch eine gewisse zufallsauswahl kann die Verteilung auf die Nutzer gleichmäßiger verteilt werden

Bitte erläutern Sie wie ein "51% Angriff" auf die Bitcoin Blockchain gestaltet werden könnte und wie ein potentieller Angreifer davon beispielsweise profitieren könnte. 
- Ich benötige 51% der Validierungspower und kann damit auch Falsche Blöcke als richtig validieren. Durch das Shorten des Bitcoin wäre es dann möglich bei bekanntgabe des    Problems viel Geld zu verdienen
- Publizieren einer Abfolge von Blöcken die länger ist als alle anderen: man glaubt immer der längeren Kette 
- Double Spending Möglichkeit durch die KOntrolle des Netzwerkes
- Zensur der Blockchain möglich

Was ist eine 51%-Attacke und wie unterscheiden sie sich bei unterschiedlichen Blockchain-Technologien (PoW, PoS)?
Musterlösungen laut Kommilitonen: https://github.com/michael-spengler/digitale-waehrungen-wwi19seb/pull/14/files - bitte stets kritisch prüfen. 
- Bei PoW benötige ich nur 51% der Minigpower
- Bei PoS benötige ich 51% der Coins im Stack

Jemand behauptet dass die Ethereum Blockchain eine Stromverschwendung darstellt und viele der Anwendungen lieber zentral auf einem Server laufen sollten, um Strom zu sparen. Was sagen Sie? 
- das ist falsch weil PoS verwendet wird und somit nur wenig Strom tatsächlich benötigt wird
- Die verteilte Speicherung der Daten hat den Vorteil, dass keine Zentrale Schnittstelle besteht und somit mehr Demokratie ermöglicht wird
- Kein Vertrauen
- Kein Einfrieren von Vermögen
- Keine Transaktionseinschränkungen
- Anonymität
- Kosten für Mittelsmänner fallen weg (Transaktionskosten instead)
- Limitation der Währung (Pro und Contra)


## Anwendungsgebiete der Blockchaintechnologie
### Digitale Währungen 
Was sind für Sie die Hauptunterschiede zwischen einer Central Bank Digital Currency und einer Cryptowährung wie Ether? Was halten Sie von der potentiellen Einführung von Central Bank Digital Currencies? (ca. 7 Sätze)
-CBCB: 

-   Keine Absicherung der Währung durch Materielle Güter bei beiden Währung, Währungsstabilität
-   Zentrale instanz besteht
-   überwachte und gelenkte Währung
-       schnellere Transaktionen
-       Kriminalität kann eingeschränkt werden (Überwachen der Transaktionen)
-       z.B. Geld wäsche 
-       Totale Überwachung des States 
-       Anonymität
-       Beschränkung des CBDCs in anderen Ländern (Digitale Euro in China)   
-       Direkten Zugang zur EZB möglich, Mittelsmann fällt weg      
-  Ich sehe es 

Was halten Sie davon, dass Richard Nixon 1971 den Goldstandard aufgehoben hat? Warum?   
- Auf der einen Seite hat der Dollar damit außer dem Wert dem wir ihm selber zuweisen keine bedeutung mehr und ist papier
- Andererseits war es damit möglich, ein Wirtschaftwachstum in den letzen zu ermöglich welches im Vergleich zu den Jahren zuvor nicht möglich gewesen wäre 
- Dreist weil es so nicht besprochen war nach dem zweiten Weltkrieg

Der folgende SC soll eine Währung namens QuinoaCoin mit den folgenden Eigenschafte definieren:  
1. Nachkommastellen: 18
2. Gesamtzahl an Tokens (fixed supply): 2000000

Bitte streichen Sie fehlerhafte Zeilen und ersetzen Sie diese durch korrekte Anweisungen:   

```sol
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.8.0 < 0.9.0;

import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v4.4/contracts/token/ERC20/ERC20.sol";


contract QuinoaCoin is ERC20 { 


    constructor () ERC20("QuinoaCoin", "QNC") { 
        _mint(msg.sender, 2000*10**17);   
    }
    
}
```

Hat eine Währung wie Bitcoin mit einem fixed / max. supply von 21.000.000 aus Ihrer Sicht eher eine inflationäre oder eine deflationäre Tendenz. Bitte erläutern Sie kurz ihre Einschätzung.
- deflationär, weil der Wohlstand auf der Welt mit der ZEit zunimmt, aber die Anzahl der Bitcoins ja beschränkt ist, sodass der Bitcoin mit der Zeit an Wert zulegen wird (Kein Einbezihen von Spekulationen durch den AKtienmarkt)

Inwiefern könnte der Zeitraum der Veröffentlichung des Bitcoin Whitepapers (31.10.2008 in einer Kryptographie-Mailingliste der Cypherpunks) und der Zeitraum der globalen Finanzkrise 2008 miteinander zusammenhängen?
- Aus meiner Sicht gar nicht, Lehman Brothers wussten wahrscheinlich nichts davon und die Finanzkrise war durch das schlechte Haushalten der Jahre zuvor entstanden. Zu Anfang hat das Bitcoin Whitepapers auch noch keine Große bedeutung gehabt


### Decentralized Finance
Stichworte: Smart Contract based Lending, Borrowing, Yield Farming, Zahlungsverkehr, Investing
Was verstehen Sie unter dem Begriff DeFi? Wie wahrscheinlich ist es aus Ihrer Sicht, dass dieser Ansatz insgesamt an Bedeutung gewinnt? Warum?
- SC based Lending:
 - Leihen und Verleihen von Wähurng zwischen den Nutzern
    - Geld in einen Pool einzahlen und dann mit Smart Contract auf die Lieher warten
    - Sicherheiten müssen hinterlegt werden (100% Coins bekomme ich 75% Kredit) 
- Yield Farmin:
    - Verleihen von Geld
- Aave, Compound

### Decentralized Governance 
Stichwort: DAO  (Dezentralised Autonomus Orgaistation Rechtsform)
Alle User treffen die Entscheidungen zusammen
Votingpower hängt z.B. von der Anzahl der gesammelten governance tokens ab... 
https://github.com/distributed-ledger-technology/airdrop

### Decentralized Web
Permanent Deployment / Censorship resistant deployment
Distributed Deployments / File Servers --> IPFS & DDNS- see https://ens.domains  

Beschreiben Sie ein Szenario, in welchem Sie eine dApp anstelle einer klassischen web app implementieren würden.
- Ausnutzen der Censorship resistenz und beispielsweise WikiLeaks damit entwickeln

Welche Browserextension können Sie z.B. für google chrome nutzen, damit Besucher Ihrer dApp mit Smart Constracts der Ethereum Blockchain interagieren können? Bitte nennen Sie eine alternative zu dieser Browserextension.
- Binance, Sollet, Metamask


### Kunst / Collectibles / GamingAssets - Non Fungible (ERC721) & Semi Fungible (ERC1155) Tokens 
- NFTs ist die Kunst
- SFTs können Gutscheine oder Eintrittskarten sein

## Smart Contracts
Bitte beschreiben Sie das Wesen eines Smart Contracts. Inwiefern kann ein Smart Contract als smarte Vereinbarung bezeichnet werden?
- Automatische Ausführiung ohne das eine dritte Person agieren oder einbezogen werden muss
- Nicht veränderbar 
- smarte Vereinbarung, weil es sich um ein Computerprogramm handelt, welches die Vertragseigenschaften festhält

## Wallets
Vergleichen Sie Custodial Wallets vs. Non-Custodial Wallets und nenne Sie dabei mindestens ein Beispiel für ein non-custodial wallet.
- Custodial sind von einer Plattform verwaltet wir COinbase (Private Key nicht verloren gehen (Sicherheit), keinen Zugriff auf den eigenen Private Key)
- Non-Custodial verwalte ich selber und kann ihn mir ausdrucken, kein Institut dazwischen, bei Verlust ist das Geld weg
- MyEtherWallet 

Vergleichen Sie Paperwallets und Browserwallets? In welchem der beiden würden Sie eher eine sehr große Summe an Ether speichern? Warum?
- Paperwallets sind ausgedruckt (damit schwieriger zu klauen, aber auch zu handhaben)
- Browserwallets sind einfacher zu manipulieren(Können gehackt werden) ermöglichen aber auch eine einfachere Handhabung der Assets (kann schwieriger verloren gehen
- Kommt auf die verwendung an, wenn ich viel Trade damit dann eher auf Browserwallet (Besser zu handhaben)
- Paperwallets wenn ich das Geld tatsächlich für lange Zeit anlegen möchte weil es sicherer ist und ich das, wenn ich motiviert bin auch im Wald verbudeln kann und eine Schatzkarte zeichen kann

## Stable Coins
Was verstehen Sie unter einem Stable Coin? Auf welche Arten können Stable Coins implementiert werden? Kennen Sie Beispiele?
- Bilden den Wert einer Währung(wie den Doller) ab (Ein Beispiel ist der Gemini Dollar oder Tether )
1. Absicherung durch klassische Assets (dollar halten, GOld auch möglich)
2. Absicherung durch Kryptowährungen (hohe schwankung der Sicherheit möglich)
3. Algorithmische Absicherung (Algo gibt neue Coins in Markt oder nimmst siw wieder heraus (Aktuell noch vollatiler als die anderen)


## Exchanges / Börsen
Was sind für Sie Unterschiede zwischen zentralen Exchanges (e.b. binance.com, coinbase.com etc.) und dezentralen Exchanges (e.g. uniswap.org)? 
- Zentrale:
    - das Unternehmen behält über alle Transaktionen die verantwortung und uberwacht diese

- Dezentral:
    - Kontrolle über geld behalten
    - Die Transaktionen sind in der Blockchain gespeichert – auf eine transparente und manipulationssichere Weise. Intermediäre sind nicht erforderlich, die Handelsbeziehungen finden Peer-to-Peer und damit direkt zwischen den Teilnehmern der Plattform statt

## On-Chain / Off-Chain Verbindungen
Example: https://deno.land/x/airdrop@v0.1.0/example-airdrops/launch-airdrop-for-wwi19seb.ts ... via TypeScript programm
Application Binary Interfaces Usage Example: https://deno.land/x/airdrop@v0.1.0/src/airdrop-service.ts#L16 ... um eine Repräsentation des Smart Contracts (der z.B. auf der Ethereum Blockchain deployed ist) im TypeScript Programm zu erhalten und damit Funktionen dieses Smart Contracts vom TypeScript Programm aus zu triggern.
- 

## Mining
Wofür steht die Abkürzung "ASIC" im Bezug auf Mininghardware?  
[ ] Application Specific Integrated Circuit  (X)
[ ] Asset Specific Integrated Circuit   
[ ] Altcoin Specific Integrated Circuit  
[ ] Application Specific Initial Coin  

## Airdrops
Warum werden AirDrops durchgeführt? (Multiple Choice)
- [x] Early Adopters belohnen
- [x] Voting Power verteilen
- [ ] Währung deployen
- [ ] Denial of Service Angriffe durchführen


## Layer 2 Scaling
Inwiefern könnte Arbitrum die Adoption der Ethereum Technologie beschleunigen?   
- Sind günstiger
- schnellere Transaktionen

### Implementierungen
#### TypeScript
https://deno.land/x/airdrop@v0.1.0/example-abis/ropsten-0x7910f84868488da3377833ccaa0e5b2b42edd9a6.ts


Welche Informationen und Module benötigen Sie wenn Sie einen Airdrop für Ihre Early Adopters gestalten möchten, welchen Sie über ein TypeScript Programm lancieren?

1. Empfänger Wallet Adressen
2. ABI
3. https://deno.land/x/web3
4. provider url (e.g. von infura.io oder zu einer eigenen Ethereum node,...)



## Eigeninitiative / Eigeninteresse
Describe you own favorite topic wrt. the Blockchain space (... wissenschaftlich / educational ... ) (4 Punkte)    
- Web3 ist aus meiner Sicht der nächste Schritt des Internets, es ist zwar für anfänger Schwierif die Seiten afzurufen n aber die Daten liegen sicherer ab und werden nicht mehr Zentral verwaltet, außerdem ist es möglich, die Macht der großen Konzerne zu brechen (EU hat vor kurzem ein gesetzt Herausgebracht, welches die Unternehmen dazu verpflichet ihre Algos offen zu legen). Es ist OpenSource sodass jeder mitarbeiten kann
- Besser entscheiden was will ich was nicht (Nicht mehr vorgeschrieben







# Tipp
Erledigt in der Klausur zunächst die Aufgaben, welche Ihr von Eurem individuellen Flow her zügig erledigen könnt und macht Euch danach an die Aufgaben, welche etwas mehr Zeit / Geduld oder gar Kreativität beanspruchen. 





