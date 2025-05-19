Simulati un sistem de management al utilizatorilor prin 3 functionalitati principale:

Inregistrarea unor utilizatori noi:
- presupune verificarea existentei unui utilizator cu acelasi nume, caz in care inregistrarea nu se efectueaza si se afiseaza un mesaj correspunzator
  pentru utilizatorii noi, se solicita detalii precum: adresa email, parola (parola nu va fi stocata in clar ci criptata - hash; ex: sha256sum), etc. cu validari de date specifice

- inregistrarea unui utilizator nou presupune adaugarea intr-un registru .csv a detaliilor de inregistrare, autogenerarea unui ID unic, crearea unui director "home", trimiterea unui email de 
  confirmare cand contul a fost creat cu succes; ex: sendmail.

Simularea autentificarii utilizatorilor + logout:
- aceasta optiune cauta numele de utilizator in registru, si daca exista, solicita parola de access. In cazul in care hash-ul parolei coincide, terminalul navigheaza catre directorul "home" 
  al utilizatorului respectiv iar in registru se actualizeaza un camp "last_login" specific fiecarui utilizator. De asemenea, in contextul de executie parinte, unei variabile array 
  "logged_in_users" se adauga numele de utilizator

- functionalitatea de logout presupune stergerea utilizatorului din lista de utilizatori autentificati

- pentru operatii text, unde este necesar, se va folosi sed si nu awk.

Generarea de rapoarte / utilizatori:
- aceasta functionalitate presupune realizarea pentru un nume de utilizator al unui raport care contorizeaza numarul de fisiere, numarul de directoare si dimensiunea pe disc a fisierelor 
  asociate acelui utilizator. Raportul se genereaza asincron si se gaseste in directorul "home" al fiecarui utilizator.
