# Anàlisi de Disseny d'Interfícies i Accessibilitat

Aquest document analitza diverses pàgines web des del punt de vista del disseny d'interfícies i l'accessibilitat, destacant l'ús del color i altres elements visuals.

---

## Exercici 1: Anàlisi de Pàgines Web

### **Université Paul Sabatier III**
- **Estil de colors:** Ús de colors cridaners amb una combinació de tonalitats grogues i negres.
- **Imatges:** Les imatges es mostren en blanc i negre per preservar les tonalitats fosques. Els colors es revelen només quan es passa el ratolí per damunt, destacant així la fotografia.
- **Objectiu:** Mantenir una estètica coherent i destacar elements visuals de manera subtil.

---

### **Ling Cars**
- **Estil de colors:** Pàgina amb colors molt saturats i recarregats, tant en el disseny com en els logos mostrats.
- **Tipografia:** Ús d'estils de fonts cridaners per als títols, reforçant l'impacte visual.
- **Objectiu:** Crear una experiència visual impactant i memorable.

---

### **Escola d'Art i Disseny de Reus**
- **Estil de colors:** Similitud amb el disseny de la pàgina de la Université Paul Sabatier III, amb imatges en blanc i negre que es revelen al passar el ratolí per damunt.
- **Objectiu:** Mantenir una estètica uniforme i evitar contrastos excessius entre les imatges.

---

### **Scratch**
- **Estil de colors:** Disseny pensat per a nens petits, amb colors vius i alegres. El lila és el color principal, complementat amb tonalitats similars.
- **Objectiu:** Crear una interfície atractiva i amigable per al públic infantil.



## Exercici 2: Anàlisi d'Eines d'Accessibilitat

En aquest exercici s'han utilitzat diverses eines per analitzar l'accessibilitat de pàgines web i comprovar el compliment de les pautes WCAG 2.2.

### Eines utilitzades

1. **[Color Blindness Test](https://www.colorblindnesstest.org/)**  
   Aquesta eina permet simular com perceben els colors les persones amb diferents tipus de daltonisme.  
   ![Exemple de test de colorblindtest.org](assets_extensions/cap1.png)

2. **[WCAG Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/)**  
   # Informe d'Auditoria d'Accessibilitat

Aquest informe detalla els problemes d'accessibilitat detectats en una pàgina web, seguint les pautes WCAG 2.2.

---

## Assumptes Crítics

### Falta l'atribut del llenguatge als elements HTML
- L'etiqueta `<html>` té `lang="en"`, però el contingut sembla estar en català.
- **Solució:** Canviar l'atribut a `lang="ca"` per garantir una pronunciació adequada amb els lectors de pantalla.

---

### Problemes d'accessibilitat de formularis
- Les entrades del formulari no tenen identificadors únics (`id="nom"` es repeteix).
- Falten etiquetes obligatòries per als camps requerits.
- No hi ha missatges de gestió d'errors ni de validació.
- **Solució:** Assignar identificadors únics, afegir etiquetes descriptives i implementar missatges d'error clars.

---

### Problemes de navegació
- El menú de navegació no té rols ARIA ni estats expandits/replegats.
- No hi ha un enllaç per saltar directament al contingut per als usuaris del teclat.
- **Solució:** Afegir rols ARIA i un enllaç de salt al contingut principal.

---

### Contrast de color
- El text clar sobre fons blau (classe `bg-primary` amb text blanc) no compleix la relació de contrast mínima de 4,5:1.
- **Solució:** Ajustar els colors per complir amb els estàndards de contrast.

---

### Accessibilitat de la imatge
- Les imatges tenen text alternatiu, però les del carrusel podrien tenir descripcions més detallades.
- Falten etiquetes ARIA per als controls del carrusel.
- **Solució:** Afegir descripcions més completes i etiquetes ARIA adequades.

---

## Problemes Mitjans

### Estructura de la taula
- Les taules tenen capçaleres, però manquen atributs `scope` per millorar la navegació amb lectors de pantalla.
- **Solució:** Afegir atributs `scope` a les capçaleres.

---

### Navegació amb teclat
- No hi ha indicadors d'enfocament visibles personalitzats per als elements interactius.
- L'ordre de tabulació segueix l'ordre del DOM, però es podria millorar.
- **Solució:** Implementar estils d'enfocament visibles i ajustar l'ordre de tabulació si cal.

---

### Estructura del document
- La jerarquia dels encapçalaments no es manté constant (salta de `h2` a `h4` en alguns llocs).
- **Solució:** Revisar i corregir la jerarquia dels encapçalaments.

---

### Disseny responsive
- Alguns elements d'amplada fixa provoquen desplaçament horitzontal en dispositius mòbils.
- **Solució:** Utilitzar dissenys flexibles i evitar amplades fixes.

---

## Fallades específiques de WCAG 2.2

### Criteri d'èxit 1.3.1: Informació i relacions
- Els controls de formulari no estan associats correctament amb les etiquetes.
- S'han trobat identificadors duplicats als elements del formulari.

---

### Criteri d'èxit 2.4.3: Ordre del focus
- No hi ha cap enllaç de navegació per saltar per als usuaris del teclat.

---

### Criteri d'èxit 3.3.2: Etiquetes o instruccions
- Els camps del formulari no tenen instruccions ni descripcions clares.

---

### Criteri d'èxit 4.1.1: Anàlisi
- Valors d'atribut d'ID duplicats (`id="nom"` apareix dues vegades).

---

Aquest informe proporciona una guia per solucionar els problemes d'accessibilitat detectats i garantir el compliment de les pautes WCAG 2.2.

3. **Eines de desenvolupador de Firefox**  
   Inclou eines integrades per analitzar l'accessibilitat, com el contrast de colors i l'ordre del focus. En auqest cas, s'ha aplicat el filtre de tritanopia (no poder veure blaus) i s'ha passat per la prova d'accessibilitat.
   ![Ús de la web](assets_extensions/cap2.png)

4. **[Are My Colors Accessible](https://www.aremycolorsaccessible.com/)**  
   Verifica si els colors utilitzats en una pàgina compleixen els estàndards d'accessibilitat.En aquest cas, s'ha posat els colors dels elements de text amb el seu color fons per comparar si retornava valors vàlids.  

5. **Extensions de navegadors**:
   - **WCAG Contrast Checker Extension**: Comprova el contrast entre el text i el fons. Passant l'exensió a la pàgina, ha donat el següent resultat:
    ![Resultat de WCAG Contrast Checker](assets_extensions/cap3.png)

   - **Accessive Web Helper Extension**: Analitza problemes d'accessibilitat en temps real. No ha funcionat l'exensuió per la meva pàgina.
   ![Resultat de WCAG Contrast Checker](assets_extensions/cap4.png)

   - **Accessibility Insights Extension**: Proporciona informes detallats sobre l'accessibilitat.
   Extensió per Edge, incompatible en aquest equip Ubuntu.

   - **Issues Extension**: Detecta problemes d'accessibilitat en el codi.
   - **Lighthouse Extension**: Genera informes d'accessibilitat, SEO i rendiment.
   ![Resultat de Lighthouse](assets_extensions/cap5.png)

---
