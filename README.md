## Описание основных команд VIM редактора

## DEVELOP 
## MASTER

### Режимы Vim__:

1) Визуальный (по умолчанию)  
2) Режим вставки ---INSERT---  
3) Командный режим  

### Переход в режимы:

При запуске редактора по умолчанию запущен визуальный режим.  
Возврат в визуальный режим из любого другого режим клавишей - <ESC>  

В визуальном режиме можно открыть какой-нибудь файлик.  
В этом режиме курсор в форме квадратика, курсор можно наводить на текст.

Переход из визуального режима в командный режим происходит с помощью нажатия клавиши <:> (двоеточие)  
При этом курсор переходит в низ экрана редактора, где можно продолжить вводить команды.

Переход из визуального режима в режим вставки с помощью клавиш: 

`<div><i>` - курсор до символа  
`<I>` - курсор в начало строки  
`<a>` - курсор после символа  
`<A>` - курсор в конец строки  
`<s>` - с удалением символа под курсором  

Команды вводят обычно в двух режимах - визуальном и командном.

### Команды визуального режима__:

`<.>` - повтор предыдущей команды (точка)   
`<*>` - поиск одинаковых слов  
`<u>` или `<CTRL+z>` - отмена сделанных изменений  

### Команды перевода курсора

`<h>` - влево  
`<l>` - вправо (маленькая L)  
`<j>` - вниз  
`<k>` - вверх  
`<b>` - на слово влево  
`<w>` - на слово вправо  
`<W>` - до пробела вправо  
`<B>` - до пробела влево  
`<^>` или `<I><ESC>` - в начало строки  
`<$>` или `<A><ESC>` - в конец строки  
`<}>` - абзац вниз  
`<{>` - абзац вверх  
`{number}<G>` - в начало строки номер `{number}`

### Команды выделения

`<CTRL+SHIFT+V>` - Визуальный блочный режим для выделенного текста 

`<v>hjkl` - выделение с перемещением курсора   

`<fx>` - Передвинуть курсор вперед к следующему вхождению символа х в текущей строке  
`<tx>` - Передвинуть курсор вперед к следующему вхождению символа х в текущей строке и установить курсор перед символом x (можно перемещаться по тексту,  
например `<f(>`, `<f)>` - для перехода к скобочкам)  

`<V>`  - выделить строку  
`<nV>` - выделить n строк (также можно выделить курсором нужные строки и нажать <v> (они выделятся полностью))  
`<v^>` - выделить текст от позиции курсора до начала строки  
`<v$>` - выделить текст от позиции курсора до конца строки  
`<v$h>` - выделить текст от позиции курсора до конца сроки (не включая символ перевода коретки),   
необходимо, если собираемся удалить этот фрагмент, чтобы не было слияния с последующей строкой.  

#### Выделения для скобок:

`<%>`   - переход к парной скобке   
`<v%>`  - когда курсор установлен на одной из скобок - выделит всё до её пары.  
`<vib>` - выделить всё между двумя ближайшими к курсору круглыми скобками  
`<viB>` - выделить всё между двумя ближайшими к курсору фигурными скобками  

#### Выделения для кавычек: 

`<vi">` - выделяет текст внутри кавычек " (или любой другой разделитель)  
`<va">` - выделяет текст внутри кавычек " включая кавычки  
`<vt">` - выделяет текст от курсора до кавычек " не включая кавычки  
`<vf">` - выделяет текст от курсора до кавычек " включая кавычки

### Команды удаления

