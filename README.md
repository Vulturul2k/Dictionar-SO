# Dictionar-SO

### ASID (Address Space ID)
este un identificator unic utilizat pentru a identifica un spațiu de adresare alocat unui proces într-un sistem de operare.

Un spațiu de adresare este un set de adrese virtuale alocate unui proces care reprezintă memorie virtuală asociată procesului. ASID-ul este utilizat pentru a distinge între diferitele spații de adresare ale proceselor în sistemul de operare și pentru a gestiona acestea în mod eficient.

ASID-ul este alocat de sistemul de operare la crearea unui spațiu de adresare pentru un proces și este utilizat de hardwareul sistemului pentru a identifica și accesa memorie virtuală alocată procesului.

În unele sisteme de operare, cum ar fi sistemele cu arhitecturi ARM, ASID-ul este utilizat împreună cu TLB (Translation Lookaside Buffer) pentru a gestiona eficient cache-ul memoriei virtuale și pentru a reduce overhead-ul sistemului.

### COW (Copy-On-Write)
este o tehnologie utilizată în sistemele de operare pentru a gestiona alocarea memoriei.

În sistemele de operare care utilizează COW, atunci când două sau mai multe procese încearcă să acceseze aceeași zonă de memorie, inițial nu se face o copie a acesteia. În loc de aceasta, toți procesele accesează aceeași zonă de memorie, împărțind-o între ele.

Dar, dacă unul dintre procese încearcă să modifice conținutul zonei de memorie, sistemul de operare alocă automat o copie a acestei zone și fiecare proces primește propria sa copie a zonei de memorie, care poate fi modificată fără a afecta celelalte procese.

COW este utilizat pentru a optimiza alocarea memoriei și a îmbunătăți performanța sistemului, deoarece permite sistemului de operare să împartă eficient zona de memorie între mai multe procese, fără a fi necesară alocarea unor copii suplimentare a acestei zone. În același timp, dacă un proces are nevoie să modifice această zonă de memorie, acesta primește propria sa copie, fără a afecta celelalte procese.

### Eterogen
Thread-urile procesului fac chestii diferite

### FDT sau Flattened Device Tree (Arbore de dispozitive aplanat)
este o reprezentare a configurației hardware a unui sistem, utilizat în sistemele bazate pe kernel-ul Linux. FDT descrie dispozitivele și componentele hardware dintr-un sistem într-un format de fișier care poate fi interpretat de sistemul de operare.

FDT permite sistemului de operare să determine configurația hardware a unui sistem și să se configureze astfel încât să funcționeze cu această configurație. De exemplu, sistemul poate determina dacă există dispozitive specifice (cum ar fi placa de rețea sau unitatea de disc) sau dacă există anumite resurse hardware limitate (cum ar fi memorie sau CPU) și poate lua măsuri pentru a gestiona acestea în consecință.

FDT este utilizat în principal în sistemele embedded și de server, unde este important să se poată detecta configurația hardware la pornire și să se poată adapta la aceasta în timpul execuției.

### Heap-ul
este o structură de date utilizată în programare pentru a gestiona alocarea dinamică a memoriei.

În majoritatea sistemelor de operare, există două zone principale de memorie: stiva și heap-ul. Stiva este utilizată pentru a stoca variabile locale și informații despre apelurile de funcții, în timp ce heap-ul este utilizat pentru a gestiona alocarea dinamică a memoriei.

Atunci când un program are nevoie de mai multă memorie decât cea alocată prin variabilele locale din stivă, el poate solicita alocarea de memorie din heap prin intermediul unei apeluri la funcții precum malloc sau new. Sistemul de operare alocă o zonă de memorie din heap și returnează un pointer către această zonă. Programul poate accesa și modifica acum această zonă de memorie, până când nu mai are nevoie de ea. În acest caz, poate apela funcția free sau delete pentru a elibera memoria din heap.

Heap-ul este important pentru programare, deoarece permite programelor să aloce dinamic memorie în funcție de necesitățile lor în timpul execuției, îmbunătățind astfel flexibilitatea și performanța programelor.

### Loader-ul
este un program care încarcă un alt program în memorie pentru a fi executat. Rolul principal al unui loader este de a aloca memorie pentru a încărca și de a inițializa programul și de a configura mediul de execuție înainte de a începe execuția propriu-zisă.

Acest proces include:

Verificarea și validarea fișierelor binare
Încărcarea secțiunilor programului (cum ar fi text, data, rodata, etc.) în memorie
Setarea legăturilor dinamice (cum ar fi referințele la biblioteci externe)
Configurarea parametrilor de intrare și a mediului de execuție (cum ar fi setarea variabilelor de mediu, a permisiunilor, etc.)
Începerea execuției programului, asigurând că totul este pregătit și configurat corect
Un loader joacă un rol crucial în execuția unui program și poate avea un impact semnificativ asupra performanței și securității sistemului.

### Mutex-urile
sunt o formă de sincronizare care funcționează prin context switch, și ocazional apel de sistem (chemarea scheduler-ului la lock() și unlock). Sunt folosite în toate celelalte cazuri în care spinlock-ul nu este viabil: apeluri blocante, zone critice mari

