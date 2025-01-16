# 1. Introducció

Fins el moment només hem vist una sentència, el SELECT, una sentència molt
potent per a poder consultar el contingut de les taules d'una Base de Dades.
Però el llenguatge SQL és més complet, i permet també crear l'estructura de
les taules i altres objectes. I també ens permetrà manipular la informació,
introduint dades noves, eliminant-ne o modificant les ja existents.

Subdividirem, aquesta part del tema en dos grans blocs:

  * **DDL** (_Data Definition Language_) llenguatge de definició de dades. És el que ens permetrà definir les estructures de dades: taules, vistes, i com veurem en altres temes, més objectes.

  * **Consultes d'actualització**. No canvien cap estructura de cap taula, sinó que modifiquen el contingut de les taules. I només hi ha 3 possibilitats en la modificació del contingut: inserir noves files (INSERT), modificar les ja existents en algun camp determinat (UPDATE) o esborrar files (DELETE)

Durant tota aquesta tercera part de SQL farem consultes per a crear o
modificar taules, o per a modificar les dades de les taules.

No ens convé en absolut treballar sobre la Base de Dades **geo** ni sobre
**factura** , ja que el que faríem seria "boicotejar-nos" entre nosaltres.
Treballarem amb dues Bases de Dades noves:

  * **proves** (connectant-nos com l'usuari **proves**): servirà per a fer proves, com el seu propi nom indica. Tots els exemples els farem en aquesta BD
  * **f_grup_9999x** , on grup és el codi del vostre grup (p.ex 1cfsg, 1cfsj, 1cfsl...), 9999 seran les 4 últimes xifres del vostre DNI, i x és la lletra del vostre NIF. És a dir, tindreu una Base de Dades per a cadascú de vosaltres, i un usuari amb el mateix nom. És on haureu de treballar els exercicis.

Us recomane vivament que us creeu una altra connexió per a cadascuna de les
Bases de Dades anteriors. D'aquesta manera, segurament en tindreu quatre
connexions: la de **geo** , la de **factura** , la de **proves** i la de
**f_grup_9999x** (substituint per les dades del vostre grup i NIF)



Llicenciat sota la  [Llicència Creative Commons Reconeixement NoComercial
CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)

