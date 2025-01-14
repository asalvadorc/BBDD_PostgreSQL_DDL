# Exercicis de tot el tema

Al llarg d'aquesta tercera part, en el conjunt d'exercicis de DDL, crearem
tota l'estructura de la Base de Dades **FACTURA** , però per a no interferir
cadascú amb els altres companys, cadascú es connectarà a la seua Base de Dades
**f_grup_9999x** (on grup és el vostre grup p.ex. 1cfsg, 1cfsh... , 9999 són
les 4 últimes xifres del vostre DNI, i x la lletra del NIF), connectant com un usuari amb el mateix nom i contrasenya

L'esquema Entitat-Relació i l'esquema relacional que implementarem serà el
següent:

![](factura.png)


!!!note "Nota"
      Durant tots aquestos exercicis de DDL pot ser molt convenient tenir obertes
      les dues connexions: la de **FACTURA** (per anar consultant) i la de
      **f_grup_9999x** (per anar creant i modificant), on grup és el vostre grup,
      9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF.

**Ex_1** Creeu la taula **CATEGORIA** , amb els mateixos camps i del mateix
tipus que en la taula CATEGORIA de **FACTURA** , però de moment sense clau
principal ni cap altra restricció. 

**Ex_2** Creeu la taula **ARTICLE** , també sense restriccions.

**Ex_3** Crear la taula **PROVINCIA** , amb la clau principal.

**Ex_4** Crear la taula **POBLE** , amb la clau principal i la restricció que
el camp **cod_pro** és clau externa que apunta a PROVINCIA.

**Ex_5** Crear la taula **VENEDOR** , amb la clau principal i la clau externa
a POBLE (de moment no definim la clau externa a VENEDOR, que és reflexiva).

**Ex_6** Crear la taula **CLIENT** , amb la clau principal i la clau externa a
POBLE

**Ex_76** Crear la taula **FACTURA** , amb la clau principal i les claus
externes a CLIENT i VENEDOR. També heu d'exigir que **cod_cli** siga no nul.

**Ex_8** Crear la taula **LINIA_FAC** , amb la clau principal (observa que
està formada per 2 camps) però de moment sense la clau externa que apunta a
ARTICLE. A més **cod_a** ha de ser no nul.

**Ex_9** Afegir un camp a la taula **VENEDOR** anomenat **alies** de tipus
text, que ha de ser no nul i únic.

**Ex_10** Esborrar el camp anterior, **alies** , de la taula **VENEDOR**.

**Ex_11** Afegir la clau principal de **CATEGORIA**.

**Ex_12** En la taula **ARTICLE** afegir la clau principal i la clau externa a
CATEGORIA.

**Ex_13** En la taula **LINIA_FAC** afegir la clau externa que apunta a
FACTURA, **exigint que s'esborre en cascada** (si s'esborra una factura,
s'esborraran automàticament les seues línies de factura). I també la clau
externa que apunta a ARTICLE (aquesta normal, és a dir NO ACTION)

**Ex_14** Afegir un índex anomenat **i_nom_cli** a la taula **CLIENT** pel camp
**nom**.

**Ex_15** Afegir un índex anomenat**i_adr_ven** a la taula **VENEDOR** per a
que estiga ordenat per **cp** (ascendent) i **adreca**(descendent).

**Ex_16** Crear la vista **RESUM_FACTURA** , que ens dóne el total dels diners
de la factura, el total després del descompte d'articles, i el total després
del descompte de la factura, tal i com teníem en la consulta **6.56**. A
partir d'aquest moment podrem utilitzar la vista per a traure aquestos
resultats

**Ex_17** Inserir en la taula **CATEGORIA** les següents files:

**cod_cat** | **descripcio**  
---|---  
BjcOlimpia | Components Bjc Seria Olimpia  
Legrand | Components marca Legrand  
IntMagn | Interruptor Magnetotérmico  
Niessen | Components Niesen Serie Lisa  
  
**Ex_18** Inserir els següents articles.

**cod_art** | **descrip** | **preu** | **stock** | **stock_min** | **cod_cat**  
---|---|---|---|---|---  
B10028B | Cruzamiento Bjc Serie Olimpia | 4.38 | 2 | 1 | BjcOlimpia  
B10200B | Cruzamiento Bjc Olimpia Con Visor | 0.88 | 29 |  | BjcOlimpia  
L16550 | Cartucho Fusible Legrand T2 250 A | 5.89 | 1 | 1 | Legrand  
L16555 | Cartucho Fusible Legrand T2 315 A | 5.89 | 3 | 3 | Legrand  
IM2P10L | Interruptor Magnetotermico 2p, 4 | 14.84 | 2 | 1 | IntMagn  
N8008BA | Base Tt Lateral Niessen Trazo Bla | 4.38 | 6 | 6 | Niessen  
  
**Ex_19** Inserir en la taula **CLIENT** tres files amb les següents dades

**cod_cli** | **nom** | **adreca** | **cp** | **cod_pob**  
---|---|---|---|---  
303 | MIRAVET SALA, MARIA MERCEDES | URBANIZACION EL BALCO, 84-11 |  |   
306 | SAMPEDRO SIMO, MARIA MERCEDES | FINELLO, 161 | 12217 |   
387 | TUR MARTIN, MANUEL FRANCISCO | CALLE PEDRO VIRUELA, 108-8 | 12008 |   
  
**Ex_21** Inserir la següent factura:

**num_f** | **data** | **cod_cli** | **cod_ven** | **iva** | **dte**  
---|---|---|---|---|---  
6535 | 2015-01-01 | 306 |  | 21 | 10  

**num_f** | **num_l** | **cod_art** | **quant** | **preu** | **dte**  
---|---|---|---|---|---  
6535 | 1 | L16555 | 2 | 5.89 | 25  
  
**Ex_22** Inserir la següent factura (aquesta té més d'una línia de factura).

**num_f** | **data** | **cod_cli** | **cod_ven** | **iva** | **dte**  
---|---|---|---|---|---  
6559 | 2015-02-16 | 387 |  | 10 | 10  

**num_f** | **num_l** | **cod_art** | **quant** | **preu** | **dte**  
---|---|---|---|---|---  
6559 | 1 | IM2P10L | 3 | 14.84 |   
6559 | 2 | N8008BA | 6 | 4.38 | 20  
  
**Ex_23** Esborrar la factura **6559**. Comprovar que també s'han esborrat les
seues línies de factura

**Ex_24** Esborrar els articles dels quals **no** tenim**stock mínim**.

**Ex_25** Llevar tots els codis postals dels clients.

**Ex_26** Pujar el preu dels articles de la categoria **BjcOlimpia** un **5%**
(el resultat serà que l'únic article d'aquesta categoria haurà passat d'un
preu de 4.38 a **4.60€**)


Llicenciat sota la  [Llicència Creative Commons Reconeixement NoComercial
CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)

