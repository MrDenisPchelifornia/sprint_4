Коменнтарии дублируюся в коде что бы удобнее было 
Названия тестам старался довать согласно правилам предложенным у спринте 
1. Метод add_new_book. Проверяем что книги длинна названия которых свыше 41 символа не добавляются
2. Метод set_book_genre. Проверяем установится ли жанр для добавленной книги
3. Метод set_book_genre. И посмотрим установится ли жанр которого нет в списке для существующей книги
Изначально я сделал такие проверки:
 def test_set_book_genre():
     collector = BooksCollector()
     collector.add_new_book("Пикник на обочине")
     collector.set_book_genre("Пикник на обочине", "Фантастика")
     assert collector.books_genre["Пикник на обочине"] == "Фантастика"
 
 def test_set_book_genre():
     collector = BooksCollector()
     collector.add_new_book("Пикник на обочине")
     collector.set_book_genre("Пикник на обочине", "Комедия")
     assert collector.books_genre["Пикник на обочине"] != "Комедия"
Потом решил что параметризацию лучше всего будет применить тут и ничего умнее чем то что в итоге оказалось в файле тест я не придумал

4. Метод get_book_genre. Проверяем что получаем верный жанр на запрос по существующей в списке книге.
5. Метод get_books_with_specific_genre. Проверяем что в запрашиваем списке по конкретному жанру верные книги.
6. Метод get_books_for_children. Проверяем что получаем верный список при запросе книг без возрастного рейтинга
7. Метод add_book_in_favorites. Проверяем что книга добавилась в избранное
8. Метод get_list_of_favorites_books. Проверяем что при запросе списка избранное возвращаются корректные книги
9. Метод delete_book_from_favorites. Проверяем что избранная книга удаляется из списка избранных.

30.04.24 Если я все правильно понял то исправил О_о
Вообше в шпаргалке сказно что нужно создать еще одну ветку для фикса
Но уже в другой сказано закомитить исправления в этой
Решил не городить неудобства закомичу в эту ветку, старый код закомментировал, а новый написал ниже как и просили
Вижу потонциал для параметризаций да и фиксутры напрашиваются, но немного не успевал(