---
title: Файлы приложений, содержимое и файлы данных
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
ms.openlocfilehash: f17898972eeef66447060db32bae5fae377b710e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186202"
---
# <a name="wpf-application-resource-content-and-data-files"></a>Ресурсы, Содержимое и Файлы данных WPF-приложения
Приложения Microsoft Windows часто зависят от файлов, содержащих неисполняемые данные, такие как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]изображения, видео и аудио. Фонд презентации Windows (WPF) предлагает специальную поддержку для настройки, идентификации и использования этих типов файлов данных, которые называются файлами данных приложений. Эта поддержка относится к определенному набору типов файлов данных приложения, включая следующие:  
  
- **Файлы ресурсов**: Файлы данных, которые компилируются либо в исполняемой, либо в библиотеке WPF сборки.  
  
- **Файлы содержимого:** автономные файлы данных, которые имеют явную связь с исполняемой сборкой WPF.  
  
- **Файлы сайта Origin:** автономные файлы данных, не имеющие связи с исполняемой сборкой WPF.  
  
 Важным отличием между этими тремя типами файлов является то, что файлы ресурсов и файлы содержимого известны во время построения. Сборка содержит информацию о них. Однако для файлов сайта происхождения сборка может вообще не знать их или неявных знаний через ссылку на единый ресурсный идентификатор (URI); в случае последнего нет никакой гарантии того, что ссылки на сайт происхождения файл на самом деле существует.  
  
 Для ссылки на файлы данных приложений, Windows Презентация Фонд (WPF) использует пакет единообразного ресурса идентификатора (URI) Схема, которая подробно описана в [pack URIs в WPF](pack-uris-in-wpf.md)).  
  
 В этом разделе описывается настройка и использование файлов данных приложения.  

<a name="Resource_Files"></a>
## <a name="resource-files"></a>Файлы ресурсов  
 Если файл данных приложения всегда должен быть доступен для приложения, то единственный способ гарантировать доступность — скомпилировать его в главную исполняемую сборку приложения или в одну из его указанных ссылками сборок. Этот тип файла данных приложения известен как *файл ресурсов.*  
  
 Нужно использовать файлы ресурсов, если:  
  
- Не нужно обновлять содержимое файла ресурсов после его компиляции в сборку.  
  
- Необходимо упростить распространение приложения за счет уменьшения количества зависимостей между файлами.  
  
- Файл данных приложения должен быть локализован (см. Обзор глобализации [и локализации WPF).](../advanced/wpf-globalization-and-localization-overview.md)  
  
> [!NOTE]
> Файлы ресурсов, описанные в этом разделе, отличаются от файлов ресурсов, описанных в [XAML Resources,](../../../desktop-wpf/fundamentals/xaml-resources-define.md) и отличаются от встроенных или связанных ресурсов, описанных в [Ресурсах приложений управления (.NET).](/visualstudio/ide/managing-application-resources-dotnet)  
  
### <a name="configuring-resource-files"></a>Настройка файлов ресурсов  
 В WPF файл ресурсов — это файл, включенный в проект движка `Resource` сборки Майкрософт (MSBuild) в качестве элемента.  
  
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
> В Visual Studio вы создаете файл ресурса, добавляя `Build Action` `Resource`файл в проект и устанавливая его для .  
  
 Когда проект построен, MSBuild компилирует ресурс в сборку.  
  
