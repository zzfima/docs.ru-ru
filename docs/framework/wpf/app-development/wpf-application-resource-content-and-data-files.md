---
title: "Ресурсы, Содержимое и Файлы данных WPF-приложения | Microsoft Docs"
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
  - "разработка приложений [WPF], файлы"
  - "управление приложениями [WPF]"
  - "файлы содержимого [WPF]"
  - "внедренные ресурсы [WPF]"
  - "файлы [WPF]"
  - "неупакованные ресурсы [WPF]"
  - "ссылки на файлы приложений [WPF]"
  - "удаленные файлы [WPF]"
  - "файлы ресурсов [WPF]"
  - "файлы исходного сайта [WPF]"
  - "приложение WPF, файлы"
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Ресурсы, Содержимое и Файлы данных WPF-приложения
Приложения [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] обычно зависят от файлов с неисполняемыми данными, такими как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], изображения, видео и аудио.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] предоставляет специальную поддержку при настройке, распознавании и использовании этих типов файлов данных, называемых файлами данных приложения.  Эта поддержка относится к определенному набору типов файлов данных приложения, включая:  
  
-   **Файлы ресурсов**: файлы данных, скомпилированные либо в исполняемую, либо в библиотечную сборку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   **Файлы содержимого**: автономные файлы данных, имеющие явную связь с исполняемой сборкой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   **Файлы исходного узла**: автономные файлы данных, не имеющие связи с исполняемой сборкой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 Важным различием между этими тремя типами файлов является то, что файлы ресурсов и содержимого известны во время построения; сборка имеет явно заданные сведения о них.  Однако сборка может вообще не иметь сведений о файлах исходного узла или иметь неявные сведения через пакетную ссылку [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. В этом случае нет гарантии, что файл начального узла, на который указывает ссылка, действительно существует.  
  
 Для ссылки на файлы данных приложения [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] использует схему пакета [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], которая подробно описана в разделе [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)\).  
  
 В этом разделе описана настройка и использование файлов данных приложения.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Resource_Files"></a>   
## Файлы ресурсов  
 Если файл данных приложения должен быть всегда доступен приложению, то единственным способом, гарантирующим доступность, является компилирование его в основную исполняемую сборку приложения или одну из его сборок, на которую указывает ссылка.  Этот тип файлов данных приложения называется *файлом ресурса*.  
  
 Файлы ресурсов следует использовать в следующих случаях.  
  
-   Не требуется обновлять содержимое этого файла ресурсов после компилирования сборки.  
  
-   Требуется упростить распространение приложения, уменьшив количество зависимостей между файлами.  
  
-   Файлы данных приложения должны быть локализуемыми \(см. раздел [Общие сведения о глобализации и локализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)\).  
  
> [!NOTE]
>  Файлы ресурсов, описанные в этом разделе, отличаются от описанных в файлы ресурсов [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) и отличается от встроенные или связанные ресурсы, описанные в пределах  [Управление ресурсами приложения \(.NET\)](../Topic/Managing%20Application%20Resources%20\(.NET\).md).  
  
### Настройка файлов ресурсов  
 В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] файл ресурсов является файлом, который включен в проект [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] в качестве элемента `Resource`.  
  
