# Kotlin Code Style

В репозитории приведен набор соглашений по оформлению кода на языке Kotlin.

Этот список правил расширяет предложенные [Google](https://android.github.io/kotlin-guides/style.html) и [командой разработки Kotlin](https://kotlinlang.org/docs/reference/coding-conventions.html) гайды и пересматривает в них некоторые неоднозначные моменты.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Длина строки](#%D0%94%D0%BB%D0%B8%D0%BD%D0%B0-%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B8)
- [Правила именования](#%D0%9F%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%B8%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)
- [Форматирование выражений](#%D0%A4%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2%D1%8B%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9)
- [Функции](#%D0%A4%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8)
  - [Функции с одним выражением](#%D0%A4%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8-%D1%81-%D0%BE%D0%B4%D0%BD%D0%B8%D0%BC-%D0%B2%D1%8B%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5%D0%BC)
  - [Именованные аргументы](#%D0%98%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%80%D0%B3%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B)
  - [Вызов переменной функционального типа](#%D0%92%D1%8B%D0%B7%D0%BE%D0%B2-%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B3%D0%BE-%D1%82%D0%B8%D0%BF%D0%B0)
  - [Форматирование лямбда-выражений](#%D0%A4%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BB%D1%8F%D0%BC%D0%B1%D0%B4%D0%B0-%D0%B2%D1%8B%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9)
- [Классы](#%D0%9A%D0%BB%D0%B0%D1%81%D1%81%D1%8B)
- [Структура класса](#%D0%A1%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D0%B0-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0)
- [Аннотации](#%D0%90%D0%BD%D0%BD%D0%BE%D1%82%D0%B0%D1%86%D0%B8%D0%B8)
- [Использование условных операторов](#%D0%98%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%BD%D1%8B%D1%85-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%B2)
- [Template header](#template-header)
- [Частые ошибки](#%D0%A7%D0%B0%D1%81%D1%82%D1%8B%D0%B5-%D0%BE%D1%88%D0%B8%D0%B1%D0%BA%D0%B8)
  - [Вызов toString() у nullable объектов](#%D0%92%D1%8B%D0%B7%D0%BE%D0%B2-tostring-%D1%83-nullable-%D0%BE%D0%B1%D1%8A%D0%B5%D0%BA%D1%82%D0%BE%D0%B2)
  - [Использование orEmpty() вместо ?:](#%D0%98%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-orempty-%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%BE-)
  - [Проверка nullable boolean](#%D0%9F%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-nullable-boolean)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Длина строки

**Рекомендуемая** длина строки: 100 символов.

**Максимальная** длина строки: 120 символов.

## Правила именования

Пакеты именуются **одним** словом в стиле lowercase. Если необходимо использовать несколько слов, то просто склеиваем их вместе.

## Форматирование выражений

При переносе на новую строку цепочки вызова методов символ `.` или оператор `?.` переносятся на следующую строку, property при этом разрешается оставлять на одной строке:

```kotlin
val collectionItems = source.collectionItems
    ?.dropLast(10)
    ?.sortedBy { it.progress }
```

Элвис оператор `?:` в многострочном выражении также переносится на новую строку:

```kotlin
val throwableMessage: String = throwable?.message
    ?: DEFAULT_ERROR_MESSAGE

throwable.message?.let { showError(it) }
    ?: showError(DEFAULT_ERROR_MESSAGE)
```

Если перед элвис оператором `?:` многострочная лямбда, желательно перенести также и лямбду:

```kotlin
// Good
throwable.message
    ?.let { message ->
        ...
        showError(message)
    }
    ?: showError(DEFAULT_ERROR_MESSAGE)
    
// Not recommended
throwable.message?.let { message ->
    ...
    showError(message)
}
    ?: showError(DEFAULT_ERROR_MESSAGE)
```

При описании переменной с делегатом, не помещающимися на одной строке, оставлять описание с открывающейся фигурной скобкой на одной строке, перенося остальное выражение на следующую строку:

```kotlin
private val promoItem: MarkPromoItem by lazy {
    extractNotNull(BUNDLE_FEED_UNIT_KEY) as MarkPromoItem
}
```

## Функции

### Функции с одним выражением

Позволительно использовать функцию с одним выражением только в том случае, если она помещается в одну строку.

### Именованные аргументы

Если по контексту не понятно назначение аргумента, то следует сделать его именованным.

```kotlin
runOperation(
    method = operation::run,
    consumer,
    errorHandler,
    tag,
    cacheSize = 3,
    cacheMode
)
calculateSquare(x = 6, y = 19)
getCurrentUser(skipCache = false)
setProgressBarVisible(true)
```

Если именованные аргументы не помещаются на одной строке, то следует переносить каждый аргумент на новую строку (как в примере выше).

Именуем все лямбды, принимаемые функцией в качестве аргументов (кроме случаев когда лямбда вынесена за круглые скобки),
чтобы во время чтения кода было понятно назначение и ответственность каждой лямбды.

```kotlin
editText.addTextChangedListener(
    onTextChanged = { text, _, _, _ -> 
        viewModel.onTextChanged(text?.toString())
    },
    afterTextChanged = { text ->
        viewModel.onAfterTextChanged(text?.toString())
    }
)
```

Полезно именовать аргументы одинаковых типов, чтобы случайно не перепутать их местами.

```kotlin
val startDate: Date = ..
val endDate: Date = ..
compareDates(startDate = startDate, endDate = endDate)
```

Полезно именовать аргумент при передаче `null`.

```kotlin
setAdditionalArguments(arguments = null)
```

### Вызов переменной функционального типа

Допускается вызов лямбды как с `invoke`, так и сокращенный вариант `()`, если отсутствуют договоренности внутри проекта. Однако явный `invoke` имеет ряд преимуществ:

> [!TIP]
> Одной из основных причин использования явного `invoke` является концептуальное разделение функции как члена класса и лямбды как входного параметра функции.
> Используя `invoke` явно, мы показываем, что используем лямбду, а не функцию.
> 
> При этом дополнительным аргументом к использованию `invoke` является его заметность. Вызывая лямбду без `invoke`, у нее можно потерять скобки в месте вызова, что приведет к некорректному поведению.

```kotlin
@Composable
fun ProfileScreenContent(
  header: @Composable LazyItemScope.() -> Unit,
  body: @Composable LazyListScope.() -> Unit,
  footer: @Composable LazyItemScope.() -> Unit,
) {
  LazyColumn {
    item(content = header)
    
    // Bad
    body
    // Good
    body()
    body.invoke(this@LazyColumn)
    
    item(content = footer)
  }
}
```

### Форматирование лямбда-выражений

По возможности передавать метод по ссылке:

```kotlin
viewPager.adapter = QuestAdapter(quest, onQuestClickListener = ::onQuestClicked)
```

При написании лямбда-выражения более чем в одну строку всегда использовать именованный аргумент, вместо `it`:

```kotlin
viewPager.adapter = QuestAdapter(
    quest, 
    onQuestClickListener = { quest ->
        Log.d(..)
        viewModel.onQuestClicked(quest)
    }
)
```

Неиспользуемые параметры лямбда-выражений всегда заменять символом `_`.

## Классы

Если описание класса не помещается в одну строку, и класс реализует несколько интерфейсов, то применять стандартные правила переноса, 
т.е. делать перенос только в случае, когда описание не помещается на одну строку, при этом продолжать перечисление интерфейсов на следующей строке.

```kotlin
class MyFavouriteVeryLongClassHolder : MyLongHolder<MyFavouriteVeryLongClass>(), SomeOtherInterface, AndAnotherOne,
    OneMoreVeryLongInteface, OneMore{

    fun foo() { /*...*/ }
}
```

Использование именованных аргументов [аналогично с функциями](#%D0%B8%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%80%D0%B3%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B)

## Структура класса

1) Поля: abstract, override, public, internal, protected, private
2) Блок инициализации: init, конструкторы
3) Абстрактные методы
4) Переопределенные методы родительского класса (желательно в порядке их следования в родительском классе)
5) Реализации методов интерфейсов (желательно в порядке добавления интерфейсов в класс и следования методов в каждом интерфейсе)
6) Методы класса ([в логическом порядке](https://kotlinlang.org/docs/coding-conventions.html#class-layout). Например, метод располагается после того, в котором впервые упомянут). Можно перемешивать с методами из пунктов 3, 4, 5.
7) inner классы
8) companion object

## Аннотации

Аннотации располагаются над описанием класса/поля/метода, к которому они применяются.

Если к классу/полю/методу применяется несколько аннотаций, размещать каждую аннотацию с новой строки:

```kotlin
@JsonValue
@JvmField
var promoItem: PromoItem? = null
```

Аннотации к аргументам в конструкторе класса или объявлении функции можно писать на той же строке, что и соответствующий аргумент.  
При этом если аннотаций к одному аргументу несколько, то все аннотации пишутся с новой строки, и соответствующий аргумент отделяется от других сверху и снизу пустыми строками.

```kotlin
data class UserInfo (
    @SerializedName("firstName") val firstName: String? = null,
    @SerializedName("secondName") val secondName: String? = null
)

@Entity(tableName = "users")
data class UserInfo (
    @PrimaryKey val id: Int,
    
    @SerializedName("firstName") 
    @ColumnInfo(name = "firstName") 
    val firstName: String? = null,
    
    @SerializedName("secondName") 
    @ColumnInfo(name = "secondName") 
    val secondName: String? = null
)
```

## Использование условных операторов

Не обрамлять `if` выражения в фигурные скобки только если условный оператор `if` помещается в одну строку.  
По возможности использовать условные операторы, как выражение:

```kotlin
return if (condition) foo() else bar()
```

В операторе `when` ветки, состоящие более чем из одной строки, обрамлять фигурными скобками и отделять от других case-веток пустыми строками сверху и снизу.

```kotlin
when (feed.type) {
    FeedType.PERSONAL -> startPersonalFeedScreen()
    
    FeedType.SUM -> {
        showSumLayout()
        hideProgressBar()
    }
    
    FeedType.CARD -> startCardFeedScreen()
    else -> showError() 
}
```

## Template header

Не использовать Template Header для классов (касается авторства и даты создания файла).

## Частые ошибки

### Вызов toString() у nullable объектов

В первом примере получится строчка `"null"`, это плохо. 
Необходимо сделать так, чтобы в таком случае возвращалась пустая строка `""`

```kotlin
binding.authInputPassword.addTextChangeListener { editable: Editable? ->
    // Bad
    viewModel.onPasswordChanged(editable.toString())
    
    // Good
    viewModel.onPasswordChanged(editable?.toString().orEmpty())
}
```

### Использование orEmpty() вместо ?:

Для коллекций и строк использовать `orEmpty()`.

```kotlin
// Bad
nullableString ?: ""
nullableObject?.toString() ?: ""
someList ?: emptyList()

// Good
nullableString.orEmpty()
nullableObject?.toString().orEmpty()
someList.orEmpty()
```

### Проверка nullable boolean

При проверке nullable boolean вместо добавления `?: false` в условии явно проверять `boolean == true`  
Это одна из общепринятных [идиом](https://kotlinlang.org/docs/idioms.html#nullable-boolean) Kotlin.

```kotlin
// Bad
val b: Boolean? = ...
if (boolean ?: false) {
    ...
} else {
    // `b` is false or null
}

// Good
val b: Boolean? = ...
if (b == true) {
    ...
} else {
    // `b` is false or null
}
```
