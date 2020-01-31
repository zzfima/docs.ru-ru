---
title: URI типа "Pack"
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: 0fec72bdedbcc2c84d8bc65e72391366e42d82be
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739159"
---
# <a name="pack-uris-in-wpf"></a>URI типа "pack" в WPF

В Windows Presentation Foundation (WPF) универсальные идентификаторы ресурсов (URI) используются для идентификации и загрузки файлов различными способами, включая следующие:

- Указание [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], отображаемых при первом запуске приложения.

- Загрузка изображений.

- Переход по страницам.

- Загрузка неисполняемых файлов данных.

Кроме того, универсальные коды ресурса (URI) можно использовать для обнаружения и загрузки файлов из различных расположений, включая следующие:

- Текущая сборка.

- Указанная ссылками сборка.

- Расположение, связанное со сборкой.

- Исходный узел приложения.

Чтобы обеспечить единообразный механизм идентификации и загрузки этих типов файлов из этих расположений, WPF использует расширяемость *схемы URI*типа "Pack". В этом разделе приводятся общие сведения о схеме, описывается создание URI типа "Pack" для различных сценариев, обсуждаются абсолютные и относительные URI и разрешение URI, прежде чем показано, как использовать URI типа "Pack" из разметки и кода.

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a>Схема URI типа "pack"

Схема URI типа "Pack" используется спецификацией [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC), которая описывает модель для Организации и идентификации содержимого. Ключевыми элементами этой модели являются пакеты и части, где *пакет* является логическим контейнером для одной или нескольких логических *частей*. Эта структура показана на следующем рисунке.

![Схема пакета и частей](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

Для определения частей в спецификации OPC используется расширяемость RFC 2396 (универсальные идентификаторы ресурсов (URI): универсальный синтаксис) для определения схемы URI типа "Pack".

Схема, заданная с помощью URI, определяется его префиксом. HTTP, FTP и файлы — это хорошо известные примеры. В схеме универсального кода ресурса (URI) типа "Pack" в качестве схемы содержится два компонента: Authority и Path. Ниже приведен формат URI типа pack.

*путь*/*центра* Pack://

*Центр* определяет тип пакета, который содержится в части, а *путь* указывает расположение части в пакете.

Эта концепция показана на следующей схеме:

![Отношение между пакетом, сертификацией и путем](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

Пакеты и элементы аналогичны приложениям и файлам. Приложение (пакет) может содержать один или несколько файлов (элементов), в том числе:

- Файлы ресурсов, скомпилированные в локальную сборку.

- Файлы ресурсов, скомпилированные в сборку, на которую указывает ссылка.

- Файлы ресурсов, скомпилированные в ссылающуюся сборку.

- Файлы содержимого.

- Файлы исходного узла.

Для доступа к этим типам файлов WPF поддерживает два центра: application:///и siteoforigin:///. Центр application:/// определяет файлы данных приложения, известные во время компиляции, включая файлы ресурсов и файлы содержимого. Центр siteoforigin:/// определяет файлы исходного узла. На следующем рисунке показана область каждого центра.

![Схема URI типа “pack”](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> Компонент центра URI типа "Pack" является внедренным универсальным кодом ресурса (URI), который указывает на пакет и должен соответствовать RFC 2396. Кроме того, символ "/" необходимо заменить символом ",", и необходимо обособлять escape-символами такие зарезервированные символы, как "%" и "?". Подробные сведения см. в OPC.

В следующих разделах объясняется, как создать URI типа "Pack" с помощью этих двух центров в сочетании с соответствующими путями для определения файлов ресурсов, содержимого и исходного узла.

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a>URI типа "pack" для файла ресурсов

Файлы ресурсов настраиваются как MSBuild `Resource` элементы и компилируются в сборки. WPF поддерживает создание URI типа "Pack", которые можно использовать для обнаружения файлов ресурсов, которые либо компилируются в локальную сборку, либо компилируются в сборку, на которую ссылается локальная сборка.

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a>Файл ресурсов локальной сборки

URI типа "Pack" для файла ресурсов, компилируемого в локальную сборку, использует следующие полномочия и путь:

- **Центр**: application:///.

- **Путь**: имя файла ресурсов, включая его путь относительно корневой папки проекта локальной сборки.

В следующем примере показан URI типа "Pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится в корне папки проекта локальной сборки.

`pack://application:,,,/ResourceFile.xaml`

В следующем примере показан URI типа "Pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится во вложенной папке проекта локальной сборки.

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a>Файл ресурсов указанной ссылками сборки

URI типа "Pack" для файла ресурсов, компилируемого в указанную сборку, использует следующие полномочия и путь:

- **Центр**: application:///.

- **Путь**: имя файла ресурсов, который компилируется в указанную ссылками сборку. Путь должен соответствовать следующему формату:

  *Ассемблишортнаме*{ *; Версия*] { *; PublicKey*]; компонент или*путь*

  - **AssemblyShortName** — краткое имя для указанной ссылками сборки.

  - **;Version** [необязательно] — версия указанной ссылками сборки, которая содержит файл ресурсов. Используется при загрузке двух или более указанных ссылками сборок с одинаковым кратким именем.

  - **;PublicKey** [необязательно]: открытый ключ, который использовался для подписи указанной ссылками сборки. Используется при загрузке двух или более указанных ссылками сборок с одинаковым кратким именем.

  - **;component**: указывает, что на упоминаемую сборку ссылается локальная сборка.

  - **/Path**: имя файла ресурсов, включая его путь относительно корневой папки проекта указанной ссылками сборки.

В следующем примере показан URI типа "Pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится в корне папки проекта указанной сборки.

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

В следующем примере показан URI типа "Pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится во вложенной папке проекта указанной сборки.

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

В следующем примере показан URI типа "Pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится в корневой папке указанной в папке проекта сборки для конкретной версии.

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

Обратите внимание, что синтаксис URI типа "Pack" для файлов ресурсов сборки, на которые указывают ссылки, можно использовать только с центром application:///. Например, в WPF не поддерживается следующее.

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a>URI типа "pack" для файла содержимого

В URI типа "Pack" для файла содержимого используются следующие полномочия и путь:

- **Центр**: application:///.

- **Путь**: имя файла содержимого, включая его путь относительно расположения файловой системы основной исполняемой сборки приложения.

В следующем примере показан URI типа "Pack" для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ного файла содержимого, расположенного в той же папке, что и исполняемая сборка.

`pack://application:,,,/ContentFile.xaml`

В следующем примере показан URI типа "Pack" для файла содержимого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится во вложенной папке, относящейся к исполняемой сборке приложения.

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> Переход к файлам HTML-содержимого невозможен. Схема URI поддерживает только навигацию по HTML-файлам, расположенным на исходном узле.

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a>URI типа "pack" исходного узла

URI типа "Pack" для файла исходного узла использует следующие полномочия и путь:

- **Центр**: siteoforigin:///.

- **Путь**: имя файла исходного узла, включая его путь относительно расположения, из которого была запущена исполняемая сборка.

В следующем примере показан URI типа Pack для файла исходного узла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], хранящегося в расположении, из которого запускается исполняемая сборка.

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

