# sass-whole-page

I detta repo har du en färdig sida med en hel del styling som ligger i `style.scss` och som är vanlig CSS. Som i tidigare övningar ska denna kod göras om så att den använder sig mer utav sass. Den har några responsiva brytpunkter. Du får gärna lägga till extra CSS om du känner att det behövs fler brytpunkter, fler färger eller liknande. Huvudfokusen är här på att testa sass-funktionaliteter, speciellt `@mixin` men även det vi lärt oss med med `nesting`, `&` samt variabler.

## Övning

* https://sass-lang.com/guide
* http://sass-lang.com/documentation/Sass/Script/Functions.html


1. Det första vi kan börja med är att bryta ner den stora filen till mindre moduler. Skapa olika partials (`_variables.scss` t.ex.) och börja dela upp koden i mindre delar. 
2. Fortsätt med att plocka ut vanligt förekommande värden och sätt dessa i variabler. Färger, marginaler, padding, textegenskaper.
3. Börja sedan nästla det som kan nästlas och försök få ner antalet css-regler. Vissa saker behöver inte nödvändigtvis nästlas men du kan köra på för övningens skull. Se även här över om du kan använda `&`-tecknet för att låta css-regler ärva. Kom ihåg att även `@media`-queries kan nästlas, se exempel nedan.
```scss
a {
  color: teal;
  transition: color 300ms;
  &:hover {
    color: complement(teal);
  }
  @media (min-width: 900px){
    font-size: 2rem;
  }
}
```
4. Näst på tur är `@mixin`. Plocka ut vanligt förekommande kodblock och gör de till mixins. Dessa mixins borde även ligga i en separat partials, skapa en fil som heter `_mixins.scss` och lägg samtliga mixins där.
5. Testa att skapa en mixin med argument. Det behöver inte vara något avancerat, bara så att man kan förse denna mixin med olika val. I nedan exempel så är defaultfärger `#fff` och `#555` men om vi skulle kalla på denna mixin med våra egna värden så ersätts defaultvärdena.
```scss
@mixin gradient($start: #fff, $stop: #555){
  background: linear-gradient($start, $stop);
}
```
Men en mixin kan också vara utan argument och mycket enklare:
```scss
@mixin rounded{
  border-radius: 50%;
}

```
6. Se över om koden går att "sassa" mera annars är det klart. Se till så att konceptet om `@mixins` sitter.
7. Blir du färdig tidigt kan du gå vidare till att applicera sass på en av dina egna hemsidor/arboreal-projektet. 