### <a name="using-resource-files"></a>Использование файлов ресурсов  
 Для загрузки файла ресурса <xref:System.Windows.Application.GetResourceStream%2A> можно <xref:System.Windows.Application> вызвать метод класса, передав пакет URI, который идентифицирует нужный файл ресурса. <xref:System.Windows.Application.GetResourceStream%2A>возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который разоблачает <xref:System.IO.Stream> файл ресурса как тип содержимого и описывает его.  
  
 Например, следующий код показывает, <xref:System.Windows.Application.GetResourceStream%2A> как <xref:System.Windows.Controls.Page> использовать для загрузки файла <xref:System.Windows.Controls.Frame> ресурса и установить его в качестве содержимого (`pageFrame`  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 При <xref:System.Windows.Application.GetResourceStream%2A> вызове дает <xref:System.IO.Stream>вам доступ к, вам нужно выполнить дополнительную работу по преобразованию его в тип свойства, что вы будете устанавливать его с. Вместо этого вы можете позволить WPF позаботиться об открытии и преобразовании <xref:System.IO.Stream> файла ресурса непосредственно в свойство типа с помощью кода.  
  
 Ниже приведен о том, <xref:System.Windows.Controls.Page> как <xref:System.Windows.Controls.Frame> загрузить`pageFrame`непосредственно в ( ) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Файлы кода приложения как файлы ресурсов  
 Специальный набор файлов кода приложения WPF можно ссылаться с помощью пакетных URIs, включая окна, страницы, документы потока и словари ресурсов. Например, можно настроить <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> свойство пакетом URI, который ссылается на окно или страницу, которую вы хотели бы загрузить при запуске приложения.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Это можно сделать, когда файл XAML включен в `Page` проект MSBuild в качестве элемента.  
  
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
> В Visual Studio, вы <xref:System.Windows.Window> <xref:System.Windows.Navigation.NavigationWindow>добавляете новый , <xref:System.Windows.Controls.Page>, , <xref:System.Windows.Documents.FlowDocument>, или <xref:System.Windows.ResourceDictionary> в проект, `Build Action` для файла разметки будет по `Page`умолчанию.  
  
 Когда компилируется проект `Page` с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементами, элементы преобразуются в двоичный формат и компилируются в связанную сборку. Следовательно, эти файлы можно использовать таким же образом, как и обычные файлы ресурсов.  
  
> [!NOTE]
> Если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл настроен как `Resource` элемент и не имеет файла с кодом, сырье [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] компилируется в сборку, а не в двоичную версию товара. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
<a name="Content_Files"></a>
## <a name="content-files"></a>Файлы с содержимым  
 *Файл содержимого* распространяется как свободный файл вместе с исполняемой сборкой. Несмотря на то, что они не компилируются в сборку, сборки компилируются с метаданными, которые устанавливают связь с каждым файлом содержимого.  
  
 Файлы содержимого необходимо использовать, если приложению требуется определенный набор файлов данных приложения, которые нужно обновлять без повторной компиляции использующей их сборки.  
  
### <a name="configuring-content-files"></a>Настройка файлов содержимого  
 Чтобы добавить файл содержимого в проект, файл данных приложения должен быть включен в качестве элемента. `Content` Кроме того, поскольку файл содержимого не компилируется непосредственно `CopyToOutputDirectory` в сборку, необходимо установить элемент метаданных MSBuild, чтобы указать, что файл содержимого копируется в место, относительно построенной сборки. Если при каждом построении проекта ресурс копируется в папку вывода `CopyToOutputDirectory` сборки, вы `Always` установите элемент метаданных со значением. В противном случае можно гарантировать, что только новейшая версия ресурса `PreserveNewest` будет скопирована в папку вывода сборки с помощью значения.  
  
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
> В Visual Studio, вы создаете файл содержимого, добавляя файл в проект и `Always`установив `Copy if newer` его `PreserveNewest` `Build Action` `Content` `Copy to Output Directory` `Copy always` на , и установить его (так же, как ) и (так же, как ).  
  
 Когда проект построен, <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> атрибут компилируется в метаданные сборки для каждого файла содержимого.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> значения подразумевает путь к файлу содержимого относительно его положения в проекте. Например, если файл содержимого находится в подфайле проекта, дополнительная информация о пути будет включена в <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> значение.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> также значение пути к файлу содержимого в папке вывода сборки.  
  
### <a name="using-content-files"></a>Использование файлов содержимого  
 Чтобы загрузить файл содержимого, <xref:System.Windows.Application.GetContentStream%2A> можно вызвать метод <xref:System.Windows.Application> класса, передав пакет URI, который идентифицирует нужный файл содержимого. <xref:System.Windows.Application.GetContentStream%2A>возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл содержимого как <xref:System.IO.Stream> и описывает его тип содержимого.  
  
 В качестве примера, следующий <xref:System.Windows.Application.GetContentStream%2A> код показывает, как использовать для загрузки файла <xref:System.Windows.Controls.Page> содержимого и установить его в качестве содержания <xref:System.Windows.Controls.Frame> (`pageFrame`  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 При <xref:System.Windows.Application.GetContentStream%2A> вызове дает <xref:System.IO.Stream>вам доступ к, вам нужно выполнить дополнительную работу по преобразованию его в тип свойства, что вы будете устанавливать его с. Вместо этого вы можете позволить WPF позаботиться об открытии и преобразовании <xref:System.IO.Stream> файла ресурса непосредственно в свойство типа с помощью кода.  
  
 Ниже приведен о том, <xref:System.Windows.Controls.Page> как <xref:System.Windows.Controls.Frame> загрузить`pageFrame`непосредственно в ( ) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a>Файлы исходного узла  
 Файлы ресурсов имеют явную связь с сборками, которые они <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>распространяются вместе, как это определено в . Но иногда необходимо установить неявную либо несуществующую связь между сборкой и файлом данных приложения, например, в следующих случаях:  
  
- Файл не существует во время компиляции.  
  
- Неизвестно, какие файлы потребуются для сборки до времени выполнения.  
  
- Нужна возможность обновлять файлы без повторной компиляции сборки, связанной с ними.  
  
- Приложение использует большие файлы данных, такие как аудио и видео, и необходимо, чтобы пользователи могли их загружать только при необходимости.  
  
 Загружать эти типы файлов можно с помощью традиционных схем URI, таких как file:/// и http:// схем.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Однако схемы file:/// и http:// требуют полного доверия приложения. Если ваше приложение является браузерным приложением XAML (XBAP), которое было запущено из Интернета или интрасети, и оно запрашивает только набор разрешений, которые разрешены для приложений, запущенных из этих мест, свободные файлы могут быть загружены только из сайта происхождения (место запуска). Такие файлы известны как файлы *происхождения.*  
  
 Файлы исходного узла являются единственным вариантом для приложений с частичным доверием, хотя и не ограничиваются такими приложениями. Приложениям с полным доверием, возможно, все равно придется загружать файлы данных приложений, о которых они не знают во время построения. Хотя приложения с полным доверием могут использовать схему file:///, вероятнее всего, файлы данных приложения будут установлены в одну папку или вложенную папку со сборкой приложения. В этом случае использовать ссылки на исходный узел проще, чем использовать file:///, так как последнее требует разработки полного пути к файлу.  
  
> [!NOTE]
> Файлы происхождения сайта не кэшируются с помощью браузерного приложения XAML (XBAP) на клиентской машине, в то время как файлы содержимого. Следовательно, они загружаются только по специальному запросу. Если приложение браузера XAML (XBAP) имеет большие медиафайлы, настройка их как файлов сайта происхождения означает, что первоначальный запуск приложения происходит гораздо быстрее, а файлы загружаются только по запросу.  
  
### <a name="configuring-site-of-origin-files"></a>Настройка файлов исходного узла  
 Если файлы исходного сайта отсутствуют или неизвестны во время компиляции, необходимо использовать традиционные механизмы развертывания для `XCopy` обеспечения доступности необходимых файлов во время выполнения, включая использование либо командной строки, либо установки Microsoft Windows.  
  
 Если вы знаете во время компиляции файлы, которые вы хотели бы быть расположены на сайте происхождения, но все `None` еще хотите, чтобы избежать явной зависимости, вы можете добавить эти файлы в проект MSBuild в качестве элемента. Как и в случае с файлами `CopyToOutputDirectory` содержимого, необходимо установить атрибут MSBuild, чтобы указать, что файл сайта `Always` происхождения `PreserveNewest` скопирован в место, относительно построенной сборки, указав либо значение, либо значение.  
  
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
> В Visual Studio вы создаете файл происхождения сайта, добавляя `Build Action` `None`файл в проект и устанавливая его.  
  
 Когда проект построен, MSBuild копирует указанные файлы в папку вывода сборки.  
  
### <a name="using-site-of-origin-files"></a>Использование файлов исходного узла  
 Чтобы загрузить файл исходного сайта, <xref:System.Windows.Application.GetRemoteStream%2A> можно вызвать метод <xref:System.Windows.Application> класса, передав пакет URI, который идентифицирует нужный файл сайта происхождения. <xref:System.Windows.Application.GetRemoteStream%2A>возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл происхождения <xref:System.IO.Stream> сайта как и описывает его тип содержимого.  
  
 В качестве примера, следующий <xref:System.Windows.Application.GetRemoteStream%2A> код показывает, как использовать для загрузки <xref:System.Windows.Controls.Page> файла происхождения сайта и установить его в качестве содержания (`pageFrame` <xref:System.Windows.Controls.Frame>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 При <xref:System.Windows.Application.GetRemoteStream%2A> вызове дает <xref:System.IO.Stream>вам доступ к, вам нужно выполнить дополнительную работу по преобразованию его в тип свойства, что вы будете устанавливать его с. Вместо этого вы можете позволить WPF позаботиться об открытии и преобразовании <xref:System.IO.Stream> файла ресурса непосредственно в свойство типа с помощью кода.  
  
 Ниже приведен о том, <xref:System.Windows.Controls.Page> как <xref:System.Windows.Controls.Frame> загрузить`pageFrame`непосредственно в ( ) с помощью кода.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 В следующем примере показан эквивалент разметки предыдущего примера.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a>Повторное построение после изменения типа построения  
 После изменения типа построения файла данных приложения необходимо перестроить все приложение, чтобы обеспечить применение этих изменений. Если просто выполнить построение приложения, изменения не применяются.  
  
## <a name="see-also"></a>См. также раздел

- [URI типа "pack" в WPF](pack-uris-in-wpf.md)
