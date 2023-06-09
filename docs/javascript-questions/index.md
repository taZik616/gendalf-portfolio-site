# Список распространенных вопросов по JavaScript.

Этот документ поможет вам в двух случаях:

- Если вы работодатель
- Вы программист, который покинул текущую работу в поисках новой, в требования которой входят знания JS

Я понимаю, что имея даже большой опыт нельзя помнить наверняка все темы JS, так как многие просто не используются, а некоторые теоретические не применяются в реальных задачах. Но повторение этих тем поможет произвести впечатление на работодателя и продемонстрирует вашу ответственность. Я не включал вопросы по темам которые часто используются в практике.

> Список вопросов я рассортировал так, чтобы сложность возрастала вместе с порядковым номером.

### Что такое `NaN` и какова его роль?

- Это специальное значение **«Not a Number»**, которое обычно **говорит о том, что была выполнена бессмысленная операция**
- Его роль в том, чтобы сообщить об ошибке математической операции
- Так же есть функция `isNaN()`, которая проверяет является ли строка не числом

### Что такое примитивные типы данных в JavaScript? Перечислите их.

- Это данные, которые **не являются объектом** и не **имеют методов**.
  <br/>
  <b>Примитивные</b>: <code>bigint, boolean, number, string, symbol, undefined.</code>
  <br/>
  <b>Остальные типы</b>: <code>object, function.</code>

### Какие значения в JS являются ложными?

- `'', 0, null, undefined, NaN, false`

### В чем разница между undefined и is not defined?

- `is not defined` - это **код ошибки** при обращении к несуществующей переменной.
- `undefined` - это значение, присваемое объявленной, но не инициализированной переменной.

### Как проверить, является ли объект массивом?

- Для этого можно использовать встроенный метод `Array.isArray()`.

### Как быстро преобразовать строку в число?

- Можно использовать **унарный +** (например: `const myNum = +myString`), он преобразует строку в число, если это возможно.
- **Унарный -** делает тоже самое, но затем меняет знак результата(`-’20’ => -20`).

### Как динамически добавлять и удалять свойства в JavaScript?

- Вы можете добавить свойство к объекту используя, `myObject.propName = value`, и удалить свойство, используя `delete myObject.propName`.

### Как рассчитать числа Фибоначчи в JavaScript?

- Числа Фибоначчи это **последовательность чисел**, где **каждое значение** – это **сумма двух предыдущих.**
- Решение

![fibonacci](fibonacci.png)

### Для чего используются операторы break и continue в JavaScript?

- `break` и `continue` обеспечивают более точный контроль над выполнением кода в цикле
- `break` завершает текущую итерацию и **приводит к немедленному выходу из цикла.**
- `continue` завершает текущую итерацию, но **не останавливает цикл.**
- `return` работает так же как и break и вдобавок **может вернуть с функции значение остановив выполнение функции.**

![return](return.png)

### Что такое Рекурсия?

- Это когда алгоритм или **функция вызывает сама себя**.

### Что такое чистые(pure) функции?

- это функции, у которых **возвращаемое значение зависит от передаваемых параметров.**

### Что такое мутабельность / иммутабельность?

- Иммутабельность предполагает что **данные, не могут быть изменены**, после создания.
- Мутабельность означает что **данные могут меняться.**
- \* Например в **redux** используются **чистые функции**(reducers), которые **не меняют состояния**, а **возвращают новый объект**, основываясь на текущем состоянии и действии. Из этого можно сделать вывод, что **редакс иммутабельный.**

### В чем разница между атрибутами и свойствами?

- Атрибут — это начальное состояние в рендеринге DOM, а свойство — это текущее состояние

### Что такое ООП (Объектно-ориентированное программирование) и ФП (функциональное программирование)?

- ООП **основано на концепции объектов**. Это **структуры данных**, **которые содержат поля данных**, известные в JavaScript как свойства, и процедуры, известные как методы (Например: `Math` с его методами `random, max, sin` и свойствами такими как `PI`)
- ФП **основан на концепции чистых функций**, которые избегают общего состояния, изменяемых данных и побочных эффектов.

### Что такое XSS?

- (Cross-Site Scripting — «**межсайтовый скриптинг**») — довольно распространенная **уязвимость**, которую можно обнаружить на множестве веб-приложений. Ее суть довольно проста, **злоумышленнику удается внедрить на страницу JavaScript-код, который не был предусмотрен разработчиками**

