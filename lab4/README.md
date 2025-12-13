# Laboratorium 4 - Nawigacja 
- Proszę zmodyfikować przykład 03 przez zmianę kolorów, oświetlenia i ułożenia elementów sceny.  
- Przede wszystkim proszę umieścić obiekt, który byłby przyklejony do kamery, znajdował się przed nią i udawał celownik, broń, deskę rozdzielczą samochodu, lub coś podobnego. Można to zrobić tak, że przed kamerą ustawiamy obiekt, np. kwadrat albo sześcian, odpowiednio go pozycjonujemy (w jakiej odległości powinien być przed kamerą), a następnie dodajemy go do obiektu `camera` analogicznie jak dodajemy obiekty do sceny: `camera.add(object)`. W ten sposób obiekt będzie poruszał się zgodnie z kamerą. Następnie na obiekt należy nałożyć wspomnianą teksturę celownika, pistoletu, kokpitu, samochodu od tyłu, etc. Tekstury proszę znaleźć w Internecie i ściągnąć je (warto wybrać tekstury z przezroczystym tłem; powinien to być obrazek w formacie np. png, bo .jpeg nie przechowuje przezroczystości). W jednej z modyfikacji, jako obiekt przed kamerą, można dodać kwadrat, a na niego nałożyć załączoną teksturę maska.png. Tekstura ma przezroczystości - wycięcia (czego przy podglądzie w niektórych aplikacjach nie widać), tak że po dołączeniu jej do sceny i odpowiednim przeskalowaniu, mamy wrażenie jakbyśmy obserwowali scenę przez otwory w masce (Batmana dajmy na to). Proszę pamiętać, żeby w materiale związanym z teksturą był ustawiony parametr `transparent:true` 

Przykład kodu może wyglądać następująco: 
```javascript
var maskTexture = new THREE.TextureLoader().load("maska.png"); 
var maskGeometry = new THREE.PlaneGeometry(5, 5); 
var maskMaterial = new THREE.MeshBasicMaterial({map: maskTexture, transparent: true}); 
var mask = new THREE.Mesh(maskGeometry, maskMaterial); 

mask.position.x = 0; 
mask.position.y = 1; 
mask.position.z = -1.3; 
camera.add(mask); 
```
- Ostatecznie proszę przygotować scenę – może być całkiem zmieniona – po której poruszamy się z jakimś efektownym obiektem przed kamerą. 
- Można również spróbować dodać skybox z nałożonymi teksturami, żeby ograniczyć scenę, choć może się on kłócić z użytą w przykładzie mgłą. Trzeba to sprawdzić – może słabsza mgła i tekstury na horyzoncie dadzą lepszy efekt. W ogóle można podokładać tekstury według uznania. 
- Wynik zawierający plik html i dodaną/dodane tekstury proszę przesłać jako zadanie tego laboratorium.