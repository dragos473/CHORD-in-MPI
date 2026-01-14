# Tema 2 APD 2025key

Am implementat versiunea statica a protocolului CHORD, dupa cerinta. Astfel, am urmat urmatorii pasi:

  Am implementat "build_finger_table"
  
    Am calculat finger table-ul pentru toate nodurile, dupa formula data in cerinta succesor((id + (2 ^ i))  % RING_SIZE)

  Am implementat "closest_perceding_finger"
    
    Pentru a calcula urmatorul "hop", trebuie parcurs finger table-ul si luat cel mai mare finger care sen afla in intervalul (ID, key).
  
  Am implementat "hanlde lookup request"
  
    Pachetul primit este processat si treimis mai departe: Se adauga nodul in path, se incrementeaza pathLen. Se verifica daca pathLen este mai mare decat 32(MAX_PATH), caz in    care se arunca pachetul. Daca succesorul nodului curent este responsabil pentru cheia cautata, se adauga si acesta in path si se trimite LOOKUP_REP la nodul care a initiat      cautarea. Altfel, se trimite LOOKUP_REQ la cel mai bun finger din tabelul nodului curent. Nu am gasit alta funcionalitate pentru current_id, in afara de debug, asa ca nu l-am   folosit.
  
  In final, am creat bucla principala a programului.
    