### Что такое чейнинг(chain) функций?

- Это когда мы **у объекта можем вызывать функции по цепочке**, один за другим

```js
obj.add(‘val’).add(‘val2’).delete(‘valN’)
```

### Что такое анонимная функция?

- Функциональное выражение, которое не записывается в переменную, называют анонимной функцией

### Объясните, что означает currying.

- Это трансформация функций таким образом, чтобы они **принимали аргументы не как** `f(a, b, c)`, **а как** `f(a)(b)(c)`. Это **продвинутая техника** для работы с функциями.
- Она **может быть полезной**, когда мы **пишем для callback функцию, в которую нужно помимо event передать еще что-то**:
  `onClick={myCallbackWithUserName(‘vadim’)}`
- Lodash: `_.curry(func)` **возвращает каррированную версию функции**, но она также может вызываться `func(a, b, c)`.

### Что делает Object.freeze()?

- `Object.freeze` работает со значениями объектов и **делает объект неизменяемым**, то есть изменить его свойства невозможно.
- \* Можно проверить заморожен ли объект с помощью `Object.isFrozen()`.

### Что такое прототип?

- **Объект, на который указывает ссылка** `__proto__`, называется «прототипом».

### Как записать несколько выражений в одну строку?

- Выражения можно записывать в одну строку **через запятую.**

### Почему результатом сравнения двух похожих объектов является false?

- В отличии от примитивов **объекты сравниваются по ссылке в памяти.**

### Как определить наличие свойства в объекте?

- `(‘propName’ in obj)`
- `obj.hasOwnProperty('propName')`
- `obj['propName']`

### В чем разница между оператором «in» и методом ≪hasOwnProperty≫?

- оператор «_in_» **проверяет наличие свойства** не только в самом объекте, но **и в его прототипах**, а метод _hasOwnProperty_ — **только в объекте**.

### Какие конструкции языка вы используете для обхода объектов?

- `for .. in ..`
- `Object.keys(obj).forEach(…)`

![iterateObj](iterateObj.png)

### Как работает Function.prototype.bind()?

- Данный **метод возвращает функцию**, по отношению к которой он вызывается, но **с подмененным контекстом**.

### Что такое hoisting (поднятие) в JavaScript?

- Это механизм в JavaScript, в котором **переменные и объявления функций**, **передвигаются вверх своей области видимости** перед тем, как код будет выполнен
- Стоит отметить то, что механизм «поднятия» передвигает только объявления функции или переменной. **Назначения переменным остаются на своих местах**.

### Как можно клонировать объект? В чем разница глубокого клонирования от поверхностного?

- Можно использовать оператор **spread** `…obj`
- `Object.assign({}, oldObj)`
- `JSON.parse(JSON.stringify(objectToClone))` - этот вариант поддерживает глубокое клонирование
- Разница глубокого клонирования:

![cloningObj](cloningObj.png)

### Что такое замыкание в JavaScript? Приведите пример.

- это создание функции и вместе с ней **окружения, к которому она может обращаться**. Это позволяет ей работать с переменным и функциям этого окружения в дальнейшем.
- Есть трюк с хуком `useMemo()` в react связанный с этой темой, так он выглядит:

![useMemoTrick](useMemoTrick.png)

> Я заметил что я часто нахожу место где useMemo трюк выручает)

### Что такое стрелочная функция и какие ее отличия от обычной?

- Это **краткий способ записи** функциональных выражений.
- Стрелочные функции **не являются конструкторами** (то есть нельзя с помощью `new` создать объект-экземпляр).
- **Не поддерживает** `this` (если быть точнее, то `this` в стрелочной функции будет ссылаться на `this` функции снаружи).
- **Отсутствие** `arguments` (`arguments` содержит список аргументов с которым обычная функция была вызвана)
- **Можно кратко вернуть значение** если стрелочная функция выглядит так:
  `const increment = (num) => num + 1`
- **В классах не нужна привязка к this** (то-есть не нужно писать дополнительную функцию bind, например: `batman.logName.bind(batman)`)
- Стрелочные функции **не имеют атрибута прототипа.**

### Объясните, что такое файлы cookie в JavaScript.

