### This:

- В глобальном контексте this ссылается на window
- При 'use strict' this в функции = undefined а без 'use strict' ссылается на window
- Если функция вызывается как метод объекта, то этот объект становится значением this
- Внутри setTimeout this ссылается на window
- В обработчиках событий this ссылается на элемент который вызвал событие

### Answers

- **strict mode** - если попытаемся присвоить Math.Pi новое значение, объявление переменной без ключевых слов, this в функции = undefined а без 'use strict' ссылается на window
- **Что такое прототип (Prototype) объекта?** - это как резерв свойств и методов
- **HOF** - функция, которая принимает другую функцию или возвращает функцию (map, forEach ext)
- **Как превратить любой тип данных в булевый?** Перечислите ложные значения в JS? - Bollean or !!. '' null undefined 0 NaN false
- **Чистая функция** - никаких side-effects (DOM, HTTP запросы)
- **Почему в JS функции называют объектами первого класса?** - потому что функция ведет себя как обычный объект. Едиственное отличие это то, что ее можно вызвать и она вернет результат
- **Как определить наличие свойства в объекте?** - hasOwnProperty, in, obj['prop'] если нет, то undefined
- **Разница между host-объектами и нативными объектами?** - host-объекты это такие объекты, которые нам предоставлет браузер или NodeJs (Window, document, location, history, setTimeout)
- **Как создать объект без прототипа?** - Object.create(null)
- **Как работает boxing/unboxing в JavaScript?** - boxing это когда упаковываем наш примитив в объект. Ручками или под капотом. Unboxing это когда из объекта делаем примитив (toString)
- **Разница между оператором in и методом hasOwnProperty?** - in проверяет в прототипах
- **Что такое цепочка вызовов функций (chaining)? Как реализовать такой подход?** - это подход, при котором методы объекта вызываются один за другим. Нужно сделать объект, методы которого будут возвращать this
- **Как работают методы find(), findIndex() и indexOf()?** - find->принимает колбэк, возвращает первый подходящий элемент. findIndex()-> возращает индекс.  indexOf() принимает не колбэк, а искомый элмент
- **Типы всплывающих окон в JavaScript?** - alert (just message), confirm (ok and cancel), propmt (input, ok, cancel)
- **Типы объектов JavaScript?** - Array, String, Number, Bollean, Math, Date, RegExp, Object, Function
- **Какие методы используются в регулярных выражениях?** - test and exec (ищет совпадения регулярке в строке, работа зависит от флага g. Если он установлен, то метод возвращает первое совпадение и сохраняет текущую позицию в /[A-B]/.lastIndex. Следующий вызов начнется уже с этого индекса
- **сравнение объектов** - в json
- **call, apply, bind** - привязывают контекст к FD. К AF они привязать контекст не могут, поэтому в объекте обычные функции (методы) они как бы привязаны с помощью этих функций (поэтому this в AF в объекте относится к глобальной области видимости)

### Notes

- Object.assign - простое копирование объекта
 - ?? - оператор нулевого слияния
- this - Для доступа к информации внутри объекта метод может использовать ключевое слово this.
- Object.is(NaN, NaN) === true
- Map – коллекция пар ключ-значение. Что угодно может быть ключом, в том числе и объекты.
- WeakMap/Set - Наиболее значительным ограничением WeakMap и WeakSet является то, что их нельзя перебрать или взять всё содержимое. 
- Деструктурирующее присваивание – это специальный синтаксис, который позволяет нам «распаковать» массивы или объекты в несколько переменных
- Чтобы изменить флаги, мы можем использовать метод Object.defineProperty.
- Object.freeze - Запрещает добавлять/удалять/изменять свойства. seal - Запрещает добавлять/удалять свойства.
- Прототип используется только для чтения свойств. Операции записи/удаления работают напрямую с объектом.
- Цикл for..in проходит не только по собственным, но и по унаследованным свойствам объекта.
- Create, GetPrototypeOf, SetPrototypeOf
- Статические свойства и методы наследуются.
- Используя специальное свойство new.target внутри функции, мы можем проверить, вызвана ли функция при помощи оператора new или без него.
- Символы имеют два основных варианта использования: «Скрытые» свойства объектов. Для изменения скртых свойств, например Symbol.iterator
- Каррирование — это преобразование функции n аргументов в последовательность n функций, принимающих только один аргумент. Когда значения одних аргументов доступны раньше других, ты можешь использовать каррирование для декомпозиции функции на ряд функций. Они выполняют работу поэтапно по мере поступления каждого значения.
- Вариативная функция — это функция, общее количество параметров которой неизвестно.
- Глобальный объект включает в себя как встроенные объекты, например, Array, так и характерные для окружения свойства, например, window.innerHeight – высота окна браузера.
- Функции, объявленные через new Function, имеют [[Environment]], ссылающийся на глобальное лексическое окружение, а не на родительское.
- Оператор instanceof позволяет проверить, к какому классу принадлежит объект, с учётом наследования. (arr -> Array, Object)
- стрелочные функции -  Не имеют this. Не имеют arguments. Не могут быть вызваны с new.
- Мы можем наследовать свои классы ошибок от Error и других встроенных классов ошибок, но нужно позаботиться о свойстве name и не забыть вызвать super.
- Promise – это специальный объект в JavaScript, который связывает «создающий» и «потребляющий» (then, catch, finaly) коды вместе. 
- Cостояние promise — вначале "pending" («ожидание»), потом меняется на "fulfilled" («выполнено успешно») при вызове resolve или на "rejected" («выполнено с ошибкой») при вызове reject.
- Promise API - all, allSettled, race, any (1st успешный или масив ошибок), resolve, reject
- Промисификация – это длинное слово для простого преобразования. Мы берём функцию, которая принимает колбэк и меняем её, чтобы она вместо этого возвращала промис.
- Обработчики промисов .then/.catch/.finally всегда асинхронны, даже если Promise.resolve(10)
- Генераторы является перебираемыми (for of, spread)
- Модуль – это просто файл. Один скрипт – это один модуль. - Всегда «use strict», Своя область видимости переменных, В модуле «this» не определён (window outside module)

### HTML / JS

- Внутри обработчика события this ссылается на текущий элемент, то есть на тот, на котором, как говорят, «висит» (т.е. назначен) обработчик.
- addEventListener может начесть несколько одинаковых событий
- событие focus не всплывает
- stopPropagation() объекта Event прекращает дальнейшую передачу текущего события (предотвращает всплытие по дереву DOM).
- Коллекция childNodes содержит список всех детей, включая текстовые узлы.
- Array.from создаст массив из коллекции
- Почти все DOM-коллекции, за небольшим исключением, живые. Другими словами, они отражают текущее состояние DOM.
- Для всех узлов: parentNode, childNodes, firstChild, lastChild, previousSibling, nextSibling.
- Только для узлов-элементов: parentElement, children, firstElementChild, lastElementChild, previousElementSibling, nextElementSibling.
- Все методы "getElementsBy*" возвращают живую коллекцию. Такие коллекции всегда отражают текущее состояние документа и автоматически обновляются при его изменении.
- querySelectorAll возвращает статическую коллекцию. Это похоже на фиксированный массив элементов.
- elem.matches(css) - соотвествует ли, elem.closest(css) - ближайший предок, elemA.contains(elemB)
- eventTarget -> node -> Text | Element | Comment -> HtmlElement | SVGElement
- tagName (есть только у элементов Element) и nodeName (у всех Node)
- Свойство outerHTML содержит HTML элемента целиком. Это как innerHTML плюс сам элемент
- С innerHTML вставка происходит «как HTML», со всеми HTML-тегами.
- elem.hasAttribute(name), elem.getAttribute(name), elem.setAttribute(name, value), elem.attributes, elem.removeAttribute(name)
- dataset нестандартный атрибут
- before, prepend, append, after
- insertAdjacentHTML/Text/Element - beforebegin, afterbegin, beforeend, afterend
- Для удаления узла есть методы node.remove().
- Вызов elem.cloneNode(true) создаёт «глубокий» клон элемента – со всеми атрибутами и дочерними элементами. Если мы вызовем elem.cloneNode(false), тогда клон будет без дочерних элементов.
- Чтобы отменить действие браузера по умолчанию, используйте event.preventDefault() или return false. Второй метод работает, только если обработчик назначен через on<событие>.
- У жизненного цикла HTML-страницы есть три важных события: DOMContentLoaded, load, beforeunload/unload
- У async и defer есть кое-что общее: они не блокируют отрисовку страницы.
- async - Остальные скрипты не ждут async, и скрипты c async не ждут другие скрипты. Ждёт DOMContentLoaded 
- Динамически загружаемые скрипты по умолчанию ведут себя как «async».
- синхронный код -> микрозадачи ->макрозадачи
- fetch - text. json. blob, formData, arrayBuffer
- заголовки, которые мы не можем установить: Access-Control-Request-Headers, Access-Control-Request-Method, Connection, Content-Length, Cookie, Date, Origin