---
title: URI типа "pack" в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: f9ea4acfc7ba86d3424bb11af0de685651f99c61
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796757"
---
# <a name="pack-uris-in-wpf"></a>URI типа "pack" в WPF

В Windows Presentation Foundation (WPF) [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] используются для определения и загрузки файлов различными способами, включая следующие:

- [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Указание для отображения при первом запуске приложения.

- Загрузка изображений.

- Переход по страницам.

- Загрузка неисполняемых файлов данных.

Более того [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , можно использовать для обнаружения и загрузки файлов из различных расположений, включая следующие:

- Текущая сборка.

- Указанная ссылками сборка.

- Расположение, связанное со сборкой.

- Исходный узел приложения.

Чтобы обеспечить единообразный механизм идентификации и загрузки этих типов файлов из этих расположений, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] использует расширяемость *схемы URI*типа "Pack". В этом разделе приводятся общие сведения о схеме, рассказывается о [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] том, как создать пакет для различных сценариев, обсуждаются [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] абсолютные и относительные и [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] разрешения, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] прежде чем показано, как использовать Pack из обеих разметки. и код.

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a>Схема URI типа "pack"

Схема Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] используется в спецификации [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC), которая описывает модель для Организации и идентификации содержимого. Ключевыми элементами этой модели являются пакеты и части, где *пакет* является логическим контейнером для одной или нескольких логических *частей*. Эта структура показана на следующем рисунке.

![Схема пакета и частей](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

Для идентификации частей в спецификации OPC используется расширяемость RFC 2396 (универсальные идентификаторы ресурсов (URI)): Универсальный синтаксис) для определения схемы пакета [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] .

Схема, заданная [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] с помощью, определяется его префиксом; http, FTP и файл являются известными примерами. Схема Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] использует "Pack" в качестве схемы и содержит два компонента: "центр" и "путь". Ниже приведен формат типа "Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]".

*путь к* *центру*/Pack://

*Центр* определяет тип пакета, который содержится в части, а *путь* указывает расположение части в пакете.

Эта концепция показана на следующей схеме:

