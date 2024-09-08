# cpp-digest-8

C++ Дайджест №8 (8 июля – 14 июля 2024)

Теги: дайджест, c++-дайджест, c++, c++17

Хабы: Программирование, C++

## Аннотация

Привет, Хабр! Сегодня я хочу вам представить подборку интересных новостей и материалов по C++ за последнюю неделю.

Приятного чтения!

## 📝 Статьи

1. [Understanding the inner workings of C++ smart pointers - The shared_ptr](https://andreasfertig.blog/2024/09/understanding-the-inner-workings-of-cpp-smart-pointers-the-shared_ptr/) — вам всегда было интересно, как устроен `std::shared_ptr` ([cppreference](https://en.cppreference.com/w/cpp/memory/shared_ptr)) изнутри? Статья предлагает разбор минималистичной, но вполне себе полноценной его реализации.
2. [What’s new in C++26 (part 1)](https://mariusbancila.ro/blog/2024/09/06/whats-new-in-c26-part-1/) — Обзор свежепринятых в C++26 новинок: переменные-плейсхолдеры ([cppreference](https://en.cppreference.com/w/cpp/language/conflicting_declarations#Potentially-conflict_declarations)), форматированные строки в `static_assert` и другое.
```c++
// Разве это не прекрасно, что мы можем написать так и на нас не будет ругаться компилятор?
auto [data, _] = get_data();
// И мы можем повторить этот _ в одной области видимости много раз!
auto [ptr, _] = std::to_chars(p, last, 42);

// Да, мы не могли использовать std::format в static_assert до C++26
static_assert(sizeof(int) == 4, std::format("Expected 4, actual {}", sizeof(int)));
```
3. [An Overview of C++26: The Library](https://www.modernescpp.com/index.php/an-overview-of-c26-the-library/) — Если предыдущая статья обозревает исключительно изменения в самом языке, то в этой статье речь идет об изменениях в стандартной библиотеке: `std::string_view` ([cppreference](https://en.cppreference.com/w/cpp/string/basic_string_view)) продолжают делать всё более и более полезным, ranges продолжают допиливать, а количество контейнеров в стандартной библиотеке всё продолжает увеличиваться:
```cpp
// Динамически-расширяемый вектор с фиксированным capacity заказывали?
std::inplace_vector<int, 2> vec;
vec.push_back(1); // OK
vec.push_back(2); // OK
vec.push_back(3); // std::bad_alloc! Место на стеке закончилось!
```
4. [Structs and constructors](https://www.sandordargo.com/blog/2024/09/04/structs-and-constructors) — Структуры и конструкторы: нужно ли одно другим, или агрегатной инициализации хватит всем?
5. [Reader Q&A: What’s the best way to pass an istream parameter?](https://herbsutter.com/2024/09/03/reader-qa-whats-the-best-way-to-pass-an-istream-parameter/) — Знаток (председатель [WG21](https://www.open-std.org/jtc1/sc22/wg21/)) отвечает на вопрос: как лучше всего принять в функцию `std::istream` ([cppreference](https://en.cppreference.com/w/cpp/io/basic_istream)). Спойлер (вы же догадались?):
```cpp
template <typename S>
void add_from_stream( S&& s )
    requires std::is_convertible_v<S, std::istream const&>
{
    // do work + remember to use s as "std::forward<S>(s)"
}
```
6. [Synchronization Primitives in C++20](https://www.kdab.com/synchronization-primitives-in-c20/) — Возвращаясь от мечт о прекрасном будущем (C++26) к реальности (C++20, если вам повезло): о `std::latch` ([cppreference](https://en.cppreference.com/w/cpp/thread/latch)) и `std::barrier` ([cppreference](https://en.cppreference.com/w/cpp/thread/barrier)).
7. [Compressing floating-point numbers quickly by converting them to brain floats](https://lemire.me/blog/2024/09/02/compressing-floating-point-numbers-quickly-by-converting-them-to-brain-floats/) — Не хватает памяти на большие объемы `double`-ов? Как насчет того, чтобы сжать их до 16 бит ([bfloat16](https://en.wikipedia.org/wiki/Bfloat16_floating-point_format))?

## 📺 Видео и доклады

1. [C++ Weekly - Ep 444 - GCC's Implicit constexpr](https://www.youtube.com/watch?v=t6hFPKiOS-Q) — Обзор расширения GCC ([GCC docs](https://gcc.gnu.org/onlinedocs/gcc/C_002b_002b-Dialect-Options.html#index-fimplicit-constexpr)), делающего все `inline` функции в вашем коде `constexpr`, если они удовлетворяют всем требованиям `constexpr`-функций.

## Послесловие

> Дайджест составлен и опубликован при поддержке московского сообщества программистов [C++ Moscow](https://t.me/cppmoscow_info)

Заметили ошибку или опечатку? Сообщите в личку ([telegram](https://t.me/eoanermine), [habr](https://habr.com/ru/conversations/eoanermine/))

Прислать ссылку можно [через форму](https://forms.yandex.ru/cloud/64f48043e010db921819c447/) или просто написав мне в личные сообщения ([telegram](https://t.me/eoanermine), [habr](https://habr.com/ru/conversations/eoanermine/))

← Предыдущий выпуск: [C++ Дайджест №7](https://habr.com/ru/articles/773894/)
