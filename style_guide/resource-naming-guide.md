# RFC 1: Правила именования ресурсов

## Соглашения

constant part  
Предопределённые части названия, которые диктуются спецификой android разработки и никогда не меняются

**required part**  
Часть названия, которая задается в зависимости от условий использования

*optional part*  
Часть, которая добавляется при необходимости что-либо уточнить

## Рефакторинг

Если после рефакторинга ресурс перестает принадлежать какому-то функционалу, он должен быть переименован в соответствии с этими правилами.
Например иконка называлась `auth_key_icon`, но потребовалось использовать ее вне сценария авторизации.
Такая иконка должна быть переименована в `key_icon`.
Если архитектура приложения подразумевает разделение на модули, нужно перенести переименованную иконку в соответствующий модуль.

## Правила именования
### Animation ![Static Badge](https://img.shields.io/badge/accepted-green)

> **[what i do]***_[duration/speed/etc]*

Примеры:
- `fade_out`
- `slide_up`

### Color ![Static Badge](https://img.shields.io/badge/on_hold-yellow)

> **[designer's color name]**  
> Цвет из Miro или дизайн системы
>
> **[color]***\_opacity_[opacity percent]*  
> Любой цвет
>
> **[color place]\_[color]***\_opacity\_[opacity percent]*  
> Цвет, который привязан к какому-то конкретному элементу интерфейса

Примеры:
- `sme_dark_grey`
- `C14`
- `brand_blue`
- `white_opacity_70`
- `divider_black_opacity_85`

### Color (Compose)

В Compose цвета описываются в отдельном object.

Пример:
- `KnowledgeBaseColor`

Цвета именуются по аналогии с формой наименования ресурсов в `color.xml`, но с использованием `CamelCase`.

> **[Designer's color name]**  
> Цвет из Miro/Figma или дизайн системы
>
> **[Color]***\_[opacity percent]*  
> Любой цвет, который также может обладать определенной прозрачностью
>
> **[Color][Dark/Light postfix]***\_[opacity percent]*  
> Цвет, который встречается в более светлом/темном виде можно выделить ключевыми словами
>
> **[Color place]\[Color]***\_[opacity percent]*  
> Цвет, который привязан к какому-то конкретному элементу интерфейса

Примеры:
- `Grey`
- `GreyLight`
- `Red_90`
- `ShimmerPrimary`

### Drawable ![Static Badge](https://img.shields.io/badge/accepted-green)

> icon/shape/image/selector_**[what i show]***_[size_dp]*  
> Drawable-ресурс, который используется повсеместно в приложении
>
> **[feature]_** icon/shape/image/selector **_[what i show]***_[size_dp]*  
> Drawable-ресурс, который используется только в рамках какого-то функционала

Примеры:
- `icon_arrow`
- `shape_search_result_background`
- `auth_icon_key`

### Drawable (Compose)

В Compose Drawable-ресурсы описываются в отдельном object.

> **[App name][Illustration/Icon]**  
> Название object в котором описываются Drawable-ресурсы

Примеры:
- `KnowledgeBaseIcon`
- `KnowledgeBaseIllustration`

> **[What i show]***_[size_dp]*  
> Drawable-ресурс, который используется повсеместно в приложении
> 
> **[Feature]**icon/shape/image/selector**[What i show]***[size_dp]*  
> Drawable-ресурс, который используется только в рамках какого-то функционала

Примеры:
- `Delete`
- `Settings_32`
- `KnowledgeBaseLogo`

### Layout ![Static Badge](https://img.shields.io/badge/accepted-green)

> activity_**[what i do]**  
> fragment_**[what i do]**  
> dialog_**[what i do]**  
> layout_**[what i do]**  
> item_**[what i do]**  
> view_**[what i do]**  

Примеры:
- `activity_main`
- `fragment_input_pin_code`
- `dialog_account_filter`
- `layout_placeholder`
- `item_user`
- `view_shimmer`

### Layout (Compose)

> [**What i do**]Screen  
> [**What i do**]BottomSheet  
> [**What i do**]Layout  
> [**What i do**]Item  
> [**What i do**]Shimmer

Локальные и общие визуальные компоненты обычно именуются только по назначению, но в случае необходимости дополнить
контекст или выделить их тип можно дополнить название припиской `View`.

> [**What i do**]View

Примеры:
- `MainScreen`
- `InfoBottomSheet`
- `DetailsInfoLayout`
- `UserItem`
- `AmountShimmer`
- `WebView`

### View ID ![Static Badge](https://img.shields.io/badge/accepted-green)

> В параметр `[view type]` не нужно включать суффикс `_view` чтобы не захламлять название.
>
> **[what i contain]**_container  
> Любой контейнер
> 
> **[view type]\_[what i do]**  
> View используемая повсеместно в приложении
>
> **[feature]\_[view type]\_[what i do]**  
> View используемая только в рамках какого-то функционала

Примеры:
- `view_pin_code`
- `button_next`
- `users_container`
- `accounts_container`
- `auth_button_login`
- `orders_text_screen_header`
- `user_profile_image_avatar`

### Menu ![Static Badge](https://img.shields.io/badge/accepted-green)

> bottom_menu   
> Единственное на все приложение меню для "нижней" навигации
>
> **[why i need]**_menu  
> Меню, которое используется по всему приложению
>
> **[feature]\_[why i need]**_menu  
> Меню, которое используется только в каком-то конкретном функционале
>
> **[screen]\_[why i need]**_menu  
> Меню, которое используется только на конкретном экране

Примеры:
- `role_type_menu`
- `orders_filter_menu`
- `chat_toolbar_menu`
- `profile_settings_user_role_menu`

### Menu item ID ![Static Badge](https://img.shields.io/badge/accepted-green)

> В параметр `[menu file name]` не нужно включать суффикс `_menu` чтобы не захламлять название.
>
> **[menu file name]_[what i show]**

Примеры:
- `role_type_admin`
- `orders_filter_by_name`
- `chat_toolbar_call`

### Raw file ![Static Badge](https://img.shields.io/badge/accepted-green)

> **[why i need]**

### Array ![Static Badge](https://img.shields.io/badge/accepted-green)

> **[what i contain]\_[array type]**_array  
> Массив элементов, который используется по всему приложению
> 
> **[feature]\_[what i contain]\_[array type]**_array  
> Массив элементов, который используется в каком-то конкретном функционале

Примеры:
- `months_string_array`
- `role_ids_string_array`
- `role_ids_int_array`
- `orders_delivery_variant_string_array`

### Dimen ![Static Badge](https://img.shields.io/badge/accepted-green)

> *[view type]\_***[dimen type]\_[dimen size]**  
> Размер который используется по всему приложению
> 
> **[feature]***\_[view type]***\_[dimen type]\_[dimen size]**  
> Размер, который используется только в каком-то конкретном функционале
> 
> **[screen]***\_[view type]***\_[dimen type]\_[dimen size]**  
> Размер, который используется только на каком-то конкретном экране

> `[dimen type]` может содержать как общий тип вроде `margin` или `padding`, так и более уточнённый `margin_top`.
> Можно использовать суффиксы `_vertical` и `_horizontal` для описания сразу двух отступов.

Примеры:
- `button_margin_8dp`
- `auth_button_margin_12dp`
- `order_info_picture_height_20dp`

### String ![Static Badge](https://img.shields.io/badge/accepted-green)

> **[what i show]\_[string type]**  
> Строка, которая используется по всему приложению
>
> **[feature]\_[what i show/where i am]\_[string type]**  
> Строка, которая используется в каком-то конкретном функционале
> 
> **[screen]\_[what i show/where i am]\_[string type]**  
> Строка, которая используется на каком-то конкретном экране

`[string type]` может принимать следующие значения:
- *title* - метки, заголовки кнопок и полей
- *description* - любые поясняющие тексты
- *hint* - подсказки для текстовых полей и потенциально для интерфейсных подсказок
- *message* - сообщения пользователю
- *error* - сообщения об ошибках
- *mask* - маски ввода
- *[custom]* - любые типы, которые требуют отдельного уточнения.
  Например url, secret и т.п.

Примеры:
- `app_name_title`
- `orders_filter_button_title`
- `login_password_hint`

### Styles and Themes ![Static Badge](https://img.shields.io/badge/on_hold-yellow)

> Theme.**[app name].[theme name]**  
> Тема
>
> ThemeOverlay.**[app name].[theme overlay name]**  
> Тема, которая определяет только некоторые атрибуты и применяется поверх активной темы
>
> Widget.**[app name].[widget name]***.[style name]*  
> Стиль виджета
>
> TextAppearance.**[app name].[text appearance name]**  
> Стиль текста
>
> ShapeAppearance.**[app name].[shape appearance name]**  
> Стиль фигур

Примеры:
- `Theme.Openbank.TranslucentStatus`
- `ThemeOverlay.Openbank.Dialog`
- `Widget.Openbank.Button.Outlined`
- `TextAppearance.Openbank.Body1`
- `ShapeAppearance.Openbank.Small`

### XML file ![Static Badge](https://img.shields.io/badge/accepted-green)

> **[why i need]**

Примеры:
- `network_security_config.xml`

### Font file ![Static Badge](https://img.shields.io/badge/on_hold-yellow)

> **[designer's font name]**  
> Стандартное имя шрифта или имя придуманное дизайнерами

## FAQ

**Q: Я художник! Мне не хочется думать когда я называю ресурсы, это так обязательно?**  
**A:** Это регулируется внутренними договоренностями в команде проекта.
Если команда берет на себя ответственность за хаос и за повышение порога входа для новых сотрудников, то называть ресурсы можно как угодно.

**Q: Почему в примерах написано именно так, а не иначе?
Я вот думаю нужно писать по-другому!**  
**А:** Потому что это просто примеры, они созданы для удобства понимания правил.
Если хочется, можно предложить свои.
Обсудим и заменим.
