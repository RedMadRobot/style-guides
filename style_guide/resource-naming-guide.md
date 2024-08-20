# RFC 1: Правила именования ресурсов

## Соглашения

::: naming
constant part
<p class="note">Предопределённые части названия, которые диктуются спецификой android разработки и никогда не меняются</p>

<span class="req">required part</span>
<p class="note">Часть названия, которая задается в зависимости от условий использования</p>

<span class="opt">optional part</span>
<p class="note">Часть, которая добавляется при необходимости что-либо уточнить</p>
:::

## Рефакторинг

Если после рефакторинга ресурс перестает принадлежать какому-то функционалу, он должен быть переименован в соответствии с этими правилами.
Например иконка называлась `auth_key_icon`, но потребовалось использовать ее вне сценария авторизации.
Такая иконка должна быть переименована в `key_icon`.
Если архитектура приложения подразумевает разделение на модули, нужно перенести переименованную иконку в соответствующий модуль.

## Правила именования
### Animation ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
<span class="req">[what i do]</span><span class="opt">_[duration/speed/etc]</span>
:::

Примеры:
- `fade_out`
- `slide_up`

### Color ![Static Badge](https://img.shields.io/badge/on_hold-yellow)

::: naming
<span class="req">[designer's color name]</span>
<p class="note">Цвет из Miro или дизайн системы</p>

<span class="req">[color]</span><span class="opt">\_opacity_[opacity percent]</span>
<p class="note">Любой цвет</p>

<span class="req">[color place]\_[color]</span><span class="opt">\_opacity_[opacity percent]</span>
<p class="note">Цвет, который привязан к какому-то конкретному элементу интерфейса</p>
:::

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

::: naming
<span class="req">[Designer's color name]</span>
<p class="note">Цвет из Miro/Figma или дизайн системы</p>

<span class="req">[Color]</span><span class="opt">\_[opacity percent]</span>
<p class="note">Любой цвет, который также может обладать определенной прозрачностью</p>

<span class="req">[Color][Dark/Light postfix]</span><span class="opt">\_[opacity percent]</span>
<p class="note">Цвет, который встречается в более светлом/темном виде можно выделить ключевыми словами</p>

<span class="req">[Color place]\[Color]</span><span class="opt">\_[opacity percent]</span>
<p class="note">Цвет, который привязан к какому-то конкретному элементу интерфейса</p>
:::

Примеры:
- `Grey`
- `GreyLight`
- `Red_90`
- `ShimmerPrimary`

### Drawable ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
icon/shape/image/selector_<span class="req">[what i show]</span><span class="opt">\_[size_dp]</span>
<p class="note">Drawable-ресурс, который используется повсеместно в приложении</p>

<span class="req">[feature]\_</span>icon/shape/image/selector<span class="req">\_[what i show]</span><span class="opt">\_[size_dp]</span>
<p class="note">Drawable-ресурс, который используется только в рамках какого-то функционала</p>
:::

Примеры:
- `icon_arrow`
- `shape_search_result_background`
- `auth_icon_key`

### Drawable (Compose)

В Compose Drawable-ресурсы описываются в отдельном object.

::: naming
<span class="req">[App name][Illustration/Icon]</span>
<p class="note">Название object в котором описываются Drawable-ресурсы</p>
:::

Примеры:
- `KnowledgeBaseIcon`
- `KnowledgeBaseIllustration`

::: naming
<span class="req">[What i show]</span><span class="opt">\_[size_dp]</span>
<p class="note">Drawable-ресурс, который используется повсеместно в приложении</p>

<span class="req">[Feature]</span>icon/shape/image/selector<span class="req">[What i show]</span><span class="opt">\[size_dp]</span>
<p class="note">Drawable-ресурс, который используется только в рамках какого-то функционала</p>
:::

Примеры:
- `Delete`
- `Settings_32`
- `KnowledgeBaseLogo`

### Layout ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
activity_<span class="req">[what i do]</span>  
fragment_<span class="req">[what i do]</span>  
dialog_<span class="req">[what i do]</span>  
layout_<span class="req">[what i do]</span>  
item_<span class="req">[what i do]</span>  
view_<span class="req">[what i do]</span>  
:::

Примеры:
- `activity_main`
- `fragment_input_pin_code`
- `dialog_account_filter`
- `layout_placeholder`
- `item_user`
- `view_shimmer`

### Layout (Compose)

::: naming
<span class="req">[what i do]</span>Screen   
<span class="req">[what i do]</span>BottomSheet  
<span class="req">[what i do]</span>Layout  
<span class="req">[what i do]</span>Item   
<span class="req">[what i do]</span>Shimmer  
:::

Локальные и общие визуальные компоненты обычно именуются только по назначению, но в случае необходимости дополнить
контекст или выделить их тип можно дополнить название припиской `View`.

::: naming
<span class="req">[what i do]</span>View
:::

Примеры:
- `MainScreen`
- `InfoBottomSheet`
- `DetailsInfoLayout`
- `UserItem`
- `AmountShimmer`
- `WebView`

### View ID ![Static Badge](https://img.shields.io/badge/accepted-green)

::: tip
В параметр `[view type]` не нужно включать суффикс `_view` чтобы не захламлять название.
:::
::: naming
<span class="req">[what i contain]</span>_container
<p class="note">Любой контейнер</p>

<span class="req">[view type]\_[what i do]</span>
<p class="note">View используемая повсеместно в приложении</p>

<span class="req">[feature]\_[view type]\_[what i do]</span>
<p class="note">View используемая только в рамках какого-то функционала</p>
:::

Примеры:
- `view_pin_code`
- `button_next`
- `users_container`
- `accounts_container`
- `auth_button_login`
- `orders_text_screen_header`
- `user_profile_image_avatar`

### Menu ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
bottom_menu
<p class="note">Единственное на все приложение меню для "нижней" навигации</p>

<span class="req">[why i need]</span>_menu
<p class="note">Меню, которое используется по всему приложению</p>

<span class="req">[feature]\_[why i need]</span>_menu
<p class="note">Меню, которое используется только в каком-то конкретном функционале</p>

<span class="req">[screen]\_[why i need]</span>_menu
<p class="note">Меню, которое используется только на конкретном экране</p>
:::

Примеры:
- `role_type_menu`
- `orders_filter_menu`
- `chat_toolbar_menu`
- `profile_settings_user_role_menu`

### Menu item ID ![Static Badge](https://img.shields.io/badge/accepted-green)

::: tip
В параметр `[menu file name]` не нужно включать суффикс `_menu` чтобы не захламлять название.
:::
::: naming
<span class="req">[menu file name]_[what i show]</span>
:::

Примеры:
- `role_type_admin`
- `orders_filter_by_name`
- `chat_toolbar_call`

### Raw file ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
<span class="req">[why i need]</span>
:::

### Array ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
<span class="req">[what i contain]\_[array type]</span>_array
<p class="note">Массив элементов, который используется по всему приложению</p>

<span class="req">[feature]\_[what i contain]\_[array type]</span>_array
<p class="note">Массив элементов, который используется в каком-то конкретном функционале</p>
:::

Примеры:
- `months_string_array`
- `role_ids_string_array`
- `role_ids_int_array`
- `orders_delivery_variant_string_array`

### Dimen ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
<span class="opt">[view type]\_</span><span class="req">[dimen type]\_[dimen size]</span>
<p class="note">Размер который используется по всему приложению</p>

<span class="req">[feature]</span><span class="opt">\_[view type]</span><span class="req">\_[dimen type]\_[dimen size]</span>
<p class="note">Размер, который используется только в каком-то конкретном функционале</p>

<span class="req">[screen]</span><span class="opt">\_[view type]</span><span class="req">\_[dimen type]\_[dimen size]</span>
<p class="note">Размер, который используется только на каком-то конкретном экране</p>
:::

::: tip
`[dimen type]` может содержать как общий тип вроде `margin` или `padding`, так и более уточнённый `margin_top`.
Можно использовать суффиксы `_vertical` и `_horizontal` для описания сразу двух отступов.
:::

Примеры:
- `button_margin_8dp`
- `auth_button_margin_12dp`
- `order_info_picture_height_20dp`

### String ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
<span class="req">[what i show]\_[string type]</span>
<p class="note">Строка, которая используется по всему приложению</p>

<span class="req">[feature]\_[what i show/where i am]\_[string type]</span>
<p class="note">Строка, которая используется в каком-то конкретном функционале</p>

<span class="req">[screen]\_[what i show/where i am]\_[string type]</span>
<p class="note">Строка, которая используется на каком-то конкретном экране</p>
:::

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

::: naming
Theme.<span class="req">[app name].[theme name]</span>
<p class="note">Тема</p>

ThemeOverlay.<span class="req">[app name].[theme overlay name]</span>
<p class="note">Тема, которая определяет только некоторые атрибуты и применяется поверх активной темы</p>

Widget.<span class="req">[app name].[widget name]</span><span class="opt">.[style name]</span>
<p class="note">Стиль виджета</p>

TextAppearance.<span class="req">[app name].[text appearance name]</span>
<p class="note">Стиль текста</p>

ShapeAppearance.<span class="req">[app name].[shape appearance name]</span>
<p class="note">Стиль фигур</p>
:::

Примеры:
- `Theme.Openbank.TranslucentStatus`
- `ThemeOverlay.Openbank.Dialog`
- `Widget.Openbank.Button.Outlined`
- `TextAppearance.Openbank.Body1`
- `ShapeAppearance.Openbank.Small`

### XML file ![Static Badge](https://img.shields.io/badge/accepted-green)

::: naming
<span class="req">[why i need]</span>
:::

Примеры:
- `network_security_config.xml`

### Font file ![Static Badge](https://img.shields.io/badge/on_hold-yellow)

::: naming
<span class="req">[designer's font name]</span>
<p class="note">Стандартное имя шрифта или имя придуманное дизайнерами</p>
:::

## FAQ

**Q: Я художник! Мне не хочется думать когда я называю ресурсы, это так обязательно?**  
**A:** Это регулируется внутренними договоренностями в команде проекта.
Если команда берет на себя ответственность за хаос и за повышение порога входа для новых сотрудников, то называть ресурсы можно как угодно.

**Q: Почему в примерах написано именно так, а не иначе?
Я вот думаю нужно писать по-другому!**  
**А:** Потому что это просто примеры, они созданы для удобства понимания правил.
Если хочется, можно предложить свои.
Обсудим и заменим.