- Это данные, **хранящиеся в небольших текстовых файлах** на вашем компьютере.
- Куки обычно устанавливаются веб-сервером при помощи заголовка `Set-Cookie`.
- Один из наиболее **частых случаев использования** куки – это **аутентификация**.

### В чем смысл и польза указания `use strict` в начале JavaScript-файла?

- Команда `use strict` включает так называемый **строгий режим**. В этом режиме **предупреждения становятся ошибками.**

### Почему запись function foo(){}() вызывает ошибку и не работает?

- Потому что **вызов декларативной функции** при ее создании **невозможен**, но это можно обойти, если вызов будет следовать за функциональным выражением. Поэтому мы должны либо **прибегнуть к варианту с присвоения к переменной**, либо **обернуть Function Declaration в скобки**, тем **самым превратив её в функциональное выражение.**

![declarativeFunction](declarativeFunction.png)

### Что такое SPA?

- _Single Page Application_ - это веб-приложение или веб-сайт, использующий **единственный HTML-документ** как оболочку для всех веб-страниц и организующий взаимодействие с пользователем через **динамически подгружаемые HTML, CSS, JavaScript.**

### Что такое функция высшего порядка?

- Это **функция, которая оперирует другими функциями**: принимает их как входные параметры или возвращает в качестве выходных.

### Что произойдет в результате выражения const `foo = 10 + "20"` и почему?

- Переменная foo примет значение "1020"
- В JavaScript(ну и в других ЯП) это поведение называется **приведением типов.**

### Что такое IIFE?

- Immediately Invoked Function Expression — это функция, которая **вызывается и выполняется сразу же после создания** или объявления.

### Почему функции в JS называют объектами первого класса (First-class Objects)?

- Потому что они **обрабатываются также**, **как и любое другое значение** в JS.
- Важным **отличием** функции **является то**, что **функция может быть выполнена или вызвана**.

### Что такое объект Set?

- Объект Set **позволяет хранить уникальные значения**.

![setJS](setJS.png)

### Что выводят эти выражения?

- `false + true => 1` (`false` преобразуется в `0`, а `true` в `1`)
- `6 \* '2' => 12`

### В чем разница между Function Declaration(классическая функция) и Function Expression(функциональное выражение)?

- Их определение выглядит по разному.

  **В Function Declaration:** `function funcName () {}`

  **В Function Expression:** `const funcName = function () {} или const funcName = () => {}`

- Механизм поднятия в JS не срабатывает для Function Expression.

### Что такое объект Map?

- это **коллекция ключ/значение**, как и `Object`. Но основное отличие в том, что Map позволяет использовать ключи любого типа(даже объекты!)

### Расскажите о пирамиде тестирования.

- Это **один из способов обеспечения качества ПО**, **визуализация**, которая помогает группировать тесты по типу их назначения.

![](testingPyramid.png)

### Что такое temporal dead zone(Временная мертвая зона)?

- Так как JS идет сверху вниз, то **переменные**, **которые должны быть определены** ниже, **попадают в мертвую зону**, до того момента **пока они не определятся.**

### Как работает boxing / unboxing в JavaScript?

- Итак, методы – это **свойства объектов**, в которые записаны функции. **Тогда почему работает такой код?** `'hexlet'.toUpperCase()`
- Можно сделать **ошибочный вывод что строка это тоже объект**.
- На самом деле, **для каждого такого типа существует собственный конструктор** "упаковывающий"примитивный тип в объект. выглядит это так:

```js
const name = new String('hexlet'); // or: const name = 'hexlet’.toString()
```

- **Распаковка** в свою очередь **происходит с помощью метода** `valueOf()`, который автоматически вызывает JavaScript и **который можно вызвать самому**.
- В отличии от упаковки, **распаковка выполняется абсолютно для всех объектов**. Это позволяет определять `valueOf()` самостоятельно (этим пользуются многие библиотеки)

### String() vs toString()

- `toString()` не будет работать с `undefined` или `null`, потому что класс этих объектов не реализовал метод `toString()`
- А поскольку String **является независимым объектом**, а не методом, унаследованным от прототипа, то **его можно использовать с объектами, у которых нет метода** `toString()`

### Что такое Garbage Collector(Сборщик мусора)?

