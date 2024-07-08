# cpp-digest-8

C++ Дайджест №8 (8 июля – 14 июля 2024)

Теги: дайджест, c++-дайджест, c++, c++17

Хабы: Программирование, C++

## Аннотация

Привет, Хабр! Сегодня я хочу вам представить подборку интересных новостей и материалов по C++ за последнюю неделю.

Приятного чтения!

## 📝 Статьи

1. [What’s the point of std::monostate? You can’t do anything with it!](https://devblogs.microsoft.com/oldnewthing/20240708-00/?p=109959) — `std::monostate` (C++17, [cppreference](https://en.cppreference.com/w/cpp/utility/variant/monostate)) и зачем он вообще нужен, если это просто пустой класс:
```cpp
struct monostate { };
// plus relational operators and a hash specialization
```

## 📺 Видео и доклады

1. [C++ Weekly - Ep 436 - Transforming Lambda Captures](https://www.youtube.com/watch?v=t6hFPKiOS-Q) — интересный пример использования [pack expansion](https://en.cppreference.com/w/cpp/language/parameter_pack) для преобразования захваченных лямбдой значений.

## Послесловие

> Дайджест составлен и опубликован при поддержке московского сообщества программистов [C++ Moscow](https://t.me/cppmoscow_info)

Заметили ошибку или опечатку? Сообщите в личку ([telegram](https://t.me/eoanermine), [habr](https://habr.com/ru/conversations/eoanermine/))

Прислать ссылку можно [через форму](https://forms.yandex.ru/cloud/64f48043e010db921819c447/) или просто написав мне в личные сообщения ([telegram](https://t.me/eoanermine), [habr](https://habr.com/ru/conversations/eoanermine/))

← Предыдущий выпуск: [C++ Дайджест №7](https://habr.com/ru/articles/773894/)
