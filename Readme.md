# Document de Disseny: 01_idea_i_abast.md

## 1. Títol provisional del joc
**Space Defender: Rogue Legacy** (Aggressive Edition)

## 2. Tipus de microvideojoc escollit
*Shoot 'em up* (Shmup) d'estil arcade lateral amb mecàniques de progressió infinita.

## 3. Objectiu del joc
Sobreviure a onades interminables d'enemics i meteorits mentre s'eliminen els Caps de Sector per avançar en la classificació i obtenir la puntuació més alta possible en una sola sessió.

## 4. Rol del jugador
El jugador controla una nau de combat avançada. La seva missió és actuar com l'última línia de defensa contra una invasió espacial, gestionant el moviment i el foc de les armes de manera estratègica.

## 5. Regles bàsiques
* **Moviment:** Lliure en les 4 direccions (`↑`, `↓`, `←`, `→`) dins dels límits de la pantalla.
* **Combat:** Disparar de forma constant (Barra Espaiadora) per destruir enemics i asteroides.
* **Power-ups:** Destruir asteroides pot alliberar nuclis d'energia que modifiquen el tipus de dispar (Doble, Escopeta, Rebot o Pesat) durant un període de 10 segons.
* **Col·lisions:** Qualsevol impacte amb un enemic, bala enemiga o asteroide resta una vida (cor).

## 6. Condicions de victòria i derrota
* **Victòria:** No existeix una victòria definitiva (joc tipus *endless*). L'èxit es mesura pel nombre de sectors netejats i la puntuació total acumulada.
* **Derrota:** Es produeix quan el comptador de vides arriba a zero. El joc ofereix un resum de la missió abans de permetre el reinici.

## 7. Bucle principal del joc (Core Loop)
1.  **Navegació:** L'usuari esquiva obstacles i bales enemigues mentre es posiciona.
2.  **Destrucció:** S'eliminen enemics per sumar punts i asteroides per buscar recursos.
3.  **Millora:** Recollida de *power-ups* per augmentar la potència ofensiva.
4.  **Enfrontament:** Cada 25 punts, s'activa el combat contra un Cap de Sector.
5.  **Progressió:** En derrotar el Cap, la dificultat augmenta i el bucle es reinicia amb paràmetres més exigents.

## 8. Repte principal i dificultat
El repte principal és la gestió del caos en pantalla a mesura que la dificultat augmenta. La progressió és **incremental i agressiva**: cada nou sector augmenta la velocitat dels projectils enemics, la velocitat de moviment de les naus enemigues i la seva cadència de dispar.

## 9. Limitacions explícites
* Sistema de gràfics basat exclusivament en l'API Canvas (sense imatges externes).
* Absència de sistema de guardat permanent (experiència purament arcade).
* Interfície d'usuari (HUD) minimalista integrada en el propi llenç de joc.

## 10. Riscos tècnics
* **Gestió d'Entitats:** L'acumulació de bales en pantalla podria afectar el rendiment si no es netegen els objectes fora de rang.
* **Control de Col·lisions:** Garantir que les col·lisions múltiples no generin errors de lògica en el moment en què un Cap de Sector mor (solucionat amb eliminació immediata de l'objecte).

## 11. Exploració amb IA (Prompts)
* **Prompt 1:** "Crea un codi base en HTML5 Canvas per a un joc de naus on aparegui un cap cada 25 punts i la dificultat pugi."
    * *Resum:* Es va establir l'estructura del bucle de joc i la lògica de generació d'enemics aleatoris.
* **Prompt 2:** "Fes que els enemics disparin més sovint i corregeix el crash que ocorre quan moltes bales maten al boss alhora."
    * *Resum:* S'ha implementat un control de cadència basat en temps (`Date.now()`) i una sentència `break` per aturar el processament de col·lisions un cop el boss és eliminat.

## 12. Proposta final escollida
Un microvideojoc d'acció ràpida accessible des del navegador, que prioritza la fluïdesa del moviment i la varietat de dispars mitjançant un sistema de *power-ups* dinàmics.

## 13. Justificació de viabilitat
El projecte és totalment viable gràcies a la seva arquitectura monolítica en JavaScript/HTML5. En no dependre de servidors ni de llibreries pesades, garanteix compatibilitat total i un rendiment estable a 60 FPS en qualsevol dispositiu.

## 14. Mini pla de treball
* **Setmana 1 (Dia 1-2):** Desenvolupament del motor de moviment i sistema de dispar bàsic.
* **Setmana 1 (Dia 3-4):** Implementació d'enemics, asteroides i lògica de col·lisions.
* **Setmana 1 (Dia 5):** Disseny del Cap de Sector i sistema de *power-ups*.
* **Setmana 1 (Dia 6):** Ajustos de dificultat "Aggressive" i depuració d'errors.
* **Setmana 1 (Dia 7):** Documentació final i poliment visual.

## 15. Eines previstes i justificació
* **HTML5 / Canvas API:** Escollit per la seva potència per gestionar gràfics 2D de forma nativa.
* **JavaScript (Vanilla):** Per mantenir el codi lleuger, ràpid i fàcil de depurar.
* **VS Code:** Editor principal per la seva integració amb eines de depuració web.
* **IA de suport (Gemini):** Utilitzada per optimitzar algoritmes de col·lisió i estructurar la documentació.