- Основной концепцией управления памятью в JavaScript является **принцип достижимости**. Достижимы считаются те, которые доступны или используются. Они гарантированно находятся в памяти.
- **Чтобы объект стал недостижимым нужно удалить на него все ссылки**, после того как он станет недостижимым он удаляется из памяти.
- \* Основной алгоритм сборки мусора называется «алгоритм пометок»:
  - Сборщик мусора «помечает»(запоминает) все корневые объекты.
  - Затем он идёт по ним и «помечает» все ссылки из них.
  - Затем он идёт по отмеченным объектам и отмечает их ссылки.
  - Все посещенные объекты запоминаются, чтобы в будущем не посещать один и тот же объект дважды.
  - …И так далее, пока не будут посещены все достижимые (из корней)ссылки.
  - Все непомеченные объекты удаляются.

### В чем разница между Promise.all() и Promise.allSettled()?

- `Promise.all` возвращает **массив значений от всех промисов.**
- `Promise.allSettled` возвращает **массив с объектами**, в которых находятся `status`, а также `value`, при разрешении промиса или `reason` при ошибке.

### Что такое дескрипторы свойств объектов?

- Помимо значения value, **свойства объекта имеют три специальных атрибута дескрипторов**:
  1. **writable** – если true, свойство можно изменить, иначе оно только для чтения.
  2. **enumerable** – если true, свойство перечисляется в циклах, в противном случае циклы его игнорируют.
  3. **configurable** – если true, свойство можно удалить, а эти атрибуты можно изменять, иначе этого делать нельзя.
- Их значения можно получить с помощью:
  1. Специальных методов по типу `Object.freeze()`
  2. `Object.getOwnPropertyDescriptor(obj, propName)`
  3. `Object.getOwnPropertyDescriptors(obj)`
  4. Статья <https://learn.javascript.ru/property-descriptors>

### Расскажите о генераторах. Расскажите о типе данных Symbol и его практическом применении

- Новый вид функций в современном JavaScript. Они отличаются от обычных тем, что **могут приостанавливать свое выполнение**, **возвращать промежуточный результат** и **затем снова возобновлять его позже**, в произвольный момент времени.
- Статья <https://learn.javascript.ru/generator>

### Что такое V8 Engine?

- Это **высокопроизводительный движок** JavaScript и WebAssembly от Google с открытым исходным кодом, написанный на C++
- Кроме того, что отличает V8 от других движков, он применяется в популярной серверной среде Node.js.
- Для того, чтобы добиться высокой скорости выполнения программ, **V8 транслирует JS-код в более эффективный машинный код**, не используя интерпретатор.

### Что такое Event loop и как он работает?

- Идея событийного цикла очень проста. Есть **бесконечный цикл**, в котором движок JavaScript **ожидает задачи, исполняет их и снова ожидает появления новых**. Задачи из очереди исполняются по правилу «**первым пришел – первым ушел**».
- Кроме главного списка задач существуют **микрозадачи** и **макрозадачи**.
- В **микрозадачи попадают колбеки завершенных промисов**, функции внутри `queueMicrotask()`(метод, который ставит в очередь микрозадачу, которая должна быть выполнена в безопасное время).
- В **макрозадачи** попадают **колбеки планирования и обработчики событий.**
- Сначала выполняется **основной код**, затем **микрозадачи** и за ними **макрозадачи.**

### Что означает аббревиатура CORS?

- Cross-Origin Resource Sharing — механизм, **использующий дополнительные HTTP-заголовки**, **чтобы дать возможность пользователю получать разрешения на доступ** к выбранным ресурсам с сервера на источнике, отличном от того, что сайт использует в данный момент

### В чем разница между императивным и декларативным программированием?

- **Императивное** программирование — это описание того, **как ты делаешь что-то**, а **декларативное** — того, **что ты делаешь**
- Другими словами: При декларативная подходе выражается логика вычисления вместе с описанием потока управления. В императивной парадигме программирования используются утверждения, изменяющие состояние программы.

### Что такое монолитная и микро-сервисная архитектуры? их + и -

