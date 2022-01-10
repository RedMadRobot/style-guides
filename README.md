# Kotlin Code Style

В репозитории приведен набор соглашений по оформлению кода на языке Kotlin. 

Этот список правил расширяет предложенные [Google](https://android.github.io/kotlin-guides/style.html) и [командой разработки Kotlin](https://kotlinlang.org/docs/reference/coding-conventions.html) гайды и пересматривает в них некоторые неоднозначные моменты.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Длина строки](#%D0%B4%D0%BB%D0%B8%D0%BD%D0%B0-%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B8)
- [Правила именования](#%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%B8%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)
- [Форматирование выражений](#%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2%D1%8B%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9)
- [Функции](#%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8)
  - [Функции с одним выражением](#%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8-%D1%81-%D0%BE%D0%B4%D0%BD%D0%B8%D0%BC-%D0%B2%D1%8B%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5%D0%BC)
  - [Именованные аргументы](#%D0%B8%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%80%D0%B3%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B)
  - [Вызов переменной функционального типа](#%D0%B2%D1%8B%D0%B7%D0%BE%D0%B2-%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B3%D0%BE-%D1%82%D0%B8%D0%BF%D0%B0)
  - [Форматирование лямбда-выражений](#%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BB%D1%8F%D0%BC%D0%B1%D0%B4%D0%B0-%D0%B2%D1%8B%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9)
- [Классы](#%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D1%8B)
- [Структура класса](#%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D0%B0-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0)
- [Аннотации](#%D0%B0%D0%BD%D0%BD%D0%BE%D1%82%D0%B0%D1%86%D0%B8%D0%B8)
- [Использование условных операторов](#%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%BD%D1%8B%D1%85-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%B2)
- [Template header](#template-header)
- [Частые ошибки](#%D1%87%D0%B0%D1%81%D1%82%D1%8B%D0%B5-%D0%BE%D1%88%D0%B8%D0%B1%D0%BA%D0%B8)
  - [Вызов toString() у nullable объектов](#%D0%B2%D1%8B%D0%B7%D0%BE%D0%B2-tostring-%D1%83-nullable-%D0%BE%D0%B1%D1%8A%D0%B5%D0%BA%D1%82%D0%BE%D0%B2)
  - [Использование orEmpty() вместо ?:](#%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-orempty-%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%BE-)
  - [Проверка nullable boolean](#%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-nullable-boolean)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


# Длина строки
- **Рекомендуемая** длина строки: 100 символов.
- **Максимальная** длина строки: 120 символов.

# Правила именования
- Пакеты именуются **одним** словом в стиле lowercase. Если же необходимо использовать несколько слов, то именовать пакет в стиле lower_snake_case.

# Форматирование выражений
- При переносе на новую строку цепочки вызова методов символ `.` или оператор `?.` переносятся на следующую строку, property при этом разрешается оставлять на одной строке:
```kotlin
val collectionItems = source.collectionItems
    ?.dropLast(10)
    ?.sortedBy { it.progress }
```
- Элвис оператор `?:` при разрыве выражения также переносится на новую строку:
```kotlin
val promoItemDistanceTradeLink: String = promoItem.distanceTradeLinks?.appLink
    ?: String.EMPTY
```
- При описании переменной с делегатом, не помещающимися на одной строке, оставлять описание с открывающейся фигурной скобкой на одной строке, перенося остальное выражение на следующую строку:
```kotlin
private val promoItem: MarkPromoItem by lazy {
    extractNotNull(BUNDLE_FEED_UNIT_KEY) as MarkPromoItem
}
```

# Функции
## Функции с одним выражением
- Позволительно использовать функцию с одним выражением только в том случае, если она помещается в одну строку.

## Именованные аргументы
- Если аргументов больше 3х, то следует их именовать.
```kotlin
runOperation(
    method = operation::run,
    consumer = consumer,
    errorHandler = errorHandler,
    tag = tag,
    cache = cache,
    cacheMode = cacheMode
)
```
- Если именованные аргументы не помещаются на одной строке, то следует переносить каждый аргумент на новую строку (как в примере выше).
- Если аргументов 3 или меньше, то необязательно именовать все аргументы. При этом именованные аргументы должны идти в конце. 
```kotlin
val date: Date = ..
savePaymentData(date, cost = 100)
```
- Если функция принимает несколько аргументов одного и то же типа, 
то стоит именовать эти аргументы при вызове данной функции, чтобы случайно не перепутать их местами.
```kotlin
val startDate: Date = ..
val endDate: Date = ..
compareDates(startDate = startDate, endDate = endDate)
```
- Именуем все лямбды, принимаемые функцией в качестве аргументов (кроме случаев когда лямбда вынесена за круглые скобки),
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
- Именовать аргументы примитивных типов.   
При этом если аргумент один, и из контекста вызова функции понятно для чего он нужен, то можно его не именовать.
```kotlin
calculateSquare(x = 6, y = 19)
getCurrentUser(skipCache = false)
setProgressBarVisible(true)
```
- Именовать аргумент при передаче `null`.
```kotlin
setAdditionalArguments(arguments = null)
```

## Вызов переменной функционального типа
- Всегда использовать полный вариант с написанием `invoke` у переменной вместо использования сокращенного варианта:
```kotlin
fun runAndCall(expression: () -> Unit): Result {
    val result = run()
    
    //Bad
    expression()
    //Good
    expression.invoke()
    
    return result
}
```

## Форматирование лямбда-выражений
- По возможности передавать метод по ссылке:
```kotlin
viewPager.adapter = QuestAdapter(quest, onQuestClickListener = ::onQuestClicked)
```
- При написании лямбда-выражения более чем в одну строку всегда использовать именованный аргумент, вместо `it`:
```kotlin
viewPager.adapter = QuestAdapter(
    quest, 
    onQuestClickListener = { quest ->
        Log.d(..)
        viewModel.onQuestClicked(quest)
    }
)
```
- Неиспользуемые параметры лямбда-выражений всегда заменять символом `_`.


# Классы
- Если описание класса не помещается в одну строку, и класс реализует несколько интерфейсов, то применять стандартные правила переноса, 
т.е. делать перенос только в случае, когда описание не помещается на одну строку, при этом продолжать перечисление интерфейсов на следующей строке.
```kotlin
class MyFavouriteVeryLongClassHolder : MyLongHolder<MyFavouriteVeryLongClass>(), SomeOtherInterface, AndAnotherOne,
    OneMoreVeryLongInteface, OneMore{

    fun foo() { /*...*/ }
}
```
- Использование именованных аргументов [аналогично с функциями](#%D0%B8%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%80%D0%B3%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B)

# Структура класса
1) Поля: abstract, override, public, internal, protected, private
2) Блок инициализации: init, конструкторы
3) Абстрактные методы
4) Переопределенные методы родительского класса (желательно в том же порядке, в каком они следуют в родительском классе)
5) Реализации методов интерфейсов (желательно в том же порядке, в каком они следуют в описании класса, соблюдая при этом порядок описания этих методов в самом интерфейсе)
6) Методы класса (в логическом порядке выбранном для этого класса. Например, метод распологается следующим за тем, в котором впервые упоминается). 
7) inner классы
8) companion object

# Аннотации
- Аннотации располагаются над описанием класса/поля/метода, к которому они применяются.
- Если к классу/полю/методу применяется несколько аннотаций, размещать каждую аннотацию с новой строки:
```kotlin
@JsonValue
@JvmField
var promoItem: PromoItem? = null
```
- Аннотации к аргументам в конструкторе класса или объявлении функции можно писать на той же строке, что и соответствующий аргумент.  
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

# Использование условных операторов
- Не обрамлять `if` выражения в фигурные скобки только если условный оператор `if` помещается в одну строку.  
По возможности использовать условные операторы, как выражение:
```kotlin
return if (condition) foo() else bar()
```
- В операторе `when` ветки, состоящие более чем из одной строки, обрамлять фигурными скобками и отделять от других case-веток пустыми строками сверху и снизу.
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

# Template header
- Не использовать Template Header для классов (касается авторства и даты создания файла).

# Частые ошибки

## Вызов toString() у nullable объектов
- В первом примере получится строчка `"null"`, это плохо. 
Необходимо сделать так, чтобы в таком случае возвращалась пустая строка `""`
```kotlin
binding.authInputPassword.addTextChangeListener { editable: Editable? ->
    // Bad
    viewModel.onPasswordChanged(editable.toString())
    
    // Good
    viewModel.onPasswordChanged(editable?.toString().orEmpty())
}
```

## Использование orEmpty() вместо ?:
- Для коллекций и строк использовать `orEmpty()`.
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

## Проверка nullable boolean
- При проверке nullable boolean вместо добавления `?: false` в условии явно проверять `boolean == true`  
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
