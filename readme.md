## Anonüümsed funktsioonid ja Stream API

Tõstke kõik failid, mis on kataloogis src/fp oma 
Bitbucket-i reposse (icd0019) kataloogi src/fp.

Veenduge, et kood kompileerub.

Kui valite Idea-s Build menüüst -> Rebuild project peaks tulema teade 
"Compilation completed successfully ..."

1. Klassis fp.Filter on meetod filter(), mis peaks sisse antud listist 
   filtreerima välja elemendid, mis vastavad etteantud tingimusele.
   
   Kirjutage see meetod lõpuni tavalise tsükli abil ilma Stream API võimalusi 
   kasutamata. Eesmärk on operatsiooni tööpõhimõttest arusaamine.
   
   Koodi testimiseks on test samas klassis.

2. Klassis fp.Map on meetod map(), mis peaks sisse antud listi
   elemente transformeerima etteantud reegli kohaselt.
   
   Kirjutage see meetod lõpuni tavalise tsükli abil ilma Stream API võimalusi 
   kasutamata. Eesmärk on operatsiooni tööpõhimõttest arusaamine.
   
   Koodi testimiseks on test samas klassis.

3. Klassis fp.Reduce on meetod reduce(), mis võtab sisse listi ja operatsiooni, 
   mis peaks teisendama (redutseerima) listi üksikuks väärtuseks.
   
   Kui sisse antud list on tühi, siis peaks meetod erindi viskama.
   
   Kirjutage see meetod lõpuni tavalise tsükli abil ilma Stream API võimalusi 
   kasutamata. Eesmärk on operatsiooni tööpõhimõttest arusaamine.
   
   Operatsioon peab sisendiks võtma kaks väärtust ja tagastama ühe väärtuse.
   
   Näiteks:
   
   Kui list on ```[1, 2, 3]``` ja operatsioon on liitmine, siis peaks 
   tulemus olema ```((1 + 2) + 3) = 6```.
   
   Kui list on ```[1, 2, 4, 6]``` ja operatsioon on korrutamine, siis peaks 
   tulemus olema ```(((1 * 2) * 4) * 6) = 48```.
   
   Muutke meetodit nii, et sellega oleks võimalik redutseerida ka list
   ```["1", "2", "3"]``` väärtuseks "123".

4. Klassis fp.Timer on meetod executeAndTime(), mis peaks sisse võtma 
   koodi, mida käivitada, selle koodi käivitama ja väljastama tulemuse, 
   kui palju käivitamine aega võttis.
   
   Aja mõõtmise kohta on näide samas klassis meetodi measureExecutionTimeExample().
   
   Käivitatava koodi parameetrina saatmise näide on klassis fp.examples.AssertThrows.

5. Klassis fp.WithResource on meetod withResource(), mis peaks võimaldama,
   klassi Resource kasutamist kontrollitud kujul.

   Ülesandes on kasutatud klassi Resource, mille ülesanne on simuleerida 
   mingi reaalse ressursi käitumist. Praktikas võiks selleks ressursiks 
   olla nt. fail, andmebaas, mõni rakendus või mistahes asi, millega suhtlus 
   peaks toimuma kindlate reeglite alusel. Antud näites on reegliks see, 
   et ressurss tuleb enne kasutamist avada ja pärast sulgeda.

   Soovime saavutada seda, et kasutaja ei peaks ise ressursi avamisele ja 
   sulgemisele mõtlema ja seega oleks vigade tekkimise võimalus väiksem.

   Soovitud käitumist kirjeldab samas failis olev test.
   
   Kirjutage lõpuni meetod withResource().

6. Klassis fp.Numbers on list numbritest. Kasutades Stream API võimalusi

   * leidke nende hulgast paaritud arvud;
   * leidke paaritud arvud, mis on suuremad kui 10;
   * leidke paaritute arvude, ruudud;
   * leidke paaritute arvude, summa.
   
7. Klassis fp.Persons on list isikutest. Kasutades Stream API võimalusi

   * leidke nende hulgast isik, kelle id on 2;
   * eemaldage isik, kelle id on 2;
   * leidke isikute nimed ja väljastage need komaga ühendatud sõnena 
     ("Alice, Bob, Carol");
   * sorteerige isikud vanuse järjekorras kahanevalt.

8. Klassis fp.averages.Main kood, mis loeb teksti failist andmed. Andmeteks
   on numbrite listide list (List<List<Integer>>).

   Kirjutage kood, mis leiab kõige arvude keskmise väärtuse.   
   
9. Paketis fp.examples on näide erinevatest Stream API operatsioonidest.

   Vaadake need näited üle ja veenduge, et saate aru, kuidas need töötavad.
   
   Näidetes olevad operatsioonid on täiesti piisavad koduse ülesande lahendamiseks.

10. NB! Selle ülesande koodis ei tohiks olla ühtki tavalist tsüklit (for, while).
   
    Failis src/fp/sales/sales-data.csv on andmed müügi kohta. Kasutades 
    Stream API võimalusi leidke
    
    * kogu müük;
    * müük kategoorias "Office Supplies";
    * müük vahemikul 2024-01-01 kuni 2024-03-31;
    * kolme kallima toote id-d tähestiku järjekorras;
    * kolm suurima müügiga osariiki.
    * kõige *kasumlikumad tooted
    
    \* Kõige kasumlikum toode on see, mille müügist teenitud kasum on suurim.
      Juurdehindluse saate meetodiga AccountingService.getProfitMargin().     
    
    Faili lugemiseks on:
      
      ```Files.readAllLines(Paths.get(FILE_PATH));```
      
    Kirjed on eraldatud tabulaatoriga ja need saab osadeks nii:
    
      ```line.split("\t");```
      
    Sõnest saate kuupäeva nii:
    
    ```
      DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd.MM.yyyy");
      LocalDate.parse(<kuupäev stringina>, formatter);   
    ```
    
    Selle ülesande koha on ka koodi ülevaatuse võimalus. Kui esitate lahenduse 
    tähtajaks, siis tähtaja möödudes on teil võimalik kellegi teise tudengi 
    tööd hinnata ja selle eest punkte saada. 
    
    Ülevaatuse leiate pärast tähtaja möödumist hindamisüsteemist ja selle 
    esitamiseks on aega 7 päeva.
    
    Ülevaatusel tuleb vastata ühele küsimusele.
      - Kas koodis on kasutatud tavalist tsüklit (for, while)?
    
    Aadressil https://github.com/mkalmo2/icd0019app on rakendus, mis illustreerib,
    kuidas loodud koodi praktikas kasutada. Rakenduse kasutamiseks kopeerige
    oma kood icd0019app projekti ja käivitage main() meetod klassis server.Server.
    See käivitab lokaalse veebiserveri aadressil http://localhost:8080.
    Sellelt aadressilt saate läbi brauseri tulemust vaadata.
    
11. Commit-ige muudatused ja push-ige need Github'i. 
   
    Lisage commit-ile tag ex09.
    
    Veenduge tulemuste lehelt, et tulemus on positiivne.

Lahendused (1-8), seletused (9, 10): https://youtu.be/uNnqqRUo8Og