- В **микро-сервисной** архитектуре **слабо связанные сервисы взаимодействуют друг с другом для выполнения задач**, относящихся к их бизнес-возможностям.

  **Преимущества**:

  - Микросервисы меньше, и благодаря этому **их легче понять и проверить**.
  - Их **легче держать модульными**.
  - Более короткое время запуска и возможность развертывания микро-сервисов независимо друг от друга действительно **выгодны для CI / CD**.
  - Хорошо спроектированная распределенная система **переживет сбой одного сервиса**.
  - С ними легче работать<br/>

  **Недостатки**:

  - для микро-сервисов также **может потребоваться больше оборудования**, чем для традиционных монолитов.
  - **Изменения**, затрагивающие несколько сервисов, **должны координироваться между несколькими командами.**

- **Монолит** - это традиционная модель ПО, которая **представляет собой единый модуль, работающий автономно** и независимо от других приложений.

  - Преимуществом монолита является то, что его легче реализовать

  **Недостатки**:

  - В монолите практически **нет изоляции**, **проблема** или **ошибка** в модуле **может замедлить или разрушить все приложение**.
  - Сложно реализовывать новые функции.
  - Код скапливается в один большой ком грязи.

### Как работает прототипное наследование?

- **Объекты** JS **связаны цепочками прототипов** с помощью `__proto__` свойства, **по которым им передаются методы и свойства.** При обращении к свойству или методу объекта сначала происходит поиск этого свойства у самого объекта. В случае неудачи поиск перенаправляется в его прототип.
- Например, **когда мы хотим прочитать свойство** из object, **а оно отсутствует**, JavaScript **автоматически берёт его из прототипа**, если оно существует.

### Как преобразовать двумерный массив в объект?

```js
Object.fromEntries([
  ['foo', 10],
  ['baz', 'by'],
]); // output - { foo: 10, baz: ‘fy’ }
```

### Что нового привнес в JS стандарт ES6?

1. Решена проблема с var
2. IIFE (это понятие озвучивалась выше)
3. Многострочные строки
4. Деструктуризация
5. Классы и объекты
6. Наследование
7. Промисы
8. Параметры по умолчанию
9. Rest и Spread операторы
10. `for-of` итератор
11. Стрелочные функции
12. Прокси
13. Symbol
14. Ну и другие менее интересные штучки

### Как проверить, что число является четным, без использования деления по модулю или деления с остатком (оператора "%")?

- Для решения данной задачи можно использовать оператор ≪&≫ (бинарное и). Оператор ≪&≫ сравнивает операнды как бинарные значения:

```js
const isEven = num & 1 ? false : true; // even - четное
```

### Что такое шаблонные литералы?

- Шаблонными литералами называются строковые литералы, **допускающие использование выражений внутри**. ВJS их можно использовать в обратных кавычках с помощью `${}`.

### Как коротко поменять значения местами?

![changeVarsTogether](changeVarsTogether.png)

### Как использовать деструктуризацию массива?

![array destructurization](arrayDestructurization.png)

### Что такое аксессоры?

- Это способы доступа к свойствам объекта, например используя точечную и скобочную записи.

### Что делает оператор ~ (тильда)?

- Выражение `~n` эквивалентно выражению `-n-1`, например, `~15 === -16`

* Преобразует строку в число.

### Какой самый быстрый способ округления?

- побитовое ИЛИ ≪|≫.

```js
const a = 23.9 | 0; // a === 23

const b = -23.9 | 0; // b === -23
```

### Что означают и делают два вопросительных знака ≪??≫?

- Знак называется **“Оператор объединения с нулевым значением”**.
- Это **логический оператор**, который **возвращает его правый операнд**, если его левый операнд равен `null` или `undefined`

### Какой самый быстрый способ получить последний элемент массива?

- `array.slice(-1)`

### Зачем нужен конструктор Proxy? Приведите пример использования.

- Объект Proxy «оборачивается» вокруг другого объекта и **может перехватывать разные действия** с ним, чтение/запись свойств, брать полное управление над действиями.
- Будет полезно для того чтобы воспроизводить **побочные эффекты**; **управлять возвращаемым значением свойства объекта**; **ставить ловушки**, которые сработают при определенных условиях и **вызовут ошибку.**

### Что такое функция обратного вызова (Callback Function)?

- Это функция, **вызов** которой **отложен на будущее** (происходит при некоторых условиях, например, при наступлении события)

### Что такое Tag-функции?

- это функции которые работают со строковыми литералами, имеют форму записи:

```js
gql`query {...}`;
```

Подробнее <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals>
