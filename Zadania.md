* Which actors have the first name ‘Scarlett’
* Which actors have the last name ‘Johansson’
* How many distinct actors last names are there?
* Which last names are not repeated?
* Which last names appear more than once?
* Which actor has appeared in the most films?
* Is ‘Academy Dinosaur’ available for rent from Store 1?
* When is ‘Academy Dinosaur’ due?
* What is that average running time of all the films in the sakila DB?
* What is the average running time of films by category?


### Wyszukiwarka filmów

Dany jest następujący zestaw klas: 

```java
record Scope(Integer min, Integer max) {}

record FilmQuery(String title, List<String> categories, String language, String actorLastName, Scope rentalRateScope) {}

class FilmSearch {
    public static List<String> search(FilmQuery query) {
        return null;
    }
}
```

Zadaniem jest zaimplementowanie wyszukiwarki filmów (metoda `search` w klasie `FilmSearch`). 

Ma ona znajdować filmy (a konkretnie ich tytuły) spełniające określone warunki - przekazane jako instancja rekordu `FilmSearch` 

Każde pole rekordu `FilmSearch` reprezentuje konkretny warunek wyszukiwania (o ile nie ma wartości `null`)

* `title` - podany tytuł musi być fragmentem (lub całością) tytułu filmu
* `categories` - kategoria filmu musi należeć do podanej listy
* `language` - podany język musi byc językiem LUB oryginalnym językiem filmu
* `actorLastName` - w filmie musi grać aktor o podanym nazwisku
* `rentalRateScope` - ocena filmu musi zawierać się w podanym zakresie (`null` jako `min` lub `max` oznacza brak odpowiednio dolnego lub górnego ograniczenia)