### Omogen
Thread-urile aplicatiei fac aceelasi lucru

### Pipe-ul
este un mecanism de comunicare între procese care permite transmisia datelor într-un singur sens, de la un proces la un altul.

Pipe-urile sunt utilizate pentru a permite proceselor să se comunice prin intermediul sistemului de fișiere, fără a folosi fișiere sau socket-uri. Datele sunt scrise într-un capăt al pipe-ului de un proces și citite din celălalt capăt de un alt proces.

Pipe-urile sunt folosite frecvent pentru a transmite date între procese care rulează în paralel sau pentru a implementa mecanisme de redirectionare a intrării și a ieșirii în shell-uri sau alte programe de linie de comandă.

### PTBR (Page Table Base Register)
este un registru special în procesor care stochează adresa bazei tabelului de pagini utilizată în sistemele de operare care folosesc memorie virtuală.

În sistemele de operare cu memorie virtuală, fiecare proces are propria sa tabelă de pagini, care conține informații despre maparea dintre adresele virtuale utilizate de proces și adresele fizice din memorie. PTBR conține adresa bazei acestei tabele, care este utilizată de procesor pentru a accesa informațiile din tabelă când un proces accesează o adresă virtuală.

### Seek
este o operație de sistem de fișiere care permite poziționarea unui indicator de citire/scriere într-un fișier. Când se apelă o operație seek, indicatorul de citire/scriere este mutat la o nouă poziție în fișier, astfel încât următoarea operație de citire sau scriere să se facă de la acea poziție. Seek-ul poate fi utilizat pentru a naviga într-un fișier mare sau pentru a citi sau scrie fragmente specifice din fișier.

### Spinlock-urile
sunt o formă de busy waiting în starea de RUNNING. Ele nu determină ieșirea de pe procesor a thread-ului care așteaptă. Sunt folosite atunci când timpul de așteptare nu este mare (zone critice mici, fără apeluri blocante), iar un context switch este mai costisitor în comparație.

### Swap memory sau swap space
este o zonă de memorie secundară utilizată de sistemul de operare pentru a gestiona resursele de memorie fizică. Când sistemul de operare are nevoie de mai multă memorie decât cea disponibilă în RAM, el poate muta pagini din RAM în swap memory pentru a elibera spațiu în RAM pentru alte procese care au nevoie de memorie.

Swap memory poate fi implementat ca un fișier sau ca un partiție de disc. Când sistemul de operare mută pagini din RAM în swap memory, acestea pot fi recuperate în RAM când devin necesare în viitor.

Utilizarea swap memory poate ajuta sistemul de operare să gestioneze resursele de memorie mai eficient, dar poate avea un impact negativ asupra performanței sistemului, deoarece accesul la swap memory este mai lent decât accesul la RAM. De aceea, este recomandat să aveți suficientă memorie RAM disponibilă pentru a evita utilizarea prea des a swap memory.

### TCB sau Task Control Block
este o structură de date utilizată de sistemele de operare pentru a gestiona fiecare proces sau thread care rulează în sistem. TCB conține informații despre proces sau thread, cum ar fi identificatorul de proces (PID), status-ul de execuție, contextul procesului (informații despre stiva, registrii CPU, etc.), informații despre alocarea resurselor (memorie, CPU, fișiere deschise, etc.) și alte informații specifice.

Informațiile din TCB sunt utilizate de sistemul de operare pentru a controla și gestiona procesele și thread-urile în sistem. De exemplu, atunci când un proces solicită o resursă, sistemul de operare consultă TCB pentru a determina dacă procesul are acces la resursa respectivă. De asemenea, sistemul de operare poate utiliza informațiile din TCB pentru a gestiona și plasa procesele pe CPU pentru a optimiza utilizarea resurselor.

TCB este o parte importantă a gestionării proceselor în sistemele de operare moderne și contribuie la organizarea și controlul eficient al resurselor și proceselor în sistem.

### TLB (Translation Lookaside Buffer)
este un cache hardware utilizat în sistemele de operare pentru a îmbunătăți performanța în accesarea memoriei virtuale.

În sistemele de operare care utilizează memorie virtuală, adresele virtuale utilizate de procese trebuie să fie translate în adrese fizice înainte de a fi accesate în memorie. Acest proces de traducere poate fi costisitor din punct de vedere al performanței, astfel încât TLB-ul este utilizat pentru a stoca informații despre traducerile recente între adresele virtuale și fizice.

Când un proces accesează o adresă virtuală, sistemul de operare verifică întâi TLB-ul pentru a vedea dacă există o traducere valabilă pentru acea adresă virtuală. Dacă există, sistemul de operare accesează direct adresa fizică corespunzătoare, evitând astfel procesul de traducere costisitor.

TLB-ul ajută la îmbunătățirea performanței sistemului prin reducerea numărului de traduceri necesare pentru accesarea memoriei virtuale și prin accelerarea accesului la această memorie.

### TOCTOU (time of check to time of use)

Se referă la un race condition care apare imediat după un compare, înainte de a se face instrucțiunea următoare (de folosire), când un alt thread apare și modifică valoarea considerată "safe".