---
title: Ресурсы, Содержимое и Файлы данных WPF-приложения
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bcf0a725b7b3467a50a9f51850709dd972da217d
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="wpf-application-resource-content-and-data-files"></a>Ресурсы, Содержимое и Файлы данных WPF-приложения
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] приложения часто зависят от файлов, содержащих данные не является исполняемым, такие как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], изображения, видео и аудио. Windows Presentation Foundation (WPF) предлагает специальную поддержку для настройки, определения и использования этих типов файлов данных, которые называются файлы данных приложения. Эта поддержка относится к определенному набору типов файлов данных приложения, включая следующие:  
  
-   **Файлы ресурсов**: файлы данных, которые компилируются в исполняемый файл или библиотека [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборки.  
  
-   **Файлы содержимого**: автономные файлы данных, имеющие явную связь с исполняемой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборки.  
  
-   **Файлы исходного узла**: автономные файлы данных, не имеющие связи с исполняемой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборки.  
  
 Важным отличием между этими тремя типами файлов является то, что файлы ресурсов и файлы содержимого известны во время построения. Сборка содержит информацию о них. Для файлов исходного узла, однако сборка может вообще нет сведений ни о них, или неявные сведения через пакетную [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] ссылку, в случае последнее, нет никакой гарантии, что указанный файл исходного сайта существуют.  
  
 Для ссылки на файлы данных приложения Windows Presentation Foundation (WPF) использует пакет [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] схему, в которой подробно описывается в [пакет URI в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).  
  
 В этом разделе описывается настройка и использование файлов данных приложения.  
  
  
<a name="Resource_Files"></a>   
## <a name="resource-files"></a>Файлы ресурсов  
 Если файл данных приложения всегда должен быть доступен для приложения, то единственный способ гарантировать доступность — скомпилировать его в главную исполняемую сборку приложения или в одну из его указанных ссылками сборок. Этот тип файлов данных приложения называется *файла ресурсов*.  
  
 Нужно использовать файлы ресурсов, если:  
  
-   Не нужно обновлять содержимое файла ресурсов после его компиляции в сборку.  
  
-   Необходимо упростить распространение приложения за счет уменьшения количества зависимостей между файлами.  
  
-   Файлы данных приложения должны быть локализуемыми (см. [Общие сведения о локализации и глобализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
>  Файлы ресурсов, описанные в этом разделе отличаются от описанных файлы ресурсов в [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) и отличаются от внедренных или связанных ресурсов, приведенных в [управление ресурсами приложения (.NET) ](http://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e).  
  
### <a name="configuring-resource-files"></a>Настройка файлов ресурсов  
 В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], файл ресурсов — это файл, включенный в [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] проект в качестве `Resource` элемента.  
  
```xml  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  В [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], создайте файл ресурсов путем добавления файла в проект и присвоив его `Build Action` для `Resource`.  
  
 При построении проекта, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] компилирует ресурс в сборку.  
  
### <a name="using-resource-files"></a>Использование файлов ресурсов  
 Чтобы загрузить файл ресурсов, можно вызвать <xref:System.Windows.Application.GetResourceStream%2A> метод <xref:System.Windows.Application> класса, передавая пакете [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , определяющий нужный файл ресурсов. <xref:System.Windows.Application.GetResourceStream%2A> Возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который представляет файл ресурсов как <xref:System.IO.Stream> и описывает тип его содержимого.  
  
 Например, ниже показано использование <xref:System.Windows.Application.GetResourceStream%2A> для загрузки <xref:System.Windows.Controls.Page> ресурсов файла и задать его в качестве содержимого <xref:System.Windows.Controls.Frame> (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 При вызове <xref:System.Windows.Application.GetResourceStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить его преобразование в тип свойства, он будет устанавливаться с помощью дополнительной работы. Вместо этого можно позволить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream> путем загрузки файла ресурсов непосредственно в свойство типа, с помощью кода.  
  
 В следующем примере показано, как загрузить <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> (`pageFrame`) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Файлы кода приложения как файлы ресурсов  
 Специальный набор [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] файлы кода приложения можно ссылаться с помощью пакета [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], включая windows, страницы, документы нефиксированного формата и словари ресурсов. Например, можно задать <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> свойства с помощью пакета [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , ссылающегося на окно или страницу, которые требуется загрузить при запуске приложения.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Вы можете это сделать, если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл включен в [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] проект в качестве `Page` элемента.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], добавляется новый <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, или <xref:System.Windows.ResourceDictionary> в проект `Build Action` для разметки файла по умолчанию будет `Page`.  
  
 При создании проекта с `Page` компиляции элементов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементы преобразуются в двоичный формат и компилируются в связанную сборку. Следовательно, эти файлы можно использовать таким же образом, как и обычные файлы ресурсов.  
  
> [!NOTE]
>  Если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл настроен как `Resource` элемента и не содержит файл кода, необработанный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] компилируется в сборку, а не двоичная версия необработанного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>Файлы с содержимым  
 Объект *содержимого файла* распространяется в виде свободный файл исполняемую сборку. Несмотря на то, что они не компилируются в сборку, сборки компилируются с метаданными, которые устанавливают связь с каждым файлом содержимого.  
  
 Файлы содержимого необходимо использовать, если приложению требуется определенный набор файлов данных приложения, которые нужно обновлять без повторной компиляции использующей их сборки.  
  
### <a name="configuring-content-files"></a>Настройка файлов содержимого  
 Чтобы добавить файл содержимого в проект, файл данных приложения должен быть включен как `Content` элемента. Кроме того, так как файл содержимого не компилируется непосредственно в сборку, необходимо задать [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` элемента метаданных, чтобы указать, что файл содержимого копируется в расположение, к сборке. Если требуется, чтобы ресурс копируются в выходную папку сборки при каждом построении проекта, задать `CopyToOutputDirectory` элемент метаданных с `Always` значение. В противном случае убедитесь, что только новая версия ресурса копируется в выходную папку построения с использованием `PreserveNewest` значение.  
  
 Ниже показан файл, настроенный как файл содержимого, который копируется в папку выходных данных построения только при добавлении новой версии ресурса в проект.  
  
```xml  
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
>  В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], создать файл содержимого путем добавления файла в проект и присвоив его `Build Action` для `Content`и задайте его `Copy to Output Directory` для `Copy always` (то же, что `Always`) и `Copy if newer` (то же, что `PreserveNewest`).  
  
 При построении проекта, <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> атрибут компилируется в метаданные сборки для каждого файла содержимого.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> указывает путь к файлу содержимого относительно его положения в проекте. Например, если файл содержимого был размещен во вложенной папке проекта, Дополнительные сведения о пути были бы включены в <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> значение.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Значение также является значением пути к файлу содержимого в выходной папке сборки.  
  
### <a name="using-content-files"></a>Использование файлов содержимого  
 Чтобы загрузить файл содержимого, можно вызвать <xref:System.Windows.Application.GetContentStream%2A> метод <xref:System.Windows.Application> класса, передавая пакете [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , определяющий нужный файл содержимого. <xref:System.Windows.Application.GetContentStream%2A> Возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл содержимого в качестве <xref:System.IO.Stream> и описывает тип его содержимого.  
  
 Например, ниже показано использование <xref:System.Windows.Application.GetContentStream%2A> для загрузки <xref:System.Windows.Controls.Page> содержимого файла и задать его в качестве содержимого <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 При вызове <xref:System.Windows.Application.GetContentStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить его преобразование в тип свойства, он будет устанавливаться с помощью дополнительной работы. Вместо этого можно позволить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream> путем загрузки файла ресурсов непосредственно в свойство типа, с помощью кода.  
  
 В следующем примере показано, как загрузить <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> (`pageFrame`) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>Файлы исходного узла  
 Файлы ресурсов имеют явную связь со сборками, которым они распространяются, в соответствии с определением <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>. Но иногда необходимо установить неявную либо несуществующую связь между сборкой и файлом данных приложения, например, в следующих случаях:  
  
-   Файл не существует во время компиляции.  
  
-   Неизвестно, какие файлы потребуются для сборки до времени выполнения.  
  
-   Нужна возможность обновлять файлы без повторной компиляции сборки, связанной с ними.  
  
-   Приложение использует большие файлы данных, такие как аудио и видео, и необходимо, чтобы пользователи могли их загружать только при необходимости.  
  
 Имеется возможность загрузки этих типов файлов с помощью традиционных [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] схем, таких как file:/// и http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Однако схемы file:/// и http:// требуют полного доверия приложения. Если приложение является [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] было запущено из Интернета или интрасети, и оно запрашивает только набор разрешений, предоставляемых приложениям, запускаемым таким образом, свободные файлы могут быть загружены только из узла приложения (источника место запуска). Такие файлы называются *исходного узла* файлов.  
  
 Файлы исходного узла являются единственным вариантом для приложений с частичным доверием, хотя и не ограничиваются такими приложениями. Приложениям с полным доверием, возможно, все равно придется загружать файлы данных приложений, о которых они не знают во время построения. Хотя приложения с полным доверием могут использовать схему file:///, вероятнее всего, файлы данных приложения будут установлены в одну папку или вложенную папку со сборкой приложения. В этом случае использовать ссылки на исходный узел проще, чем использовать file:///, так как последнее требует разработки полного пути к файлу.  
  
> [!NOTE]
>  Файлы не кэшируются с исходного узла [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] на клиентском компьютере, пока файлы содержимого. Следовательно, они загружаются только по специальному запросу. Если [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] приложение имеет больших файлов мультимедиа, их настройка в качестве файлов исходного узла означает начальный запуск приложения выполняется гораздо быстрее и файлы будут загружаться только по требованию.  
  
### <a name="configuring-site-of-origin-files"></a>Настройка файлов исходного узла  
 Если файлы исходного узла не существуют или неизвестны во время компиляции, необходимо использовать традиционные средства для обеспечения необходимые файлы доступны во время выполнения, включая использование либо `XCopy` программы командной строки или [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Если вы знаете во время компиляции файлов, которые должны быть расположены на исходном узле, но все еще требуется избежать явных зависимостей, можно добавить эти файлы в [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] проект в качестве `None` элемента. Как и для файлов содержимого, необходимо задать [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` атрибут, чтобы указать, что узел исходный файл копируется в расположение, к сборке, указывая либо `Always` значение или `PreserveNewest` значение.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], создать сайт исходный файл путем добавления файла в проект и присвоив его `Build Action` для `None`.  
  
 При построении проекта, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] копирует указанные файлы в выходной папке сборки.  
  
### <a name="using-site-of-origin-files"></a>Использование файлов исходного узла  
 Чтобы загрузить файл исходного сайта, можно вызвать <xref:System.Windows.Application.GetRemoteStream%2A> метод <xref:System.Windows.Application> класса, передавая пакете [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , определяющее требуемый сайт исходного файла. <xref:System.Windows.Application.GetRemoteStream%2A> Возвращает <xref:System.Windows.Resources.StreamResourceInfo> объекта, который предоставляет сайта исходный файл как <xref:System.IO.Stream> и описывает тип его содержимого.  
  
 Например, ниже показано использование <xref:System.Windows.Application.GetRemoteStream%2A> для загрузки <xref:System.Windows.Controls.Page> исходного узла файла и задать его в качестве содержимого <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 При вызове <xref:System.Windows.Application.GetRemoteStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить его преобразование в тип свойства, он будет устанавливаться с помощью дополнительной работы. Вместо этого можно позволить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream> путем загрузки файла ресурсов непосредственно в свойство типа, с помощью кода.  
  
 В следующем примере показано, как загрузить <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> (`pageFrame`) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>Повторное построение после изменения типа построения  
 После изменения типа построения файла данных приложения необходимо перестроить все приложение, чтобы обеспечить применение этих изменений. Если просто выполнить построение приложения, изменения не применяются.  
  
## <a name="see-also"></a>См. также  
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)