В следующем примере показан URI типа Pack для файла исходного узла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], хранящегося в подпапке, которая относится к расположению, из которого запускается исполняемая сборка приложения.

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a>Файлы подкачки

Файлы XAML, настроенные как MSBuild `Page` элементы, компилируются в сборки так же, как и файлы ресурсов. Следовательно, элементы `Page` MSBuild можно определить с помощью URI типа "Pack" для файлов ресурсов.

Типы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлов, которые обычно настраиваются как элементы`Page` MSBuild, имеют в качестве корневого элемента один из следующих элементов:

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a>Абсолютные и относительные URI типа Pack

Полный URI типа "Pack" включает схему, центр и путь, и считается абсолютным URI типа "Pack". В качестве упрощения для разработчиков [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементы обычно позволяют задавать соответствующие атрибуты с помощью относительного URI типа "Pack", который включает только путь.

Например, рассмотрим следующий абсолютный пакет URI для файла ресурсов в локальной сборке.

`pack://application:,,,/ResourceFile.xaml`

Относительный URI типа "Pack", ссылающийся на этот файл ресурсов, будет следующим.

`/ResourceFile.xaml`

> [!NOTE]
> Так как файлы исходного узла не связаны со сборками, они могут называться только абсолютными URI типа "Pack".

По умолчанию относительный URI типа "Pack" рассматривается относительно расположения разметки или кода, содержащего ссылку. Однако если используется начальная обратная косая черта, ссылка на URI-адрес относительных пакетов будет рассматриваться относительно корня приложения. Например, рассмотрим следующую структуру проекта.

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

Если параметр ". XAML" содержит URI, который ссылается на *корневой*\SubFolder\Page2.XAML, ссылка может использовать следующий относительный URI типа "Pack".

`Page2.xaml`

Если параметр ". XAML" содержит URI, который ссылается на *корневой*\Page2.XAML, ссылка может использовать следующий относительный URI типа "Pack".

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a>Разрешение URI типа "pack"

Формат URI типа "Pack" позволяет одинаково различать URI типа "Pack" для различных типов файлов. Например, рассмотрим следующий абсолютный URI типа pack.

`pack://application:,,,/ResourceOrContentFile.xaml`

Этот абсолютный URI типа "Pack" может ссылаться либо на файл ресурсов в локальной сборке, либо на файл содержимого. То же справедливо для следующего относительного URI.

`/ResourceOrContentFile.xaml`

Чтобы определить тип файла, на который ссылается URI типа Pack, WPF разрешает URI для файлов ресурсов в локальных сборках и файлах содержимого, используя следующие эвристики:

1. Проверяет метаданные сборки для атрибута <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, соответствующего URI типа pack.

2. Если найден атрибут <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, путь URI типа "Pack" ссылается на файл содержимого.

3. Если атрибут <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> не найден, проверяют файлы ресурсов, компилируемые в локальную сборку.

4. Если найден файл ресурсов, соответствующий пути URI типа "Pack", путь к URI типа "Pack" ссылается на файл ресурсов.

5. Если ресурс не найден, <xref:System.Uri>, созданный внутренним образом, является недопустимым.

Разрешение URI не применяется для URI, которые ссылаются на следующие:

- Файлы содержимого в сборках, на которые имеются ссылки: эти типы файлов не поддерживаются в WPF.

- Внедренные файлы в упоминаемых сборках: URI, которые их определяют, являются уникальными, так как включают имя сборки, на которую указывает ссылка, и суффикс `;component`.

- Файлы исходного узла: универсальные коды ресурса (URI) являются уникальными, так как они являются единственными файлами, которые можно идентифицировать с помощью URI типа "Pack", содержащих центр siteoforigin:///.

Одно упрощение, позволяющее разрешающему URI типа "Pack", заключается в том, что код может быть несколько независимым от расположения файлов ресурсов и содержимого. Например, если в локальной сборке есть файл ресурсов, который перестраивается как файл содержимого, URI типа "Pack" для ресурса остается прежним, так же как и код, использующий URI типа "Pack".

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a>Программирование с использованием URI типа "pack"

Многие классы WPF реализуют свойства, которые можно задать с помощью URI типа Pack, в том числе:

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

Эти свойства можно задать из разметки и кода. В этом разделе демонстрируются основные конструкции для разметки и кода, а также приводятся примеры наиболее распространенных сценариев.

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a>Использование URI типа "pack" в разметке

URI типа "Pack" указывается в разметке путем задания элемента атрибута с URI типа "Pack". Например:

`<element attribute="pack://application:,,,/File.xaml" />`

В таблице 1 показаны различные абсолютные URI типа "Pack", которые можно указать в разметке.

Таблица 1. Абсолютные URI типа "pack" в разметке

|File|Абсолютный URI типа Pack|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Файл ресурсов — локальная сборка|`"pack://application:,,,/ResourceFile.xaml"`|
|Файл ресурсов в подпапке — локальная сборка|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|Файл ресурсов — указанная ссылками сборка|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|Файл ресурсов в подпапке указанной ссылками сборки|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|Файл ресурсов в указанной ссылками сборке с несколькими версиями|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|Файл содержимого|`"pack://application:,,,/ContentFile.xaml"`|
|Файл содержимого в подпапке|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|Файл исходного узла|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|Файл исходного узла в подпапке|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

В таблице 2 показаны различные относительные URI типа "Pack", которые можно указать в разметке.

Таблица 2. Относительные URI типа "pack" в разметке

|File|Относительный URI типа Pack|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Файл ресурсов в локальной сборке|`"/ResourceFile.xaml"`|
|Файл ресурсов в подпапке — локальная сборка|`"/Subfolder/ResourceFile.xaml"`|
|Файл ресурсов в указанной ссылками сборке|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|Файл ресурсов в подпапке указанной ссылками сборки|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|Файл содержимого|`"/ContentFile.xaml"`|
|Файл содержимого в подпапке|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a>Использование URI типа "pack" в коде

URI типа "Pack" указывается в коде путем создания экземпляра класса <xref:System.Uri> и передачи URI типа "Pack" в качестве параметра в конструктор. Это показано в следующем примере.

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

По умолчанию класс <xref:System.Uri> считает URI типа "Pack" абсолютным. Следовательно, исключение возникает, когда экземпляр класса <xref:System.Uri> создается с помощью относительного URI типа "Pack".

```csharp
Uri uri = new Uri("/File.xaml");
```

К счастью, перегрузка <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> конструктора класса <xref:System.Uri> принимает параметр типа <xref:System.UriKind>, чтобы можно было указать, является ли универсальный код ресурса (URI) абсолютным или относительным.

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

Необходимо указать только <xref:System.UriKind.Absolute> или <xref:System.UriKind.Relative>, если вы уверены, что предоставленный URI типа "Pack" является одним или другим. Если неизвестно, какой тип URI используется, например, когда пользователь вводит URI типа "Pack" во время выполнения, используйте вместо этого <xref:System.UriKind.RelativeOrAbsolute>.

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

В таблице 3 показаны различные относительные URI типа "Pack", которые можно указать в коде с помощью <xref:System.Uri?displayProperty=nameWithType>.

Таблица 3. Абсолютные URI типа "pack" в коде

|File|Абсолютный URI типа Pack|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Файл ресурсов — локальная сборка|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|Файл ресурсов в подпапке — локальная сборка|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|Файл ресурсов — указанная ссылками сборка|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|Файл ресурсов в подпапке указанной ссылками сборки|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|Файл ресурсов в указанной ссылками сборке с несколькими версиями|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|Файл содержимого|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|Файл содержимого в подпапке|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|Файл исходного узла|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|Файл исходного узла в подпапке|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

В таблице 4 показаны различные относительные URI типа "Pack", которые можно указать в коде с помощью <xref:System.Uri?displayProperty=nameWithType>.

Таблица 4. Относительные URI типа "pack" в коде

|File|Относительный URI типа Pack|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Файл ресурсов — локальная сборка|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|Файл ресурсов в подпапке — локальная сборка|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|Файл ресурсов — указанная ссылками сборка|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|Файл ресурсов в подпапке — указанная ссылками сборка|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|Файл содержимого|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|Файл содержимого в подпапке|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a>Типичные сценарии URI типа "pack"

В предыдущих разделах обсуждалось создание URI типа "Pack" для указания файлов ресурсов, содержимого и исходного узла. В WPF эти конструкции используются различными способами, и в следующих разделах рассматриваются некоторые распространенные способы использования.

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>Указание пользовательского интерфейса для отображения при запуске приложения

<xref:System.Windows.Application.StartupUri%2A> указывает первый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], отображаемый при запуске приложения WPF. Для автономных приложений [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] может быть окном, как показано в следующем примере.

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