![Отношение между пакетом, сертификацией и путем](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

Пакеты и элементы аналогичны приложениям и файлам. Приложение (пакет) может содержать один или несколько файлов (элементов), в том числе:

- Файлы ресурсов, скомпилированные в локальную сборку.

- Файлы ресурсов, скомпилированные в сборку, на которую указывает ссылка.

- Файлы ресурсов, скомпилированные в ссылающуюся сборку.

- Файлы содержимого.

- Файлы исходного узла.

Для доступа к этим типам файлов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживает два центра: Application:///и siteoforigin:///. Центр application:/// определяет файлы данных приложения, известные во время компиляции, включая файлы ресурсов и файлы содержимого. Центр siteoforigin:/// определяет файлы исходного узла. На следующем рисунке показана область каждого центра.

![Схема URI типа “pack”](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> Компонент центра "Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] " является внедренным [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , который указывает на пакет и должен соответствовать RFC 2396. Кроме того, символ "/" необходимо заменить символом ",", и необходимо обособлять escape-символами такие зарезервированные символы, как "%" и "?". Подробные сведения см. в OPC.

В следующих разделах объясняется, как создать [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] пакет с помощью этих двух центров в сочетании с соответствующими путями для определения файлов ресурсов, содержимого и исходного узла.

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a>URI типа "pack" для файла ресурсов

Файлы ресурсов настраиваются как [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` элементы и компилируются в сборки. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]поддерживает создание пакетов [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , которое можно использовать для обнаружения файлов ресурсов, которые либо компилируются в локальную сборку, либо компилируются в сборку, на которую ссылается локальная сборка.

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a>Файл ресурсов локальной сборки

Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для файла ресурсов, компилируемого в локальную сборку, использует следующие полномочия и путь:

- **Центр**: application:///.

- **Путь**: Имя файла ресурсов, включая путь, относительно корневой папки проекта локальной сборки.

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла ресурсов, который находится в корне папки проекта локальной сборки.

`pack://application:,,,/ResourceFile.xaml`

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла ресурсов, который находится во вложенной папке проекта локальной сборки.

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a>Файл ресурсов указанной ссылками сборки

Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для файла ресурсов, компилируемого в указанную сборку, использует следующие полномочия и путь:

- **Центр**: application:///.

- **Путь**: Имя файла ресурсов, компилируемого в указанную сборку. Путь должен соответствовать следующему формату:

  *Ассемблишортнаме* { *; Версия*] { *; PublicKey*]; компонент или*путь*

  - **AssemblyShortName** — краткое имя для указанной ссылками сборки.

  - **;Version** [необязательно] — версия указанной ссылками сборки, которая содержит файл ресурсов. Используется при загрузке двух или более указанных ссылками сборок с одинаковым кратким именем.

  - **;PublicKey** [необязательно]: открытый ключ, который использовался для подписи указанной ссылками сборки. Используется при загрузке двух или более указанных ссылками сборок с одинаковым кратким именем.

  - **;component**: указывает, что на упоминаемую сборку ссылается локальная сборка.

  - **/Path**: имя файла ресурсов, включая его путь относительно корневой папки проекта указанной ссылками сборки.

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла ресурсов, который находится в корне папки проекта указанной сборки.

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла ресурсов, который находится во вложенной папке проекта указанной сборки.

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла ресурсов, который находится в корневой папке указанной в папке проекта сборки, относящейся к конкретной версии.

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

Обратите внимание, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] что синтаксис пакета для файлов ресурсов сборки, на которые указывают ссылки, можно использовать только с центром Application:///. Например, в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]не поддерживается следующее.

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a>URI типа "pack" для файла содержимого

Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для файла содержимого использует следующие полномочия и путь:

- **Центр**: application:///.

- **Путь**: Имя файла содержимого, включая путь относительно расположения файловой системы главной исполняемой сборки приложения.

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла содержимого, расположенного в той же папке, что и исполняемая сборка.

`pack://application:,,,/ContentFile.xaml`

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла содержимого, который находится во вложенной папке, относящейся к исполняемой сборке приложения.

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> Переход к файлам HTML-содержимого невозможен. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Схема поддерживает только навигацию по HTML-файлам, расположенным на исходном узле.

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a>URI типа "pack" исходного узла

Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для файла исходного сайта использует следующие полномочия и путь:

- **Центр**: siteoforigin:///.

- **Путь**: Имя файла исходного узла, включая его путь относительно расположения, из которого была запущена исполняемая сборка.

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла исходного узла, хранящегося в расположении, из которого запускается исполняемая сборка.

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для файла исходного узла, хранящегося в подпапке, которая относится к расположению, из которого запускается исполняемая сборка приложения.

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a>Файлы подкачки

[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]файлы, настроенные как [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` элементы, компилируются в сборки таким же образом, как и файлы ресурсов. Следовательно, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` элементы можно определить с помощью Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] для файлов ресурсов.

Типы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлов, которые обычно настраиваются как [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` элементы, имеют один из следующих элементов в качестве корневого элемента:

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a>Абсолютные и относительные URI типа "pack"

Полный пакет Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] включает схему, центр и путь, а также считается абсолютным пакетом [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. В качестве упрощения для разработчиков [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементы обычно позволяют устанавливать соответствующие атрибуты с относительным пакетом [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], который включает только путь.

Например, рассмотрим следующий абсолютный пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для файла ресурсов в локальной сборке.

`pack://application:,,,/ResourceFile.xaml`

Относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] пакет, который ссылается на этот файл ресурсов, будет выглядеть следующим образом.

`/ResourceFile.xaml`

> [!NOTE]
> Так как файлы исходного узла не связаны со сборками, они могут называться только абсолютным пакетом [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].

По умолчанию относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] пакет рассматривается относительно расположения разметки или кода, содержащего ссылку. Однако если используется начальная обратная косая черта, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] то относительная ссылка на пакет будет рассматриваться относительно корня приложения. Например, рассмотрим следующую структуру проекта.

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

Если параметр «\SubFolder\Page2.XAML. XAML [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] » содержит объект, который ссылается на *корневой*, ссылка может [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]использовать следующий относительный пакет.

`Page2.xaml`

Если параметр «\Page2.XAML. XAML [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] » содержит объект, который ссылается на *корневой*, ссылка может [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]использовать следующий относительный пакет.

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a>Разрешение URI типа "pack"

Формат пакета [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] позволяет другим типам файлов выглядеть так же [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , как Pack. Например, рассмотрим следующий абсолютный пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].

`pack://application:,,,/ResourceOrContentFile.xaml`

Этот абсолютный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] пакет может ссылаться либо на файл ресурсов в локальной сборке, либо на файл содержимого. То же справедливо и для следующего относительного [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].