```  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  В [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] файл ресурсов создается путем добавления файла к проекту и задания для его свойства `Build Action` значения `Resource`.  
  
 После создания проекта [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] компилирует ресурс в сборку.  
  
### Использование файлов ресурсов  
 Чтобы загрузить файл ресурсов, можно вызвать метод <xref:System.Windows.Application.GetResourceStream%2A> класса <xref:System.Windows.Application> при передаче пакета [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], идентифицирующего нужный файл ресурсов.  Метод <xref:System.Windows.Application.GetResourceStream%2A> возвращает объект <xref:System.Windows.Resources.StreamResourceInfo>, который предоставляет файл ресурсов в качестве объекта <xref:System.IO.Stream> и описывает тип его содержимого.  
  
 Например, следующий фрагмент кода показывает использование <xref:System.Windows.Application.GetResourceStream%2A> для загрузки файла ресурсов <xref:System.Windows.Controls.Page> и установки его как содержимого <xref:System.Windows.Controls.Frame> \(`pageFrame`\):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 В то время как вызов <xref:System.Windows.Application.GetResourceStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить дополнительные действия по преобразованию его к типу свойства, с помощью которого он будет устанавливаться.  Вместо этого можно позволить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream> путем загрузки файла ресурсов с помощью кода непосредственно в свойство типа.  
  
 В следующем примере показана загрузка <xref:System.Windows.Controls.Page> с помощью кода непосредственно в <xref:System.Windows.Controls.Frame> \(`pageFrame`\).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 В следующем примере разметка эквивалентна разметке в предыдущем примере.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### Файлы кода приложения как файлы ресурсов  
 На специальный набор файлов кода приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] можно ссылаться с помощью пакета [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], включая окна, страницы, документы нефиксированного формата и словари ресурсов.  Например, можно задать свойство <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName> с помощью пакета [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], ссылающегося на окно или страницу, которую требуется загрузить при запуске приложения.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Это можно сделать, когда файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] включен в проект [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] в качестве элемента `Page`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] при добавлении к проекту нового <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument> или <xref:System.Windows.ResourceDictionary> `Build Action` для файла разметки по умолчанию устанавливается в значение `Page`.  
  
 При компиляции проекта с элементами `Page`, элементы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] преобразуются в двоичный формат и компилируются в связанную сборку.  Следовательно, эти файлы могут быть использованы так же, как обычные файлы ресурсов.  
  
> [!NOTE]
>  Если файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] настроен в качестве элемента `Resource` и не имеет файла кода программной части, в сборку компилируется необработанный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а не двоичная версия необработанного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Content_Files"></a>   
## Файлы содержимого  
 *Файл содержимого* рассматривается исполняемой сборкой как свободный файл.  Несмотря на то что они не компилируются в сборку, сборки компилируются с метаданными, устанавливающими связь с каждым файлом содержимого.  
  
 Файлы содержимого необходимо использовать, когда приложению требуется определенный набор файлов данных приложения, которые необходимо обновлять без перекомпиляции использующей их сборки.  
  
### Настройка файлов содержимого  
 Чтобы добавить файл содержимого в проект, файл данных приложения должен быть включен как элемент `Content`.  Кроме того, так как файл содержимого не компилируется непосредственно в сборку, необходимо задать [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]```CopyToOutputDirectory` элемента метаданных, чтобы указать, что файл содержимого копируется в местоположение, имеющее отношение к сборке.  Если требуется, чтобы ресурс копировался в папку назначения при каждом построении проекта, установите для элемента метаданных `CopyToOutputDirectory` значение `Always`.  Также можно убедиться, что только новая версия ресурса копируется в папку назначения, с помощью значения `PreserveNewest`.  
  
 Ниже приведен файл, настроенный в качестве файла содержимого, который копируется в папку назначения только при добавлении в проект новой версии ресурса.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] создание файла содержимого осуществляется путем добавления файла в проект и задания для его `Build Action` значения `Content`, для `Copy to Output Directory` — `Copy always` \(то же, что и `Always`\) и `Copy if newer` \(то же, что и `PreserveNewest`\).  
  
 При сборке проекта атрибут <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> компилируется в метаданные сборки для каждого файла содержимого.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> указывает путь к файлу содержимого относительно его положения в проекте.  Например, если бы файл содержимого был расположен во вложенной папке проекта, дополнительные сведения о пути были бы включены в значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> также является значением пути к файлу содержимого в папке назначения построения.  
  
### Использование файлов содержимого  
 Чтобы загрузить файл содержимого, можно вызвать метод <xref:System.Windows.Application.GetContentStream%2A> класса <xref:System.Windows.Application> при передаче пакета [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], идентифицирующего нужный файл содержимого.  Метод <xref:System.Windows.Application.GetContentStream%2A> возвращает объект <xref:System.Windows.Resources.StreamResourceInfo>, который предоставляет файл содержимого в качестве объекта <xref:System.IO.Stream> и описывает тип его содержимого.  
  
 Например, следующий фрагмент кода показывает использование <xref:System.Windows.Application.GetContentStream%2A> для загрузки файла содержимого <xref:System.Windows.Controls.Page> и задания его в качестве содержимого <xref:System.Windows.Controls.Frame> \(`pageFrame`\).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 В то время как вызов <xref:System.Windows.Application.GetContentStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить дополнительные действия по преобразованию его к типу свойства, с помощью которого он будет устанавливаться.  Вместо этого можно позволить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream> путем загрузки файла ресурсов с помощью кода непосредственно в свойство типа.  
  
 В следующем примере показана загрузка <xref:System.Windows.Controls.Page> с помощью кода непосредственно в <xref:System.Windows.Controls.Frame> \(`pageFrame`\).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 В следующем примере разметка эквивалентна разметке в предыдущем примере.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## Файлы исходного узла  
 Файлы ресурсов имеют явную связь со сборками, на которые они распространяются, определенную в <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.  Но существуют случаи, когда необходимо установить либо неявную, либо не существующую связь между сборкой и файлом данных приложения. К таким случаям относятся следующие.  
  
-   Файл не существует во время компиляции.  
  
-   До времени выполнения неизвестно, какие файлы потребуются для сборки.  
  
-   Требуется возможность обновления файлов без перекомпиляции сборки, с которой они связаны.  
  
-   В приложение используются файлы данных большого размера, такие как аудио\- и видеофайлы, и необходимо предоставить пользователю возможность загружать их только по желанию.  
  
 Загрузить файлы этих типов можно с помощью традиционных схем [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], таких как file:\/\/\/ и http:\/\/.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Однако схемы file:\/\/\/ и http:\/\/ требуют полного доверия приложения.  Если приложение [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] было запущено из Интернета или интрасети и оно запрашивает только набор разрешений, предоставляемых приложениям, запускаемым таким образом, свободные файлы могут быть загружены только с исходного узла приложения \(расположения запуска\).  Такие файлы называются файлами *исходного узла*.  
  
 В приложениях с частичным доверием используются только файлы исходного узла, однако сами файлы этого типа могут использоваться и в других приложениях.  Приложениям с полным доверием по\-прежнему может требоваться загрузить файлы данных приложения, о которых они не знают во время построения. Хотя приложения с полным доверием могут использовать file:\/\/\/, вполне вероятно, что файлы данных приложения будут установлены в ту же папку, что и сборка приложения, или вложенную папку.  В этом случае использование ссылки на исходный сайт является более простым способом, чем использование file:\/\/\/, так как при использовании file:\/\/\/ требуется указывать полный путь к файлу.  
  
> [!NOTE]
>  Файлы исходного узла не кэшируются с [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] на клиентском компьютере, в отличие от файлов содержимого.  Поэтому они загружаются только по специальному запросу.  Если приложение [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] содержит файлы мультимедиа большого объема, то их настройка в качестве файлов исходного узла намного ускоряет начальный запуск приложения, а файлы будут загружаться только по требованию.  
  
### Настройка файлов исходного узла  
 Если файлы исходного узла не существуют или неизвестны во время компиляции, необходимо использовать традиционные средства для обеспечения доступности необходимых файлов во время выполнения, включая использование либо программы командной строки `XCopy`, либо [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Если во время компиляции известны файлы, которые должны быть расположены на исходном узле, но все еще требуется избежать явных зависимостей, то можно добавить эти файлы в проект [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] в качестве элемента `None`.  Как и для файлов содержимого, необходимо установить атрибут [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory`, чтобы указать, что файл исходного узла скопируется в местоположение, имеющее отношение к сборки, указав значение `Always` или `PreserveNewest`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] файл исходного узла создается путем добавления файла к проекту и установления для его `Build Action` значения `None`.  
  
 При построении проекта [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] копирует указанные файлы в папку назначения.  
  
