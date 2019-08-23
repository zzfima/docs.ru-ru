---
title: Ресурсы, Содержимое и Файлы данных WPF-приложения
ms.date: 03/30/2017
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
ms.openlocfilehash: 57eae5067a72777db2c19331029b6df679a9fdce
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956191"
---
# <a name="wpf-application-resource-content-and-data-files"></a>Ресурсы, Содержимое и Файлы данных WPF-приложения
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]приложения часто зависят от файлов, содержащих неисполняемые данные, такие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]как, изображения, видео и звук. Windows Presentation Foundation (WPF) предлагает специальную поддержку для настройки, идентификации и использования этих типов файлов данных, которые называются файлами данных приложения. Эта поддержка относится к определенному набору типов файлов данных приложения, включая следующие:  
  
- **Файлы ресурсов**: Файлы данных, компилируемые в исполняемый файл или сборку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] библиотеки.  
  
- **Файлы содержимого**: Автономные файлы данных с явной связью с исполняемой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборкой.  
  
- **Файлы исходного узла**: Автономные файлы данных, не имеющие связи с исполняемой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборкой.  
  
 Важным отличием между этими тремя типами файлов является то, что файлы ресурсов и файлы содержимого известны во время построения. Сборка содержит информацию о них. Однако для файлов исходного узла сборка может вообще не иметь сведений о них или неявного набора знаний через ссылку на пакет [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] ; в последнем случае нет никакой гарантии, что упоминаемый исходный файл узла действительно существует.  
  
 Для ссылки на файлы данных приложения Windows Presentation Foundation (WPF) использует схему Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] , которая подробно описана в разделе URI типа " [Pack" в WPF](pack-uris-in-wpf.md).  
  
 В этом разделе описывается настройка и использование файлов данных приложения.  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a>Файлы ресурсов  
 Если файл данных приложения всегда должен быть доступен для приложения, то единственный способ гарантировать доступность — скомпилировать его в главную исполняемую сборку приложения или в одну из его указанных ссылками сборок. Этот тип файла данных приложения называется *файлом ресурсов*.  
  
 Нужно использовать файлы ресурсов, если:  
  
- Не нужно обновлять содержимое файла ресурсов после его компиляции в сборку.  
  
- Необходимо упростить распространение приложения за счет уменьшения количества зависимостей между файлами.  
  