`<x>` - удалить символ под курсором  
`<d>` - команад удаления (после нее обычно используются дополнительные символы  
`<dl>` - удалить символ под курсором (delete letter), аналогично `<x>`  
`<dw>` - удалить  текст от курсора до конца слова (чтобы удалить слово нужно установить курсор на первую букву слова)  
`<daw>` - удалить слово под курсором  
`<dd>` - удалить строку  
`<dap>` - удалить абзац  
`<D>` - удалить текст от позиции курсора до конца строки  
`<c>` - удаление (аналогично команде `<d>`), но с переходом в режим вставки.  
`<cw>` - удалить текст от курсора до конца слова и перейти в режим вставки  
`<cw>text` - удалить и на месте удаленного фрагмента ввести текст

### Копирование и вставка

`<yy>` - Скопировать строку  
`<p>` - Вставка строки ниже текущей  
`<f>{char}` - поиск символа  
`<;>` - продолжить поиск далее по тексту  
`<CTRL+C>` - копировать текст (предварительно выделенный)  
`<CTRL+V>` - вставить текст

### Изменение текста 

`>>` - вставка отступа (аналогично табуляции)  
`<gUU>` - преобразовать строку к верхнему регистру  
`<guu>` - преобразовать строку к нижнему регистру  
`<g~~>` - изменить регистр строки (верхний в нижний и наоборот)  
`<J>`   - преобразует несколько выделенных строк в одну строку (вставляет по одному пробелу после слияния)  
`<gJ>` - преобразует несколько выделенных строк в одну строку (сливает строки как есть - удобнее!)  
`<gqq>` - формат текущей строки (согласно настройке :set tw=80) - настройка textwrap (вставка переносов строк для длинных строк)  
`<gq>` - формат строк (предварительно выделенных)

### Поиск

`/pattern<CR>` - найти следующее совпадение   
`?pattern<CR>` - найти предыдущее совпадение  
`<n>` - повтор поиска

### Разное

`<CTRL+A>` - инкремент числа под курсором (увеличение на 1)  
`<CTRL+X>` - декремент числа под курсором (уменьшение на 1)  
- команда может не работать под OS Windows - нужно вносить изменения в файл  
"mswin.vim" в корне каталога, где установлен GVIM  

**Настройка табуляции для отступов (командный режим) **  
`:set ts=4 sts=4 sw=4 noexpandtab`

**Отступы (нужно выделить кусок кода курсором) **  
`CTRL+>>` - Слева  
`CTRL+<<` - Справа


## **Полезные трюки**

### **Возможные режимы печати текста:**

`<R>` - включение режима печати с заменой  
`<r>` - заменяет символы в выделении  
Eсли выделить текст, нажать `<r>` и напечатать `<X>`,   
весь выделенный текст будет заменен на символ "X"

Вставка повторяющихся символов:  
`[num]<i>[символ]<Esc>` -  вставит [num] раз [символ],   
например: `<5iG>` напечатает "GGGGG"

**Сделать дырку в тексте из пробелов:**   
`<Ctr+Shivt+v><r><space>`   
Выделить область с текстом в визуальном блочном режиме,   
нажать `<r>`, затем `<пробел>`

### Командный режим:

**Для перехода в командный режим:**
`<__:>` или `<Esc><__:>`  

`:s/target/replacement/<CR>` - поиск и замена до первого совпадения  
`:%s/target/replacement/g<CR>` - поиск и замена в тексте  
`:'<,'>s/,$//g`  - удалить последнюю запятую в выделенном диапазоне строк  
`:'<,'>s!$!//!`   - вставить в конец каждой строки `// (двойной слеш)`, вместо `/` используется знак `!`  
(работает отлично, нужно чтобы не экранировать слеши)

### Форматирование текста

**Перенос строк:**  
`:set tw=80`  
`<gq>` - Выставляет перенос на другую строку выделенному тексту (длина строки 80 символов)  
(можно установить :set tw=1 и выполнить <gq> в этом случае каждое слово будет в отдельной строке

**Удаление лишних пробелов:**

`:'<,'>s/ +/ /g` - Удаляет лишние пробелы (оставляет только один пробел)  
`:'<,'>s/^ *//g`  - Удаляет все пробелы в начале строки  
`:'<,'>s/$ *//g`  - Удаляет все пробелы в конце строки  
`<dw>` - Удаляет пробелы между курсором и словом справа (удобно для выравнивания текста)

**Удаление пустых строк:**   
`:'<,'>g/^$/d` - Удалит пустые строки из выделенного пользователем диапазона строк  
`:'<,'>g/^ *$/d`  - Удалит пустые строки и строки, даже если в этих строках есть пробелы и нет других символов (универсальнее)

**Фоматирование кода для знаков "="** (можно для других пар - ключ значение)  
:'<,'>s/=/=              /g`  - Заменить равно на пробелы и равно (чтобы сделать сдвиг)  
далее встать в нужное место и сделать `<dw>`   
(затем если строк несколько `<j.>` - несколько раз - переход вниз `<j>` и повтор `<.>`

**Поместить каждую строку в кавычки (")**  
`:'<,'>s/^(.*)$/"\1"/g`      
Используется сохраняющая группа (в скобках) под номером 1 `(\1)`  
`(.*)` - означает сохраняющую группу, внутри которой любой символ `(.)` повтояющийся сколько угодно раз `(*)`

**Поместить каждую строку в тэг абзаца `<p>`**  
`:'<,'>s/^(.*)$/<p>\1<\/p>/g`    
Закрывающий тэг `</p>`, прямой слеш экранируется так `<\/p>`

`:'<,'>s/^(.*)$/<p>\1<\/p> \n/g`       
Аналогично предыдущей команде со вствкой пустой строки   
после каждого обзаца " \n" (пробел символ перед \n)

### Поиск

`/word`  - Искать слово “word” сверху вниз  
`?word`  - Искать слово “word” снизу вверх  
`/jo[ha]n>`  - Искать “john” или “joan”  
`/\< the`  - Искать слова, начинающееся на “the”  
`/the\>`  - Искать слова, заканчивающиеся на “the”  
`/\< the\>`  - Искать “the” (точное соответствие)  
`/\< …. \>`  -  Искать слова из четырех символов  
`/fred\|joe` - Искать “fred” или “joe”  
`/\<\d\d\d\d\>`  - Искать 4 цифры подряд  
`/^\n\{3}`  - Искать 3 пустые строки  
`:bufdo /searchstr/`  -  Искать во всех открытых файлах

### Удаление

`d^`  - Удалить все символы от текущей позиции до начала строки  
`d$`  - Удалить все символы от текущей позиции до конца строки  
`d/word`  - Удалить всё от текущей позиции до слова "word"  
`dfx`  - Удалить всё от текущей позиции до символа "x"

### Замена и очистка

`:%s/old/new/g`  - Заменить все вхождения “old” на “new”  
`:%s/old/new/gw`  - Заменить все вхождения “old” на “new” с запросом подтверждения  
`:2,35s/old/new/g`  - Заменить все вхождения “old” на “new” между 2 и 35 строками  
`:5,$s/old/new/g`  - Заменить все вхождения “old” на “new” начиная с 5 строки и до конца файла  
`:%s/^/hello/g`  - Добавить “hello” в начало каждой строки  
`:%s/$/Harry/g`  - Добавить “Harry” в конец каждой строки  
`:%s/onward/forward/gi`  - Заменить “onward” на “forward” с учетом регистра  
`:%s/ *$//g`  - Убрать все пробелы  
`:g/string/d`  - Удалить все строки, содержащие “string”  
`:v/string/d`  - Удалить все строки, не содержащие “string”  
`:s/Bill/Steve/`  - Заменить первое вхождение “Bill” на “Steve” в текущей строке  
`:s/Bill/Steve/g`   - Заменить все вхождения “Bill” на “Steve” в текущей строке  
`:%s/\r//g` - Убрать символ возврата каретки (Такие тексты обычно приходят от windows-пользователей)  
`:%s#>[^<]\+>##g`  - Очистить текст от HTML-тегов  
`:%s/^\(.*\)\n\1$/\1/`  - Удалить строки, повторяющиеся дважды  
`Ctrl+a`  - Увеличить число под курсором на единицу  
`Ctrl+x`  - Уменьшить число под курсором на единицу  
`ggVGg?`  - Преобразовать текст в Rot13

### Регистр

`Vu`  - Перевести строку в нижний регистр  
`VU`  - Перевести строку в верхний регистр  
`g~~`  - Инвертировать регистр  
`vEU`  - Перевести слово под курсором в верхний регистр  
`vE~`  - Инвертировать регистр слова  
`gggu`  - GПеревести весь текст в нижний регистр  
`:set ignorecase`  - Регистронезависимый поиск  
`:set smartcase`  - Игнорировать регистр при поиске, если в искомом выражении нет символов верхнего регистра  
`:%s/\<./\u&/g`  - Перевести первую букву каждого слова в верхний регистр  
`:%s/\<./\l&/g`  - Перевести первую букву каждого слова в нижний регистр  
`:%s/.*/\u&`  - Перевести первую букву первого слова в каждой строке в верхний регистр  
`:%s/.*/\l&`  - Перевести первую букву первого слова в каждой строке в нижний регистр

### Полезные ссылки 

http://rayninfo.co.uk/vimtips.html


**Дополнительные источники:**

http://www.instanceof.ru/linux/vim/step-by-step  
http://ru.wikibooks.org/wiki/Vim  
https://www.youtube.com/watch?v=5r6yzFEXajQ  - Отличный видос How To Use  
https://www.youtube.com/watch?v=lQNFfhC4QI8 - Vim Magic (real example)

За основу взят GVIM редактор, который работает под Windows  
- http://vrapper.sourceforge.net/home/ - Установка плагина для Eclipse  
- http://vrapper.sourceforge.net/documentation/?topic=basics - Документация для плагина
- http://konishchevdmitry.blogspot.ru/2008/07/howto-vim.html - Хорошее описание команд.  
- http://fatroom.blogspot.ru/2007/02/vim.html - Описание команд  
- http://transerfing-realnosti.ru/debian/22-navigaciya-v-vim.html  - Отличное (все есть)
- http://scabere.livejournal.com/62886.html - командная строка  
- http://vimcasts.org/episodes/tabs-and-spaces/ - Настройки табуляции

