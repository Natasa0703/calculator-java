Analiza je izvršena nad svim .java fajlovima u projektu.

Calculator.java: 188 lines (134 loc)

Start.java: 26 lines (19 loc)

Ukupan LOC za ceo projekat: 214 lines (153 loc)


Neformalan pregled koda

Calculator.java – linija 5 – Korišćenje statičke promenljive finalResult može dovesti do problema pri ponovljenim ili paralelnim pozivima metode za izračunavanje izraza.

Calculator.java – linija 21 – Metoda ToString ne poštuje Java konvenciju imenovanja metoda, jer bi trebalo da se zove toString.

Calculator.java – linija 35 – Ne postoji provera da li je ulazni string prazan pre poziva expression.charAt(0), što može izazvati izuzetak.

Calculator.java – linija 45 – Metoda Operations.ToString() vraća niz operacija bez jasnog redosleda prioriteta, što može otežati razumevanje koda.

Calculator.java – linija 62 – Hvatanje opšteg Exception umesto specifične greške smanjuje čitljivost i otežava dijagnostiku problema.

Calculator.java – linija 76 – Rekurzivna metoda Calculate nema zaštitu od prevelike dubine rekurzije, što može dovesti do greške pri izvršavanju.

Calculator.java – linija 89 – Postoji velika količina ponovljenog koda za različite aritmetičke operacije, što otežava održavanje i proširivanje koda.

Calculator.java – linija 115 – Promenljiva result se koristi u više grana bez jasnog resetovanja vrednosti, što može izazvati greške u računanju.

Start.java – linija 9 – Naziv promenljive Expression ne poštuje Java konvenciju imenovanja promenljivih.

Start.java – linija 12 – Objekat Scanner se kreira unutar while petlje, što je neefikasno i nepotrebno.

Start.java – linija 18 – Zatvaranje Scanner objekta unutar petlje može izazvati probleme pri daljem korišćenju standardnog ulaza.



Statička analiza koda (Lint analiza)

Statička analiza koda je obavljena korišćenjem principa lint alata SonarLint i Checkstyle plugina u Eclipse-u, sa ciljem pronalaženja nedoslednosti, potencijalnih grešaka i code smell-ova, bez pokretanja aplikacije.

Zapažanja

Calculator.java – linija 5 – Statička promenljiva finalResult predstavlja globalno stanje i može izazvati neželjeno ponašanje u slučaju višestrukih poziva metode.

Calculator.java – linija 21 – Naziv metode ToString krši Java naming konvenciju i može zbuniti alat za statičku analizu.

Calculator.java – linija 35 – Nedostaje validacija ulaznog parametra pre pristupa indeksu stringa, što predstavlja potencijalni runtime problem.

Calculator.java – linija 62 – Hvatanje opšteg Exception je loša praksa prema lint pravilima i trebalo bi koristiti specifične izuzetke.

Calculator.java – linija 76 – Rekurzivna metoda Calculate je kompleksna i duga, što predstavlja code smell prema pravilima o čitljivosti i održavanju koda.

Calculator.java – linija 89 – Prisutna je značajna količina dupliranog koda za obradu aritmetičkih operacija, što lint alati označavaju kao maintainability issue.

Calculator.java – linija 103 – Metoda Calculate ima previše odgovornosti (računanje, upravljanje listama, kontrolu prioriteta), što ukazuje na loš dizajn.

Start.java – linija 9 – Naziv promenljive Expression ne poštuje camelCase konvenciju i označava se kao style issue.

Start.java – linija 12 – Kreiranje Scanner objekta unutar petlje predstavlja performance code smell.

Start.java – linija 18 – Zatvaranje Scanner objekta koji koristi System.in se označava kao potencijalni problem u radu sa resursima.