`/ResourceOrContentFile.xaml`

Чтобы определить тип файла, на который ссылается пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] разрешает [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] файлы ресурсов в локальных сборках и файлах содержимого, используя следующие эвристики:

1. Проверяет метаданные сборки для <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> атрибута, который соответствует пакету. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]

2. Если атрибут найден, путь к пакету [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ссылается на файл содержимого. <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>

3. <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Если атрибут не найден, проверяют файлы ресурсов, компилируемые в локальную сборку.

4. Если найден файл ресурсов, соответствующий пути типа "Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ", путь к пакету [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ссылается на файл ресурсов.

5. Если ресурс не найден, создается <xref:System.Uri> Недопустимый внутренний объект.

[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]разрешение не применяется [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] к следующим параметрам:

- Файлы содержимого в сборках, на которые имеются ссылки: эти типы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]файлов не поддерживаются.

- Внедренные файлы в сборках [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , на которые имеются ссылки. они определяются уникальными, так как включают имя сборки `;component` , на которую указывает ссылка, и суффикс.

- Файлы исходного узла. [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] они идентифицируются уникальными, так как они являются единственными файлами, которые можно идентифицировать по пакету [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , содержащему центр siteoforigin:///.

Одно упрощение, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] которое позволяет разрешить пакетное разрешение, заключается в том, что код может быть несколько независимым от расположения файлов ресурсов и содержимого. Например, если в локальной сборке есть файл ресурсов, который перенастроен для использования в качестве файла содержимого, то пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для ресурса остается прежним, так же как и код, использующий этот пакет. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a>Программирование с использованием URI типа "pack"

Многие [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] классы реализуют свойства, которые можно задать с [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]помощью Pack, в том числе:

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

Эти свойства можно задать из разметки и кода. В этом разделе демонстрируются основные конструкции для разметки и кода, а также приводятся примеры наиболее распространенных сценариев.

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a>Использование URI типа "pack" в разметке

Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] задается в разметке путем установки элемента атрибута с пакетом [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Например:

`<element attribute="pack://application:,,,/File.xaml" />`

В таблице 1 показан различные абсолютные [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] пакеты, которые можно указать в разметке.

Таблица 1. Абсолютные URI типа "Pack" в разметке

|Файл|Абсолютный пакет[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
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

В таблице 2 показаны различные относительные пакеты [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , которые можно указать в разметке.

Таблица 2. Относительные URI типа "Pack" в разметке

|Файл|Относительный пакет[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Файл ресурсов в локальной сборке|`"/ResourceFile.xaml"`|
|Файл ресурсов в подпапке — локальная сборка|`"/Subfolder/ResourceFile.xaml"`|
|Файл ресурсов в указанной ссылками сборке|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|Файл ресурсов в подпапке указанной ссылками сборки|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|Файл содержимого|`"/ContentFile.xaml"`|
|Файл содержимого в подпапке|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a>Использование URI типа "pack" в коде

Чтобы указать пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] в коде, нужно создать экземпляр <xref:System.Uri> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] класса и передать его в качестве параметра в конструктор. Это показано в следующем примере.

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

По умолчанию <xref:System.Uri> класс рассматривает параметр [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Pack как абсолютный. Следовательно, при создании экземпляра <xref:System.Uri> класса с относительным пакетом [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]возникает исключение.

```csharp
Uri uri = new Uri("/File.xaml");
```

К счастью, <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> перегрузка <xref:System.Uri> конструктора класса принимает параметр типа <xref:System.UriKind> , чтобы можно было указать, является ли пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] абсолютным или относительным.

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

Необходимо указать только <xref:System.UriKind.Absolute> или <xref:System.UriKind.Relative> , если вы уверены, что предоставленный пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] является одним или другим. Если неизвестно, какой тип пакета [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] используется, например, когда пользователь вводит пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] во время выполнения, используйте <xref:System.UriKind.RelativeOrAbsolute> вместо него.

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

В таблице 3 показаны различные относительные пакеты [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , которые можно указать в коде с помощью. <xref:System.Uri?displayProperty=nameWithType>

Таблица 3. Абсолютные URI типа "Pack" в коде

|Файл|Абсолютный пакет[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
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

В таблице 4 показаны различные относительные пакеты [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , которые можно указать в коде с помощью. <xref:System.Uri?displayProperty=nameWithType>

Таблица 4. Относительные URI типа "Pack" в коде

|Файл|Относительный пакет[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Файл ресурсов — локальная сборка|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|Файл ресурсов в подпапке — локальная сборка|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|Файл ресурсов — указанная ссылками сборка|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|Файл ресурсов в подпапке — указанная ссылками сборка|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|Файл содержимого|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|Файл содержимого в подпапке|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a>Типичные сценарии URI типа "pack"

В предыдущих разделах обсуждалось создание пакета [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] для указания файлов ресурсов, содержимого и исходного узла. В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]эти конструкции используются различными способами, и в следующих разделах рассматриваются некоторые распространенные способы использования.

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>Указание пользовательского интерфейса для отображения при запуске приложения

<xref:System.Windows.Application.StartupUri%2A>Указывает первый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для отображения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] при запуске приложения. Для автономных приложений [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] может быть окном, как показано в следующем примере.

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

Автономные приложения [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] . также можно указать страницу в качестве начального пользовательского интерфейса, как показано в следующем примере.

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

Если приложение является автономным приложением, а страница указана с помощью <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] открывает <xref:System.Windows.Navigation.NavigationWindow> для размещения страницы. Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]страница отображается в браузере узла.

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a>Переход на страницу

В следующем примере показано, как перейти на какую-либо страницу.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Дополнительные сведения о различных способах перехода в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]см. в разделе [Общие сведения о навигации](navigation-overview.md).

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a>Указание значка окна

В следующем примере показано использование URI для указания значка окна.

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

Дополнительные сведения см. в разделе <xref:System.Windows.Window.Icon%2A>.

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a>Загрузка файлов изображения, аудио и видео файлов

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]позволяет приложениям использовать разнообразные типы носителей, которые могут быть идентифицированы и загружены с помощью типа "Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]", как показано в следующих примерах.

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

Дополнительные сведения о работе с мультимедийным содержимым см. в разделе [графика и мультимедиа](../graphics-multimedia/index.md).

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>Загрузка словаря ресурсов с исходного узла

Словари ресурсов<xref:System.Windows.ResourceDictionary>() можно использовать для поддержки тем приложений. Одним из способов создания тем и управления ими является создание нескольких тем в качестве словарей ресурсов, расположенных в исходном узле приложения. Это позволяет добавлять и обновлять темы без повторной компиляции и развертывания приложения. Эти словари ресурсов можно определить и загрузить с помощью [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]метода Pack, как показано в следующем примере.

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

Общие сведения о темах в см [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. в разделе [Стилизация и создание шаблонов](../controls/styling-and-templating.md).

## <a name="see-also"></a>См. также

- [Файлы ресурсов, содержимого и данных WPF-приложения](wpf-application-resource-content-and-data-files.md)
