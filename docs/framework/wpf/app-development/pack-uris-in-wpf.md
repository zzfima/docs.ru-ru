---
title: "URI типа &quot;pack&quot; в WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "управление приложениями [WPF]"
  - "загрузка внедренных ресурсов"
  - "загрузка файлов, не относящихся к ресурсам"
  - "pack URI scheme"
  - "Универсальные коды ресурсов (URI)"
  - "URI (универсальные коды ресурсов)"
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# URI типа &quot;pack&quot; в WPF
В [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] используются для идентификации и загрузки файлов несколькими способами, включая следующие:  
  
-   Указание отобразить [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] при первом запуске приложения.  
  
-   Загрузка изображений.  
  
-   Переход по страницам.  
  
-   Загрузка неисполняемых файлов данных.  
  
 Кроме того, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] может использоваться для идентификации и загрузки файлы из различных мест, включая следующие:  
  
-   Текущая сборка.  
  
-   Сборка, на которую указывает ссылка.  
  
-   Расположение относительно сборки.  
  
-   Начальный веб\-узел приложения.  
  
 Для обеспечения согласованного механизма идентификации и загрузки этих типов файлов из указанных мест [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] использует расширяемость *схемы URI типа "pack"*.  Этот раздел содержит обзор данной схемы, описывает создание [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" для различных скриптов, показывает абсолютное и относительное разрешение [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] и [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], а также описывает использование [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" из разметки и кода.  
  
   
  
<a name="The_Pack_URI_Scheme"></a>   
## Схема URI типа "pack"  
 Схема [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" используется спецификацией [Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255) \(OPC\), которая описывает модель для организации и определения содержимого.  Основными элементами этой модели являются пакеты и части. При этом *пакет* представляет собой логический контейнер для одной или нескольких логических *частей*.  Эта структура показана на следующем рисунке.  
  
 ![Схема пакета и частей](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.png "WPFPackURISchemeFigure1")  
  
 Чтобы идентифицировать части, спецификация OPC использует расширяемость RFC 2396 \(Uniform Resource Identifiers \(URI\): Generic Syntax\) для определения схемы [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
 Схема, заданная [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], определяется по его префиксу, например http, ftp или file.  Схема [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" использует "пакет" в качестве схемы и содержит два компонента: полномочия и путь.  Ниже приведен формат для [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
 пакет:\/\/*полномочия*\/*путь*  
  
 *Полномочия*  указывают тип пакета, в котором содержится часть, а *путь* указывает расположение части внутри пакета.  
  
 Эта структура продемонстрирована на следующем рисунке.  
  
 ![Отношение между пакетом, сертификацией и путем](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.png "WPFPackURISchemeFigure2")  
  
 Пакеты и части являются аналогами для приложений и файлов. При этом приложение \(пакет\) может включать в себя один или несколько файлов \(частей\), например, следующие:  
  
-   Файлы ресурсов, скомпилированные в локальную сборку.  
  
-   Файлы ресурсов, скомпилированные в сборку, на которую указывает ссылка.  
  
-   Файлы ресурсов, скомпилированные в ссылающуюся сборку.  
  
-   Файлы содержимого.  
  
-   Файлы исходного узла.  
  
 Для доступа к этим типам файлов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживает два вида полномочий: application:\/\/\/ и siteoforigin:\/\/\/.  Полномочия application:\/\/\/ идентифицируют файлы данных приложения, известные на момент компиляции, в том числе файлы ресурсов и содержимого.  Полномочия siteoforigin:\/\/\/ определяют файлы исходного узла.  Области полномочий показаны на следующем рисунке.  
  
 ![Схема URI типа “pack”](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")  
  
> [!NOTE]
>  Компонент полномочий [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" является встроенным [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], указывающим на пакет, и должен соответствовать стандарту RFC 2396.  Кроме того, символ "\/" должен быть заменен символом ",", а зарезервированные символы \(например, "%" и "?"\) необходимо заменять escape\-последовательностями.  Подробности см. в OPC.  
  
 В следующих разделах рассматривается построение пакета [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] с использованием этих полномочий с соответствующими путями для идентификации файлов ресурса, содержимого и исходного узла.  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## URI типа "pack" для файлов ресурса  
 Файлы ресурсов настраиваются как элементы [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` и компилируются в сборки.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживает конструирование пакета [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], который может использоваться для идентификации файлов ресурсов, компилируемых в локальную сборку или в сборку, на которую ссылается локальная сборка.  
  
<a name="Local_Assembly_Resource_File"></a>   
### Файл ресурсов локальной сборки  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла ресурсов, который компилируется в локальную сборку, использует следующие полномочия и путь:  
  
-   **Полномочия**: application:\/\/\/.  
  
-   **Путь**: имя файла ресурсов, включая его путь относительно корня папки проекта локальной сборки.  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], расположенного в корне папки проекта локальной сборки.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 В следующем примере показан пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], расположенного во вложенной папке проекта локальной сборки.  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### Файл ресурсов ссылочной сборки.  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла ресурсов, который компилируется в ссылочную сборку, использует следующие полномочия и путь:  
  
-   **Полномочия**: application:\/\/\/.  
  
-   **Путь**: имя файла ресурсов, который компилируется в ссылочную сборку.  Путь должен строиться согласно следующему формату:  
  
     *КраткоеИмяСборки*\[*;Версия*\]\[*;ОткрытыйКлюч*\];компонент\/*Путь*  
  
    -   **КраткоеИмяСборки**: короткое имя для ссылочной сборки.  
  
    -   **;Версия** \[необязательно\]: версия ссылочной сборки, которая содержит файл ресурсов.  Этот параметр используется при загрузке двух или более ссылочных сборок с одинаковым коротким именем.  
  
    -   **;ОткрытыйКлюч** \[необязательно\]: открытый ключ, использованный для подписи ссылочной сборки.  Этот параметр используется при загрузке двух или более ссылочных сборок с одинаковым коротким именем.  
  
    -   **;компонент**: указывает, что ссылочная сборка имеет ссылку из локальной сборки.  
  
    -   **\/Путь**: имя файла ресурсов, включая его путь относительно корня папки проекта ссылочной сборки.  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], расположенного в корне папки проекта ссылочной сборки.  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], расположенного во вложенной папке проекта ссылочной сборки.  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла ресурсов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], расположенного во вложенной папке проекта ссылочной сборки определенной версии.  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 Обратите внимание, что синтаксис [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файлов ресурсов ссылочной сборки может использоваться только с полномочием application:\/\/\/.  Например, приведенный ниже пример не поддерживается в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## URI типа "pack" для файлов содержимого  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла содержимого использует следующие полномочия и путь:  
  
-   **Полномочия**: application:\/\/\/.  
  
-   **Путь**: имя файла содержимого, включая его путь относительно расположения главной выполнямой сборки приложения в файловой системе.  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла содержимого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], расположенного в той же папке в качестве исполняемой сборки.  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла содержимого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], расположенного во вложенной папке относительно исполняемой сборки приложения.  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  К файлам содержимого [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] перейти невозможно.  Схема [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] поддерживает только переход к файлам [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], которые расположены на начальном узле.  
  
<a name="The_siteoforigin_____Authority"></a>   
## URI типа "pack" для начального узла  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла начального узла использует следующие полномочия и путь:  
  
-   **Полномочия**: siteoforigin:\/\/\/.  
  
-   **Путь**: имя файла начального узла, включая путь относительно места, из которого была запущена исполняемая сборка.  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла начального узла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], хранящегося в месте, из которого запускается исполняемая сборка.  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла начального узла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], хранящегося во вложенной папке относительно места, из которого запускается исполняемая сборка приложения.  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## Файлы страницы  
 Файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], которые настроены как элементы [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page`, компилируются в сборки таким же образом, как и файлы ресурсов.  Следовательно, элементы [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` могут быть идентифицированы с помощью [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" для файлов ресурсов.  
  
 Типы файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], которые обычно настраиваются как элементы [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` имеют в качестве корневого элемента один из нижеперечисленных:  
  
-   <xref:System.Windows.Window?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=fullName>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=fullName>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## Абсолютныеи относительные URI типа "pack"  
 Полный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" включает в себя схему, полномочия и путь, и считается абсолютным [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  Для упрощения разработки элементы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обычно позволяют задавать соответствующие атрибуты с относительным [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", который включает только путь.  
  
 В качестве пример рассмотрим следующий абсолютный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для файла ресурсов в локальной сборке.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 Относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", который ссылается на этот файл ресурсов, будет выглядеть следующим образом.  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  Поскольку файлы начального узла не связаны со сборками, на них можно ссылаться только при помощи абсолютного [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack".  
  
 По умолчанию относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" рассматривается относительно расположения разметки или кода, содержащего ссылку.  Однако, если в начале используется обратная косая черта,то относительного [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" рассматривается относительно корня приложения.  В качестве примера рассмотрим следующую структуру проекта.  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 Если Page1.xaml содержит [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], который ссылается на *Root*\\SubFolder\\Page2.xaml, ссылка может использовать следующий относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
 `Page2.xaml`  
  
 Если Page1.xaml содержит [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], который ссылается на *Root*\\Page2.xaml, ссылка может использовать следующий относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## Разрешение URI типа "pack"  
 Формат [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" позволяет [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" выглядеть одинаково для различных типов файлов.  В качестве примера рассмотрим следующий абсолютный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 Этот абсолютный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" может ссылаться на файлы ресурсов в локальной сборке или на файлы содержимого.  То же самое верно для следующего относительного [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `/ResourceOrContentFile.xaml`  
  
 Чтобы определить тип файла, на который ссылается [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] разрешает [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] для файлов ресурсов в локальных сборках и файлах содержимого с помощью следующей логики:  
  
1.  Выполняется проверка метаданных сборки на атрибут <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, который соответствует [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
2.  Если атрибут <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> обнаружен, путь [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" ссылается на файл содержимого.  
  
3.  Если атрибут <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> отсутствует, выполняется проверка файлов ресурсов набора, которые компилируются в локальную сборку.  
  
4.  Если обнаружен файл ресурсов, который соответствует пути [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", то путь [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" ссылается на файл ресурсов.  
  
5.  Если ресурс не найден, то созданный <xref:System.Uri> является недействительным.  
  
 Разрешение [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] не применяется для [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], которые ссылаются на следующие объекты:  
  
-   Файлы содержимого в ссылочных сборках: эти типы файлов не поддерживаются [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   Внедренные файлы в ссылочных сборках: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], идентифицирующие их, являются уникальными, так как включают в себя имя ссылочной сборки и суффикс`;component`.  
  
-   Файлы начального узла: определяющие их [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] являются уникальными, поскольку это единственные файлы, которые могут быть идентифицированы по [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", содержащему полномочия siteoforigin:\/\/\/.  
  
 Единственным упрощением, которое позволяет разрешение [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", является частичная независимость кода от расположения файлов ресурсов и содержимого.  Например, если имеется файл ресурса в локальной сборке, который перенастроен в файл содержимого, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для ресурса останется таким же. Это же будет справедливо и для кода, использующего [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
<a name="Programming_with_Pack_URIs"></a>   
## Программирование с использованием URI типа "pack"  
 Многие классы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] реализуют свойства, которые могут быть установлены с помощью [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", например следующие:  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=fullName>  
  
 Эти свойства могут быть заданы из разметки и из кода.  В этом разделе демонстрируются основные конструкции для разметки и кода, а также приводятся примеры частых скриптов.  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### Использование URI типа "pack" в разметке  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" указывается в разметке путем установки элемента атрибута с помощью [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  Примеры.  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 Таблица 1 демонстрирует различные абсолютные [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", которые можно указывать в разметке.  
  
 Таблица 1. Абсолютные URI типа "pack" в разметке  
  
|Файл|Абсолютный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack"|  
|----------|-----------------------------------------------------------------------------------------|  
|Файл ресурсов — локальная сборка|`"pack://application:,,,/ResourceFile.xaml"`|  
|Файл ресурсов во вложенной папке — локальная сборка|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|Файл ресурсов — ссылочная сборка|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Файл ресурсов во вложенной папке ссылочной сборки|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Файл ресурсов в ссылочной сборке с поддержкой версий|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|Файл содержимого|`"pack://application:,,,/ContentFile.xaml"`|  
|Файл содержимого во вложенной папке|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|Файл начального узла|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|Файл начального узла во вложенной папке|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 Таблица 2 демонстрирует различные относительные [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", которые можно задавать в разметке.  
  
 Таблица 2. Относительные URI типа "pack" в разметке  
  
|Файл|Относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack"|  
|----------|--------------------------------------------------------------------------------------------|  
|Файл ресурсов в локальной сборке|`"/ResourceFile.xaml"`|  
|Файл ресурсов во вложенной папке локальной сборки|`"/Subfolder/ResourceFile.xaml"`|  
|Файл ресурсов в ссылочной сборке|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Файл ресурсов во вложенной папке ссылочной сборки|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Файл содержимого|`"/ContentFile.xaml"`|  
|Файл содержимого во вложенной папке|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### Использование URI типа "pack" в коде  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" указывается в коде путем создания экземпляра класса <xref:System.Uri> и передачи [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" в конструктор в качестве параметра.  Это показано в следующем примере.  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 По умолчанию класс <xref:System.Uri> рассматривает [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" как абсолютный.  Это приводит к возникновению исключения, если экземпляр класса <xref:System.Uri> создается относительным [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 К счастью, перегрузка <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> конструктора класса <xref:System.Uri> принимает аргумент типа <xref:System.UriKind>, что позволяет указать, является ли [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" абсолютным или относительным.  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml", UriKind.Relative);  
```  
  
 Указание параметров <xref:System.UriKind> или <xref:System.UriKind> требуется только в том случае, если предоставленный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" точно будет иметь тот или иной тип.  Если тип используемого [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" неизвестен \(например, когда пользователь вводит [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" во время выполнения\), следует использовать <xref:System.UriKind>.  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 Таблица 3 демонстрирует различные относительные [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", которые можно указать в коде с помощью <xref:System.Uri?displayProperty=fullName>.  
  
 Таблица 3. Абсолютные URI типа "pack" в коде  
  
|Файл|Абсолютный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack"|  
|----------|-----------------------------------------------------------------------------------------|  
|Файл ресурсов — локальная сборка|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|Файл ресурсов во вложенной папке — локальная сборка|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Файл ресурсов — ссылочная сборка|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Файл ресурсов во вложенной папке ссылочной сборки|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Файл ресурсов в ссылочной сборке с поддержкой версий|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Файл содержимого|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|Файл содержимого во вложенной папке|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|Файл начального узла|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|Файл начального узла во вложенной папке|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 Таблица 4 демонстрирует различные относительные [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", которые можно указать в коде с помощью <xref:System.Uri?displayProperty=fullName>.  
  
 Таблица 4. Относительные URI типа "pack" в коде  
  
|Файл|Относительный [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack"|  
|----------|--------------------------------------------------------------------------------------------|  
|Файл ресурсов — локальная сборка|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|Файл ресурсов во вложенной папке — локальная сборка|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Файл ресурсов — ссылочная сборка|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|Файл ресурсов во вложенной папке — ссылочная сборка|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Файл содержимого|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|Файл содержимого во вложенной папке|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### Общие сценарии URI типа "pack"  
 В предыдущих разделах обсуждались способы создания [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" для идентификации файлов ресурсов, содержимого и начального узла.  В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] эти конструкции используются различными способами, и в следующих разделах будут рассмотрены некоторые общие способы использования.  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### Указание отображения пользовательского интерфейса при запуске приложения  
 <xref:System.Windows.Application.StartupUri%2A> указывает первый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для отображения при запуске приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Для автономных приложений [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] может быть окном, как показано в следующем примере.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 Автономные приложения и [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] также могут указать страницу в качестве начального пользовательского интерфейса, как показано в следующем примере.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 Если приложение является автономным приложением, а страница указывается с <xref:System.Windows.Application.StartupUri%2A>, то [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] открывает <xref:System.Windows.Navigation.NavigationWindow> для размещения страницы.  Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] страница отображается в браузере узла.  
  
<a name="Navigating_to_a_Page"></a>   
#### Перемещение на страницу  
 В следующем примере показан способ перехода на страницу.  
  
 [!code-xml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Дополнительные сведения о различных способах перехода в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Specifying_a_Window_Icon"></a>   
#### Задание значка окна  
 В следующем примере показано использование URI для указания значка окна.  
  
 [!code-xml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 Дополнительные сведения см. в разделе <xref:System.Windows.Window.Icon%2A>.  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### Загрузка изображений, звуковых и видео файлов  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет приложениям использовать разнообразные типы мультимедиа, каждый из которых может быть определен и загружен с помощью [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", как показано в следующих примерах.  
  
 [!code-xml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 Дополнительные сведения по работе с медиа содержимым см. в разделе [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md).  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### Загрузка словаря ресурсов с начального узла  
 Словари ресурсов \(<xref:System.Windows.ResourceDictionary>\) можно использовать для поддержки тем приложений.  Единственным способом создания и управления темами является создание нескольких тем в качестве словарей ресурсов, расположенных на начальном узле приложения.  Это позволяет добавлять и обновлять темы без повторной компиляции и повторного развертывания приложения.  Определить и загрузить эти словари ресурсов можно с помощью [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack", как показано в следующем примере.  
  
 [!code-xml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 Обзор тем в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## См. также  
 [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)