- Файл данных приложения должен быть локализуемой (см. [Общие сведения о глобализации и локализации WPF](../advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
> Файлы ресурсов, описанные в этом разделе, отличаются от файлов ресурсов, описанных в [ресурсах XAML](../advanced/xaml-resources.md) , и отличаются от внедренных или связанных ресурсов, описанных в статье [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
### <a name="configuring-resource-files"></a>Настройка файлов ресурсов  
 В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]файл ресурсов — это файл, который включается в проект Microsoft Build Engine (MSBuild) в `Resource` качестве элемента.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> В [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]файл ресурсов создается путем добавления файла в проект и присвоения `Resource`ему `Build Action` значения.  
  
 При построении проекта MSBuild компилирует ресурс в сборку.  
  
### <a name="using-resource-files"></a>Использование файлов ресурсов  
 Чтобы загрузить файл ресурсов, можно вызвать <xref:System.Windows.Application.GetResourceStream%2A> метод <xref:System.Windows.Application> класса, передав ему пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , который определяет нужный файл ресурсов. <xref:System.Windows.Application.GetResourceStream%2A>Возвращает объект, который предоставляет файл ресурсов <xref:System.IO.Stream> как и описывает его тип содержимого. <xref:System.Windows.Resources.StreamResourceInfo>  
  
 Например, в следующем коде показано, как <xref:System.Windows.Application.GetResourceStream%2A> использовать для <xref:System.Windows.Controls.Page> загрузки файла ресурсов и его установки в <xref:System.Windows.Controls.Frame> качестве содержимого объекта (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Хотя при <xref:System.Windows.Application.GetResourceStream%2A> вызове предоставляется доступ <xref:System.IO.Stream>к, необходимо выполнить дополнительную работу по преобразованию в тип свойства, для которого будет задано значение. Вместо этого можно [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться о открытии и <xref:System.IO.Stream> преобразовании, загрузив файл ресурсов непосредственно в свойство типа с помощью кода.  
  
 В следующем примере показано, как загрузить объект <xref:System.Windows.Controls.Page> непосредственно <xref:System.Windows.Controls.Frame> в (`pageFrame`) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Файлы кода приложения как файлы ресурсов  
 На Специальный набор [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] файлов кода приложения можно ссылаться с помощью пакета [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], в том числе окон, страниц, документов нефиксированного формата и словарей ресурсов. Например, можно задать <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> свойство с пакетом [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , который ссылается на окно или страницу, которые необходимо загрузить при запуске приложения.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Это можно сделать, когда XAML-файл включается в проект MSBuild как `Page` элемент.  
  
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
> В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]добавляется новый <xref:System.Windows.Window>объект, <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page> `Page`,, или<xref:System.Windows.ResourceDictionary> в проект ,`Build Action` для файла разметки по умолчанию будет. <xref:System.Windows.Documents.FlowDocument>  
  
 При компиляции `Page` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] проекта с элементами элементы преобразуются в двоичный формат и компилируются в связанную сборку. Следовательно, эти файлы можно использовать таким же образом, как и обычные файлы ресурсов.  
  
> [!NOTE]
> Если файл настроен `Resource` в качестве элемента и не имеет файла кода программной части, то необработанный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] код компилируется в сборку, а не в двоичную версию RAW [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>Файлы с содержимым  
 *Файл содержимого* распространяется в виде свободного файла вместе с исполняемой сборкой. Несмотря на то, что они не компилируются в сборку, сборки компилируются с метаданными, которые устанавливают связь с каждым файлом содержимого.  
  
 Файлы содержимого необходимо использовать, если приложению требуется определенный набор файлов данных приложения, которые нужно обновлять без повторной компиляции использующей их сборки.  
  
### <a name="configuring-content-files"></a>Настройка файлов содержимого  
 Чтобы добавить файл содержимого в проект, в качестве `Content` элемента необходимо включить файл данных приложения. Более того, поскольку файл содержимого не компилируется непосредственно в сборку, необходимо задать элемент метаданных MSBuild `CopyToOutputDirectory` , чтобы указать, что файл содержимого копируется в расположение, относящееся к построенной сборке. Если требуется, чтобы ресурс копировался в выходную папку сборки при каждом построении проекта, необходимо задать `CopyToOutputDirectory` для элемента `Always` метаданных значение. В противном случае можно гарантировать, что только последняя версия ресурса копируется в выходную папку сборки с использованием `PreserveNewest` значения.  
  
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
> В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]файл содержимого создается путем добавления файла в проект и установки его `Copy if newer` `Always` `Build Action` в `Content`значение, а также для `Copy always` задания его `Copy to Output Directory` значения (то же, что `PreserveNewest`и).  
  
 При построении <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> проекта атрибут компилируется в метаданные сборки для каждого файла содержимого.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Значение параметра <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> указывает путь к файлу содержимого относительно его положения в проекте. Например, если файл содержимого находился во вложенной папке проекта, то в это <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> значение будет включен дополнительный путь к данным.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Значение является также значением пути к файлу содержимого в выходной папке построения.  
  
### <a name="using-content-files"></a>Использование файлов содержимого  
 Чтобы загрузить файл содержимого, можно вызвать <xref:System.Windows.Application.GetContentStream%2A> метод <xref:System.Windows.Application> класса, передав ему пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , идентифицирующий нужный файл содержимого. <xref:System.Windows.Application.GetContentStream%2A>Возвращает объект, который предоставляет файл содержимого в <xref:System.IO.Stream> виде и описывает его тип содержимого. <xref:System.Windows.Resources.StreamResourceInfo>  
  
 Например, в следующем коде показано, как <xref:System.Windows.Application.GetContentStream%2A> использовать для <xref:System.Windows.Controls.Page> загрузки файла содержимого и его установки в <xref:System.Windows.Controls.Frame> качестве содержимого объекта (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Хотя при <xref:System.Windows.Application.GetContentStream%2A> вызове предоставляется доступ <xref:System.IO.Stream>к, необходимо выполнить дополнительную работу по преобразованию в тип свойства, для которого будет задано значение. Вместо этого можно [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться о открытии и <xref:System.IO.Stream> преобразовании, загрузив файл ресурсов непосредственно в свойство типа с помощью кода.  
  
 В следующем примере показано, как загрузить объект <xref:System.Windows.Controls.Page> непосредственно <xref:System.Windows.Controls.Frame> в (`pageFrame`) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>Файлы исходного узла  
 Файлы ресурсов имеют явную связь со сборками, которые они распределяют вместе, как определено в <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>. Но иногда необходимо установить неявную либо несуществующую связь между сборкой и файлом данных приложения, например, в следующих случаях:  
  
- Файл не существует во время компиляции.  
  
- Неизвестно, какие файлы потребуются для сборки до времени выполнения.  
  
- Нужна возможность обновлять файлы без повторной компиляции сборки, связанной с ними.  
  
- Приложение использует большие файлы данных, такие как аудио и видео, и необходимо, чтобы пользователи могли их загружать только при необходимости.  
  
 Эти типы файлов можно загрузить с помощью традиционных [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] схем, таких как схемы file:///и http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Однако схемы file:/// и http:// требуют полного доверия приложения. Если приложение [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] запущено из Интернета или интрасети и запрашивает только набор разрешений, разрешенных для приложений, запускаемых из этих расположений, свободные файлы могут загружаться только с исходного узла приложения ( Расположение запуска). Такие файлы называются файлами *исходного узла* .  
  
 Файлы исходного узла являются единственным вариантом для приложений с частичным доверием, хотя и не ограничиваются такими приложениями. Приложениям с полным доверием, возможно, все равно придется загружать файлы данных приложений, о которых они не знают во время построения. Хотя приложения с полным доверием могут использовать схему file:///, вероятнее всего, файлы данных приложения будут установлены в одну папку или вложенную папку со сборкой приложения. В этом случае использовать ссылки на исходный узел проще, чем использовать file:///, так как последнее требует разработки полного пути к файлу.  
  
> [!NOTE]
> Файлы исходного узла не кэшируются [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] на клиентском компьютере, а файлы содержимого —. Следовательно, они загружаются только по специальному запросу. [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] Если приложение содержит большие файлы мультимедиа, их настройка в качестве файлов исходного узла означает, что начальный запуск приложения выполняется гораздо быстрее, а файлы скачиваются по запросу.  
  
### <a name="configuring-site-of-origin-files"></a>Настройка файлов исходного узла  
 Если файлы исходного сайта не существуют или неизвестны во время компиляции, необходимо использовать традиционные механизмы развертывания для обеспечения доступности необходимых файлов во время выполнения, в том числе с помощью `XCopy` программы командной строки или [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Если во время компиляции вы узнаете, какие файлы необходимо найти на исходном узле, но все равно хотите избежать явной зависимости, можно добавить эти файлы в проект MSBuild как `None` элемент. Как и в случае с файлами содержимого, необходимо задать атрибут `CopyToOutputDirectory` MSBuild, чтобы указать, что файл исходного узла копируется в расположение относительно сборки, указав `Always` либо значение `PreserveNewest` , либо значение.  
  
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
> В [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]создайте файл исходного узла, добавив файл в проект и задав для `None`него `Build Action` значение.  
  
 При построении проекта MSBuild копирует указанные файлы в выходную папку сборки.  
  
### <a name="using-site-of-origin-files"></a>Использование файлов исходного узла  
 Чтобы загрузить файл исходного узла, можно вызвать <xref:System.Windows.Application.GetRemoteStream%2A> метод <xref:System.Windows.Application> класса, передав ему пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , определяющий нужный файл исходного узла. <xref:System.Windows.Application.GetRemoteStream%2A>Возвращает объект, который предоставляет файл исходного узла <xref:System.IO.Stream> как и описывает его тип содержимого. <xref:System.Windows.Resources.StreamResourceInfo>  
  
 В следующем примере кода показано, как <xref:System.Windows.Application.GetRemoteStream%2A> использовать для <xref:System.Windows.Controls.Page> загрузки файла исходного узла и задать его в <xref:System.Windows.Controls.Frame> качестве содержимого объекта (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Хотя при <xref:System.Windows.Application.GetRemoteStream%2A> вызове предоставляется доступ <xref:System.IO.Stream>к, необходимо выполнить дополнительную работу по преобразованию в тип свойства, для которого будет задано значение. Вместо этого можно [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться о открытии и <xref:System.IO.Stream> преобразовании, загрузив файл ресурсов непосредственно в свойство типа с помощью кода.  
  
 В следующем примере показано, как загрузить объект <xref:System.Windows.Controls.Page> непосредственно <xref:System.Windows.Controls.Frame> в (`pageFrame`) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>Повторное построение после изменения типа построения  
 После изменения типа построения файла данных приложения необходимо перестроить все приложение, чтобы обеспечить применение этих изменений. Если просто выполнить построение приложения, изменения не применяются.  
  
## <a name="see-also"></a>См. также

- [URI типа "pack" в WPF](pack-uris-in-wpf.md)