### Использование файлов исходного сайта  
 Чтобы загрузить файл исходного сайта, можно вызвать метод <xref:System.Windows.Application.GetRemoteStream%2A> класса <xref:System.Windows.Application> при передаче пакета [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], идентифицирующего нужный файл исходного сайта.  Метод <xref:System.Windows.Application.GetRemoteStream%2A> возвращает объект <xref:System.Windows.Resources.StreamResourceInfo>, который предоставляет файл исходного сайта в качестве объекта <xref:System.IO.Stream> и описывает тип его содержимого.  
  
 Например, следующий фрагмент кода иллюстрирует использование <xref:System.Windows.Application.GetRemoteStream%2A> для загрузки файла исходного узла <xref:System.Windows.Controls.Page> и установки его в качестве содержимого <xref:System.Windows.Controls.Frame> \(`pageFrame`\).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 В то время как вызов <xref:System.Windows.Application.GetRemoteStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить дополнительные действия по преобразованию его к типу свойства, с помощью которого он будет устанавливаться.  Вместо этого можно позволить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream> путем загрузки файла ресурсов с помощью кода непосредственно в свойство типа.  
  
 В следующем примере показана загрузка <xref:System.Windows.Controls.Page> с помощью кода непосредственно в <xref:System.Windows.Controls.Frame> \(`pageFrame`\).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 В следующем примере разметка эквивалентна разметке в предыдущем примере.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## Повторное построение после изменения типа построения  
 После изменения типа построения файла данных приложения необходимо осуществить повторную сборку всего приложения для применения изменений.  Если просто выполнить построение приложения, изменения применяться не будут.  
  
## См. также  
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)