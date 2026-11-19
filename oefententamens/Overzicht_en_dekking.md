# Oefententamens OOP – overzicht

| Bestand | Thema | Niveau |
|---|---|---|
| `00_Origineel_Sikora_Breuken.md` | Breuken | Voorbeeld van de prof (mail 29-10-2026) |
| `01_Oefententamen_A_Rechthoeken_zelfde-niveau.md` | Rechthoeken | Gelijk |
| `02_Oefententamen_B_Tijdsduren_zelfde-niveau.md` | Tijdsduren | Gelijk |
| `03_Oefententamen_C_Weerstanden_niveau-hoger.md` | Weerstanden | Hoger |
| `04_Oefententamen_D_Sensormetingen_niveau-hoger.md` | Sensormetingen | Hoger |

Elke stap verwijst naar het hoofdstuk (H1–H19) in `cpp-cursus/cpp_cursus_aantekeningen.md`.

## Dekking: stappen van de prof ↔ C++-cursus (freeCodeCamp, Daniel Gakwaya)

| Stap prof | Onderwerp | In cursus? |
|---|---|---|
| 1 | Arrays | ✅ H7 |
| 2 | Invoer met controle | ✅ H2, H5, H6 |
| 3 | Dynamische allocatie | ✅ H8 |
| 4 | Rekenen en printen | ✅ H4, H6 |
| 5 | Commentaar | ✅ H2 |
| 6 | Functies, pass by value vs reference | ✅ H11, H9, H12 |
| 7 | Class met `private` | ✅ H17 |
| 8 | `operator>>` en `operator<<` overloaden | ⚠️ alleen `<<` (als `friend`, H18/H19); `>>` en operator overloading in het algemeen **niet** |
| 9 | Container: array → `std::list` | ❌ STL-containers (`std::list`) komen niet aan bod |
| 10 | Inheritance | ✅ H18 (+ H19 polymorphism) |
| 11 | Function template | ✅ H15 (+ H16 concepts) |
| 12 | Virtual functions (alleen op de echte midterm, nog niet precies uitgelegd) | ✅ H19 Polymorphism |

**Echte midterm (19-11-2026):** thema complexe getallen, stap 1–7 gedaan. Stap 8–12 staan in [`../midterm/README.md`](../midterm/README.md).

**Gaten om apart te leren:** `operator>>`, overige operator overloading (`+`, `<`, `[]`) en `std::list` (plus `push_back`, iterators, `remove_if`).
