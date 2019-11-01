---
title:
- ЗАГОЛОВОК СТАТЬИ
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - MM/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: 4f50d4d446896e12b5beb86fc649ea4fa7c82718
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775543"
---
# <a name="metadata-and-markdown-template"></a>Шаблон метаданных и разметки Markdown

Этот шаблон dotnet/docs содержит примеры синтаксиса Markdown, а также указания по заданию метаданных. Чтобы использовать шаблон наиболее эффективно, следует просматривать как [необработанную разметку Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md), так и [подготовленное к просмотру представление](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (например, в необработанной разметке Markdown виден блок метаданных, а в подготовленном к просмотру представлении — нет).

При создании файла Markdown следует скопировать этот шаблон в новый файл, заполнить метаданные, как указано ниже, задать заголовок H1 в соответствии с названием статьи и удалить содержимое.

## <a name="metadata"></a>Metadata

Полный блок метаданных (в [необработанной разметке Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)) разделен на четыре обязательных поля и необязательные поля. Ключевые замечания:

- Между двоеточием (:) и значением элемента метаданных **должен** быть пробел.
- Если необязательный элемент метаданных не имеет значения, закомментируйте элемент символом # или удалите его (не оставляйте его пустым и не используйте "НД"). Если вы добавляете значение к элементу, который был закомментирован, не забудьте удалить #.
- Двоеточия в значении (например, названии) нарушают работу средства анализа метаданных. В этом случае заключите название в двойные кавычки (например, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- Поле **title**. Отображается в результатах поисковой системы. Заголовок не обязательно должен совпадать с названием в заголовке H1 и должен содержать не более 60 символов.
- **description**: содержит сводку по содержимому статьи. Обычно отображается на странице результатов поиска, но не используется для ранжирования поиска. Его длина должна составлять 115–145 символов, включая пробелы.
- **author** и **ms.author**: поле author должно содержать **имя пользователя GitHub**, принадлежащее автору, а не его псевдоним.  Поле **ms.author**, с другой стороны, должно содержать псевдоним Майкрософт и указывает лицо, ответственное за сопровождение статьи.
- **ms.topic**: тип раздела. Наиболее распространенное значение — `conceptual`. Оно устанавливается на глобальном уровне. Используются и другие распространенные значения: `tutorial`, `overview` и `reference`.
- **ms.devlang** определяет языковой фильтр, отображаемый для раздела. Список поддерживаемых значений можно просмотреть в разделе [Поддерживаемые языки](#supported-languages). Необходимо устанавливать только в том случае, если в разделе содержится более одного языка программирования. Как правило, для этого значения в содержимом используются только `csharp`, `vb`, `fsharp` и `cpp`.
- **ms.prod**: идентификатор продукта, используемый для бизнес-аналитики. Обычно они устанавливаются на глобальном уровне, поэтому не отображаются в блоке метаданных каждой статьи.
- **ms.technology**: дополнительная классификация бизнес-аналитики. Некоторые из поддерживаемых значений: `devlang-csharp` для разделов по C#, `devlang-fsharp` для разделов по F# и `devlang-visual-basic` для разделов по VB. Для других руководств значения будут различаться, поэтому обратитесь к участнику группы за рекомендациями.
- **ms.date**: дата в формате MM/ДД/ГГГГ. Отображается на опубликованной странице, чтобы указать время последнего существенного изменения статьи или гарантировать ее актуальность (то есть статья была проверена и признана актуальной).
- **helpviewer_keywords**: Записи используются для автономного индексирования книг (функция в Visual Studio).
- **f1_keywords**: Подключает статью к клавише F1 (функция в Visual Studio).

## <a name="basic-markdown-gfm-and-special-characters"></a>Базовая разметка Markdown, GFM и специальные символы

Поддерживаются все возможности базовой разметки Markdown и GitHub Flavored Markdown (GFM). Дополнительные сведения см. в следующих ресурсах.

- [Базовый синтаксис Markdown](https://daringfireball.net/projects/markdown/syntax)
- [Документация GFM](https://guides.github.com/features/mastering-markdown)

Для форматирования в Markdown используются специальные символы, такие как \*, \` и \#. Если вы хотите включить в содержимое один из этих символов, нужно выполнить одно из двух действий:

- поставить обратную косую черту перед специальным символом для его экранирования (например, `\*` для символа \*);
- использовать [код сущности HTML](https://www.ascii.cl/htmlcodes.htm) для символа (например, `&#42;` для &#42;).

## <a name="file-name"></a>Имя файла

В отношении имен файлов действуют указанные ниже правила.

- Содержат только строчные буквы, цифры и дефисы.
- Пробелы и знаки препинания недопустимы. Для разделения слов и чисел в именах файлов используйте дефисы.
- Для обозначения действий используйте глаголы, например develop, buy, build, troubleshoot. Не используйте суффикс -ing.
- Не используйте служебные слова, такие как a, and, the, in, or и т. д.
- Необходимо использовать формат Markdown и расширение имени файла .md.
- Имена файлов не должны быть слишком длинными. Они являются частью URL-адресов статей.

## <a name="headings"></a>Заголовки

Прописные буквы следует использовать как в предложениях. Первое слово заголовка всегда должно начинаться с прописной буквы, но не начинайте с него слово, идущее после двоеточия в заголовке или названии (например, "How to: sort an array").

Заголовки следует оформлять в стиле atx, то есть использовать для указания заголовка 1–6 символов решетки (#) в начале строки, что соответствует уровням заголовков HTML с H1 по H6. Выше приведены примеры заголовков первого и второго уровней.

В статье **должен** быть только один заголовок первого уровня (H1), который будет отображаться на странице как название.

Если заголовок заканчивается символом `#`, его необходимо экранировать, чтобы заголовок отображался правильно. Например, `# Async programming in F\#`.

На основе заголовков второго уровня будет сформировано оглавление, которое приводится в разделе "Содержимое статьи" под названием статьи.

### <a name="third-level-heading"></a>Заголовок третьего уровня
#### <a name="fourth-level-heading"></a>Заголовок четвертого уровня
##### <a name="fifth-level-heading"></a>Заголовок пятого уровня
###### <a name="sixth-level-heading"></a>Заголовок шестого уровня

## <a name="text-styling"></a>Стиль текста

*Курсив* — используйте для имен файлов, папок и путей (если из-за большой длины они выносятся в отдельные строки), новых терминов.

**Полужирный** — используйте для элементов пользовательского интерфейса.

`Code` — используется для встроенного кода, ключевых слов языка, имен пакетов NuGet, команд командной строки, имен таблиц и столбцов базы данных, а также URL-адресов, по которым не нужно переходить.

## <a name="links"></a>Ссылки

### <a name="internal-links"></a>Внутренние ссылки

Чтобы создать ссылку на заголовок в том же файле Markdown (ссылку привязки), необходимо определить идентификатор заголовка, на который должна указывать ссылка. Для этого просмотрите исходный код обработанной статьи, найдите идентификатор заголовка (например, `id="blockquote"`) и создайте ссылку, поставив перед идентификатором символ # (например, `#blockquote`).
Идентификатор формируется автоматически на основе текста заголовка. Например, для уникального раздела под названием `## Step 2` идентификатор будет выглядеть так: `id="step-2"`.

- Пример: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` создает [объявление встроенных блоков с идентификатором языка](#inline-code-blocks-with-language-identifier).

Чтобы создать ссылку на файл Markdown в том же репозитории, используйте [относительную ссылку](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), указав расширение .md в конце имени файла.

- Пример: `[Readme file](../README.md)` создает [файл сведений](../README.md). (Обратите внимание, что в ссылках учитывается регистр.)
- Пример: `[Welcome to .NET](../docs/welcome.md)` создает [Добро пожаловать в .NET](../docs/welcome.md).

Чтобы создать ссылку на заголовок в файле Markdown в том же репозитории, используйте относительную ссылку + ссылку с символом решетки.

- Пример: `[.NET Community](../docs/welcome.md#open-source)` создает [Сообщество .NET](../docs/welcome.md#open-source).

В большинстве случаев мы используем относительные ссылки и не рекомендуем использовать `~/` в ссылках, так как относительные ссылки разрешаются в источнике на GitHub. Однако при ссылке на файл в зависимом репозитории мы будем использовать символ `~/` для предоставления пути. Так как файлы в зависимом репозитории находятся в другом расположении на GitHub, ссылки не будут правильно разрешаться с относительными ссылками независимо от того, как они были написаны.

Спецификации языков C# и Visual Basic включены в документы .NET путем включения источника из репозиториев языка. Источники Markdown управляются в репозиториях [csharplang](https://github.com/dotnet/csharplang) и [visual basic](https://github.com/dotnet/vblang).

Ссылки на спецификацию должны указывать на исходные каталоги, в которых включены эти спецификации. Для C# это **~/_csharplang/spec**, а для VB — **~/_vblang/spec**.

- Пример: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` создает [выражения запросов C#](~/_csharplang/spec/expressions.md#query-expressions).

### <a name="external-links"></a>Внешние ссылки

Чтобы создать ссылку на внешний файл, используйте полный URL-адрес.

- Пример: `[GitHub](https://www.github.com)` создает [GitHub](https://www.github.com).

Если URL-адрес включается в файл Markdown, он преобразуется в активную ссылку.

- Пример: `<https://www.github.com>` создает <https://www.github.com>.

Используйте протокол `https` для внешних ссылок. Используйте ссылки `http` только для тех сайтов, которые не поддерживают `https`.

### <a name="links-to-apis"></a>Ссылки на интерфейсы API

Система сборки имеет ряд расширений, которые позволяют ссылаться на основные интерфейсы API .NET, не используя внешние ссылки.
Для ссылки на интерфейс API можно использовать его уникальный идентификатор (UID), который формируется автоматически на основе исходного кода.

Уникальный идентификатор соответствует полному типу и имени члена.

При добавлении \* (или %2A) после уникального идентификатора ссылка представляет страницу перегрузки, а не конкретный API. Например, используйте это для ссылки на страницу [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) обычным способом вместо конкретной перегрузки, например [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_). Также можно использовать \* для ссылки на страницу элемента, если элемент не перегружен. Это позволяет избежать включения списка параметров в уникальный идентификатор.

Чтобы создать ссылку на определенную перегрузку метода, включите полное имя типа каждого из параметров метода. Например, \<xref:System.DateTime.ToString> ссылается на метод [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) без параметров, а \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> ссылается на метод [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_). Уникальные идентификаторы определенного перегруженного элемента можно найти в `https://xref.docs.microsoft.com/autocomplete`. Строка запроса "?text= *\<type-member-name>* " определяет тип или элемент, уникальный идентификатор которого вы хотите просмотреть. Например, `https://xref.docs.microsoft.com/autocomplete?text=string.format` получает перегрузки [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).

Чтобы создать ссылку на универсальный тип, например [System.Collections.Generic.ListT\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), используйте символ (%60), за которым следует число параметров универсального типа. Например, \<xref:System.Nullable%601> ссылается на тип [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), а \<xref:System.Func%602> ссылается на делегат [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).

Можно использовать один из следующих вариантов синтаксиса.

1. Автоматическая ссылка: `<xref:UID>` или `<xref:UID?displayProperty=nameWithType>`

   Параметр запроса `displayProperty` создает полный текст ссылки. По умолчанию текст ссылки показывает только имя элемента или типа.

2. Ссылка Markdown: `[link text](xref:UID)`

   Используется, если вы хотите настроить отображаемый текст ссылки.

Примеры

- `<xref:System.String>` преобразуется как [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` преобразуется как [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` преобразуется как [класс String](https://docs.microsoft.com/dotnet/api/system.string)

Дополнительные сведения об использовании этой нотации см. в разделе [Использование перекрестных ссылок](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).

Есть два способа найти уникальный идентификатор:

- Просмотрите исходный код для страницы API, на которую вы хотите сослаться, и найдите значение ms.assetid. Обратите внимание, что отдельные значения перегрузки не показаны в исходном коде.
- Используйте следующее средство для поиска уникальных идентификаторов: https://xref.docs.microsoft.com/autocomplete?text=tostring (замените tostring на части имени API, который вы пытаетесь найти). Средство выполняет поиск указанного параметра запроса `text` в любой части уникального идентификатора. Например, вы можете искать имя элемента (ToString), частичное имя элемента (ToStri), имя типа и элемента (Double.ToString) и т. д.

Если уникальный идентификатор содержит специальные символы \`, \# или \*, они должны быть представлены в значении идентификатора в кодировке HTML как `%60`, `%23` и `%2A` соответственно. Иногда круглые скобки кодируются, но это не обязательно.

Примеры

- System.Threading.Tasks.Task\`1 преобразуется в `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor преобразуется в `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) преобразуется в `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

## <a name="lists"></a>Списки

### <a name="ordered-lists"></a>Упорядоченные списки

1. Это
1. Пример
1. Обычного
1. Упорядоченного
1. Списка

#### <a name="ordered-list-with-an-embedded-list"></a>Упорядоченный список с внедренным списком.

1. А
1. это
1. пример
1. внедренного
    1. Мисс Скарлетт
    1. Профессор Плам
1. упорядоченного
1. списка

### <a name="unordered-lists"></a>Неупорядоченные списки

- Вот
- это
- пример
- маркированного
- списка

#### <a name="unordered-list-with-an-embedded-list"></a>Неупорядоченный список с внедренным списком

- Этот
- маркированный
- списка
  - Миссис Пикок
  - Мистер Грин
- содержит
- другие
  1. Полковник Мастард
  1. Миссис Уайт
- списки

## <a name="horizontal-rule"></a>Горизонтальная линия

---

## <a name="tables"></a>Таблицы

| Таблицы        | Это           | Здорово  |
| ------------- |:-------------:| -----:|
| столбец 3      | выровнен по правому краю | $1600 |
| столбец 2      | выровнен по центру      |   $12 |
| столбец 1 по умолчанию | выровнен по левому краю     |    $1 |

Для удобства можно использовать [средство создания таблиц Markdown](https://www.tablesgenerator.com/markdown_tables).

## <a name="code"></a>Код

Лучший способ добавления кода — включение фрагментов из рабочего образца. Создайте образец согласно инструкциям в [руководстве по добавлению кода](../CONTRIBUTING.md#contributing-to-samples).

Код можно включить с помощью следующего синтаксиса:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- `-<language>` (*необязательно*, но *рекомендуется*)
  - Язык фрагмента кода, на который указывает ссылка. Список поддерживаемых значений см. в разделе [Поддерживаемые языки ](#supported-languages).

- `<name>` (*необязательно*)
  - Имя фрагмента кода. Оно не влияет на выходные данные HTML, но его можно использовать для повышения удобочитаемости источника Markdown.

- `<pathToFile>` (*обязательно*)
  - Относительный путь в файловой системе, указывающий на файл фрагмента кода для ссылки.

- `<queryoption>` и `<queryoptionvalue>` (*необязательно*)
  - Используется совместно для указания способа извлечения кода из файла:
    - `#`: `#L{startlinenumber}-L{endlinenumber}` (диапазон строк) *или* `#{tagname}` (имя тега).
    Мы не рекомендуем использовать номера строк, так отдельные строки слишком отрывочны. Лучше используйте имя тега для ссылки на фрагменты кода.
    - `range`. `?range=1,3-5` Диапазон строк. Этот пример включает строки 1, 3, 4 и 5.
    - `dedent`. `?dedent=8` Укорачивает строки на число пробелов — в данном случае 8. Это можно сочетать с `range` и другими параметрами запросов, которые выбирают подмножество строк файла.
    - `outdent`. `?outdent=8` Отменяет отступ строк на число пробелов — в данном случае 8. Это можно сочетать с `range` и другими параметрами запросов, которые выбирают подмножество строк файла.

По возможности рекомендуется использовать параметр имени тега. Имя тега — это имя региона или комментария к коду в формате `Snippettagname`, присутствующее в исходном коде. В приведенном ниже примере показано, как ссылаться на имя тега `1`:

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

Вы видите, как фрагменты кода структурированы в [этом исходном файле](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs). Дополнительные сведения о представлении имени тега в исходных файлах фрагментов кода по языку см. в [руководстве по DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

Включение фрагментов из полных программ обеспечивает выполнение всего кода в нашей системе непрерывной интеграции (CI). Однако если вам нужно показать фрагмент, который вызывает ошибки во время компиляции или выполнения, вы можете использовать встроенные блоки кода.

### <a name="inline-code-blocks-with-language-identifier"></a>Встроенные блоки кода с идентификатором языка

Чтобы применить к блоку кода цветовое выделение синтаксиса, характерное для данного языка, используйте три обратных апострофа (\`\`\`) и идентификатор языка. Ниже приведен список поддерживаемых языков, в которых отображается метка Markdown для каждого идентификатора языка.

#### <a name="supported-languages"></a>Поддерживаемые языки

|name|Метка Markdown|
|-----|-------|
|Консоль .NET|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|Инфраструктура CLI Azure|azurecli|
|AzCopy|azcopy|
|Azure PowerShell|azurepowershell|
|Bash|bash|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|C# в браузере|csharp-interactive|
|Консоль|console|
|CSHTML|cshtml|
|DAX|dax|
|Dockerfile|dockerfile|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Язык запросов Kusto|kusto|
|Markdown|md|
|Node.js|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|PowerApps (десятичный разделитель — точка)|powerapps-dot|
|PowerApps (десятичный разделитель — запятая)|powerapps-comma|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|R|процедура|
|Ruby|ruby|
|SQL-код|sql|
|Swift|swift|
|TypeScript|typescript|
|Visual Basic|vb|
|VBScript|vbscript|
|XAML|xaml|
|XML|xml|

Имя `csharp-interactive` указывает язык C# и возможность запуска примеров из браузера. Эти фрагменты кода компилируются и выполняются в контейнере Docker, и результаты выполнения программы отображаются в окне браузера пользователя.

Ниже приведены примеры блоков кода с использованием идентификаторов языков для C# (\`\`\`csharp), Python (\`\`\`python) и PowerShell (\`\`\`powershell).

##### <a name="c9839"></a>C&#9839;

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a>Python

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a>PowerShell

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a>Общий блок кода

Для общего выделения синтаксиса в блоке кода используйте три обратных апострофа (&#96;&#96;&#96;).

> Рекомендуемым подходом является использование блоков кода с идентификаторами языков, как описано в предыдущем разделе, для обеспечения правильного выделения синтаксиса на сайте документации. Используйте общие блоки кода только при необходимости.

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a>Блок цитирования

> Засуха продолжалась десять миллионов лет, и царству ужасных ящеров уже давно пришел конец. Здесь, близ экватора, на материке, который позднее назовут Африкой, с новой яростью вспыхнула борьба за существование, и еще не ясно было, кто выйдет из нее победителем. На этой бесплодной, иссушенной зноем земле благоденствовать или хотя бы просто выжить могли только маленькие, или ловкие, или свирепые.

## <a name="images"></a>Изображения

### <a name="static-image-or-animated-gif"></a>Статическое изображение или анимационный GIF

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![это замещающий текст](../images/Logo_DotNet.png)

### <a name="linked-image"></a>Связанное изображение

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

[![замещающий текст для связанного изображения](../images/Logo_DotNet.png)](https://dot.net)

## <a name="videos"></a>Видеоролики

В настоящее время вы можете внедрить видео Channel 9 и YouTube с помощью следующего синтаксиса:

### <a name="channel-9"></a>Канал 9

```markdown
> [!VIDEO <channel9_video_link>]
```

Чтобы получить правильный URL-адрес видео, выберите вкладку **Внедрить** под видеокадром и скопируйте URL-адрес из элемента `<iframe>`. Например:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Чтобы получить правильный URL-адрес видео, щелкните видео правой кнопкой мыши, выберите **Копировать код внедрения** и скопируйте URL-адрес из элемента `<iframe>`.

```markdown
> [!VIDEO <youtube_video_link>]
```

Например:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>Расширения docs.microsoft

docs.microsoft предоставляет несколько дополнительных расширений для GitHub Flavored Markdown.

### <a name="alerts"></a>Предупреждения

Необходимо использовать показанные ниже стили оповещений, чтобы они правильно отображались на сайте документации. Однако модуль отрисовки GitHub не различает их.

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

Отображение будет таким: ![Стили оповещений](../images/alerts.png)

### <a name="includes"></a>Содержит

Вы можете внедрить Markdown одного файла в другой, используя include.

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a>Отмеченные списки

Пользовательский стиль доступен для списков. Можно отобразить списки с зелеными галочками.

> [!div class="checklist"]
>
> - как создать приложение .NET Core;
> - как добавить ссылку на пакет Microsoft.XmlSerializer.Generator;
> - как изменить MyApp.csproj для добавления зависимостей;
> - как добавить класс и XmlSerializer;
> - как собрать и запустить приложение.

Пример отмеченных списков в действии см. в [документации по .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Кнопки

> [!div class="button"]
> [ссылки кнопок](../docs/core/index.md)

Примеры кнопок в действии можно увидеть в [документации по Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="selectors"></a>Селекторы

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

Примеры селекторов в действии можно увидеть в [документации по Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).

### <a name="step-by-steps"></a>Пошаговые инструкции

>[!div class="step-by-step"]
>[Назад](../docs/csharp/expression-trees-interpreting.md)
>[Вперед](../docs/csharp/expression-trees-translating.md)

Примеры пошаговых операций можно увидеть в [руководстве по C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