Автономные приложения и приложения браузера XAML (XBAP) также могут указывать страницу в качестве начального пользовательского интерфейса, как показано в следующем примере.

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

Если приложение является автономным и страница указана с помощью <xref:System.Windows.Application.StartupUri%2A>, WPF откроет <xref:System.Windows.Navigation.NavigationWindow> для размещения страницы. Для XBAP страница отображается в браузере узла.

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a>Переход на страницу

В следующем примере показано, как перейти на какую-либо страницу.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Дополнительные сведения о различных способах навигации в WPF см. в разделе [Общие сведения о навигации](navigation-overview.md).

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a>Указание значка окна

В следующем примере показано использование URI для указания значка окна.

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

Для получения дополнительной информации см. <xref:System.Windows.Window.Icon%2A>.

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a>Загрузка файлов изображения, аудио и видео файлов

WPF позволяет приложениям использовать разнообразные типы мультимедиа, которые можно идентифицировать и загрузить с помощью URI типа Pack, как показано в следующих примерах.

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

Дополнительные сведения о работе с мультимедийным содержимым см. в разделе [графика и мультимедиа](../graphics-multimedia/index.md).

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>Загрузка словаря ресурсов с исходного узла

Словари ресурсов (<xref:System.Windows.ResourceDictionary>) можно использовать для поддержки тем приложений. Одним из способов создания тем и управления ими является создание нескольких тем в качестве словарей ресурсов, расположенных в исходном узле приложения. Это позволяет добавлять и обновлять темы без повторной компиляции и развертывания приложения. Эти словари ресурсов можно определить и загрузить с помощью URI типа "Pack", как показано в следующем примере.

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

Общие сведения о темах в WPF см. в разделе [Стилизация и создание шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

## <a name="see-also"></a>См. также:

- [Файлы ресурсов, содержимого и данных WPF-приложения](wpf-application-resource-content-and-data-files.md)
