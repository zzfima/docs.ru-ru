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
ms.openlocfilehash: e50f542086aadc2f61412fe409d7df0f49422718
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920364"
---
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="18401-102">Ресурсы, Содержимое и Файлы данных WPF-приложения</span><span class="sxs-lookup"><span data-stu-id="18401-102">WPF Application Resource, Content, and Data Files</span></span>
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] <span data-ttu-id="18401-103">приложения часто зависят от файлов, которые содержат неисполняемые данные, такие как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], изображения, видео и звук.</span><span class="sxs-lookup"><span data-stu-id="18401-103">applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="18401-104">Windows Presentation Foundation (WPF) предлагает специальную поддержку для настройки, идентификации и использования этих типов файлов данных, которые называются файлами данных приложения.</span><span class="sxs-lookup"><span data-stu-id="18401-104">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="18401-105">Эта поддержка относится к определенному набору типов файлов данных приложения, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="18401-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="18401-106">**Файлы ресурсов**. файлы данных, компилируемые в исполняемый файл или библиотеку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборки.</span><span class="sxs-lookup"><span data-stu-id="18401-106">**Resource Files**: Data files that are compiled into either an executable or library [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
- <span data-ttu-id="18401-107">**Файлы содержимого**: автономные файлы данных с явной связью с исполняемым [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборкой.</span><span class="sxs-lookup"><span data-stu-id="18401-107">**Content Files**: Standalone data files that have an explicit association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
- <span data-ttu-id="18401-108">**Файлы исходного узла**: автономные файлы данных, не имеющие связи с исполняемым [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сборкой.</span><span class="sxs-lookup"><span data-stu-id="18401-108">**Site of Origin Files**: Standalone data files that have no association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
 <span data-ttu-id="18401-109">Важным отличием между этими тремя типами файлов является то, что файлы ресурсов и файлы содержимого известны во время построения. Сборка содержит информацию о них.</span><span class="sxs-lookup"><span data-stu-id="18401-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="18401-110">Однако для файлов исходного узла сборка может вообще не иметь сведений о них или неявного набора знаний через универсальный код ресурса (URI) типа pack. в последнем случае нет никакой гарантии, что файл исходного узла, на который указывает ссылка, фактически существует.</span><span class="sxs-lookup"><span data-stu-id="18401-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="18401-111">Для ссылки на файлы данных приложения Windows Presentation Foundation (WPF) использует схему универсального идентификатора ресурса (URI) типа Pack, которая подробно описана в разделе URI типа " [Pack" в WPF](pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="18401-111">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="18401-112">В этом разделе описывается настройка и использование файлов данных приложения.</span><span class="sxs-lookup"><span data-stu-id="18401-112">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a><span data-ttu-id="18401-113">Файлы ресурсов</span><span class="sxs-lookup"><span data-stu-id="18401-113">Resource Files</span></span>  
 <span data-ttu-id="18401-114">Если файл данных приложения всегда должен быть доступен для приложения, то единственный способ гарантировать доступность — скомпилировать его в главную исполняемую сборку приложения или в одну из его указанных ссылками сборок.</span><span class="sxs-lookup"><span data-stu-id="18401-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="18401-115">Этот тип файла данных приложения называется *файлом ресурсов*.</span><span class="sxs-lookup"><span data-stu-id="18401-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="18401-116">Нужно использовать файлы ресурсов, если:</span><span class="sxs-lookup"><span data-stu-id="18401-116">You should use resource files when:</span></span>  
  
- <span data-ttu-id="18401-117">Не нужно обновлять содержимое файла ресурсов после его компиляции в сборку.</span><span class="sxs-lookup"><span data-stu-id="18401-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="18401-118">Необходимо упростить распространение приложения за счет уменьшения количества зависимостей между файлами.</span><span class="sxs-lookup"><span data-stu-id="18401-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="18401-119">Файл данных приложения должен быть локализуемой (см. [Общие сведения о глобализации и локализации WPF](../advanced/wpf-globalization-and-localization-overview.md)).</span><span class="sxs-lookup"><span data-stu-id="18401-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18401-120">Файлы ресурсов, описанные в этом разделе, отличаются от файлов ресурсов, описанных в [ресурсах XAML](../advanced/xaml-resources.md) , и отличаются от внедренных или связанных ресурсов, описанных в статье [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="18401-120">The resource files described in this section are different than the resource files described in [XAML Resources](../advanced/xaml-resources.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="18401-121">Настройка файлов ресурсов</span><span class="sxs-lookup"><span data-stu-id="18401-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="18401-122">В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]файл ресурсов — это файл, который включается в проект Microsoft Build Engine (MSBuild) как элемент `Resource`.</span><span class="sxs-lookup"><span data-stu-id="18401-122">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
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
> <span data-ttu-id="18401-123">В Visual Studio создайте файл ресурсов, добавив файл в проект и задав для его `Build Action` значение `Resource`.</span><span class="sxs-lookup"><span data-stu-id="18401-123">In Visual Studio, you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="18401-124">При построении проекта MSBuild компилирует ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="18401-124">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="18401-125">Использование файлов ресурсов</span><span class="sxs-lookup"><span data-stu-id="18401-125">Using Resource Files</span></span>  
 <span data-ttu-id="18401-126">Чтобы загрузить файл ресурсов, можно вызвать метод <xref:System.Windows.Application.GetResourceStream%2A> класса <xref:System.Windows.Application>, передав URI типа Pack, который идентифицирует нужный файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="18401-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="18401-127"><xref:System.Windows.Application.GetResourceStream%2A> возвращает объект <xref:System.Windows.Resources.StreamResourceInfo>, который предоставляет файл ресурсов как <xref:System.IO.Stream> и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="18401-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="18401-128">В следующем примере кода показано, как использовать <xref:System.Windows.Application.GetResourceStream%2A> для загрузки <xref:System.Windows.Controls.Page> файла ресурсов и его установки в качестве содержимого <xref:System.Windows.Controls.Frame> (`pageFrame`):</span><span class="sxs-lookup"><span data-stu-id="18401-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="18401-129">При вызове <xref:System.Windows.Application.GetResourceStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить дополнительную работу по преобразованию в тип свойства, которое будет задано.</span><span class="sxs-lookup"><span data-stu-id="18401-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="18401-130">Вместо этого можно разрешить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream>, загрузив файл ресурсов непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="18401-130">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="18401-131">В следующем примере показано, как загрузить <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> (`pageFrame`) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="18401-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="18401-132">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="18401-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="18401-133">Файлы кода приложения как файлы ресурсов</span><span class="sxs-lookup"><span data-stu-id="18401-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="18401-134">На Специальный набор [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] файлов кода приложения можно ссылаться с помощью URI типа "Pack", включая окна, страницы, документы нефиксированного формата и словари ресурсов.</span><span class="sxs-lookup"><span data-stu-id="18401-134">A special set of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="18401-135">Например, можно задать свойство <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> с URI типа Pack, который ссылается на окно или страницу, которые вы хотите загрузить при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="18401-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="18401-136">Это можно сделать, когда XAML-файл включается в проект MSBuild как элемент `Page`.</span><span class="sxs-lookup"><span data-stu-id="18401-136">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
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
> <span data-ttu-id="18401-137">В Visual Studio вы добавляете в проект новый <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>или <xref:System.Windows.ResourceDictionary>, `Build Action` для файла разметки по умолчанию будет `Page`.</span><span class="sxs-lookup"><span data-stu-id="18401-137">In Visual Studio, you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="18401-138">При компиляции проекта с `Page` элементами [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементы преобразуются в двоичный формат и компилируются в связанную сборку.</span><span class="sxs-lookup"><span data-stu-id="18401-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="18401-139">Следовательно, эти файлы можно использовать таким же образом, как и обычные файлы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="18401-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18401-140">Если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл настроен как элемент `Resource` и не имеет файла кода программной части, то необработанный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] компилируется в сборку, а не в двоичную версию необработанного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18401-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a><span data-ttu-id="18401-141">Файлы с содержимым</span><span class="sxs-lookup"><span data-stu-id="18401-141">Content Files</span></span>  
 <span data-ttu-id="18401-142">*Файл содержимого* распространяется в виде свободного файла вместе с исполняемой сборкой.</span><span class="sxs-lookup"><span data-stu-id="18401-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="18401-143">Несмотря на то, что они не компилируются в сборку, сборки компилируются с метаданными, которые устанавливают связь с каждым файлом содержимого.</span><span class="sxs-lookup"><span data-stu-id="18401-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="18401-144">Файлы содержимого необходимо использовать, если приложению требуется определенный набор файлов данных приложения, которые нужно обновлять без повторной компиляции использующей их сборки.</span><span class="sxs-lookup"><span data-stu-id="18401-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="18401-145">Настройка файлов содержимого</span><span class="sxs-lookup"><span data-stu-id="18401-145">Configuring Content Files</span></span>  
 <span data-ttu-id="18401-146">Чтобы добавить файл содержимого в проект, файл данных приложения должен быть добавлен в качестве элемента `Content`.</span><span class="sxs-lookup"><span data-stu-id="18401-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="18401-147">Более того, поскольку файл содержимого не компилируется непосредственно в сборку, необходимо задать элемент метаданных `CopyToOutputDirectory` MSBuild, чтобы указать, что файл содержимого копируется в расположение, относящееся к построенной сборке.</span><span class="sxs-lookup"><span data-stu-id="18401-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="18401-148">Если требуется, чтобы ресурс копировался в выходную папку сборки при каждом построении проекта, необходимо задать для элемента метаданных `CopyToOutputDirectory` значение `Always`.</span><span class="sxs-lookup"><span data-stu-id="18401-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="18401-149">В противном случае можно убедиться, что только последняя версия ресурса копируется в выходную папку сборки с использованием значения `PreserveNewest`.</span><span class="sxs-lookup"><span data-stu-id="18401-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="18401-150">Ниже показан файл, настроенный как файл содержимого, который копируется в папку выходных данных построения только при добавлении новой версии ресурса в проект.</span><span class="sxs-lookup"><span data-stu-id="18401-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
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
> <span data-ttu-id="18401-151">В Visual Studio вы создаете файл содержимого, добавляя файл в проект и настроив его `Build Action` на `Content`и настраиваете его `Copy to Output Directory` на `Copy always` (то же, что `Always`) и `Copy if newer` (то же, что `PreserveNewest`).</span><span class="sxs-lookup"><span data-stu-id="18401-151">In Visual Studio, you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="18401-152">При построении проекта <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> атрибут компилируется в метаданные сборки для каждого файла содержимого.</span><span class="sxs-lookup"><span data-stu-id="18401-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="18401-153">Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> подразумевает путь к файлу содержимого относительно его положения в проекте.</span><span class="sxs-lookup"><span data-stu-id="18401-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="18401-154">Например, если файл содержимого находится во вложенной папке проекта, то дополнительные сведения о пути будут включены в <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> значение.</span><span class="sxs-lookup"><span data-stu-id="18401-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="18401-155">Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> — это также значение пути к файлу содержимого в выходной папке построения.</span><span class="sxs-lookup"><span data-stu-id="18401-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="18401-156">Использование файлов содержимого</span><span class="sxs-lookup"><span data-stu-id="18401-156">Using Content Files</span></span>  
 <span data-ttu-id="18401-157">Чтобы загрузить файл содержимого, можно вызвать метод <xref:System.Windows.Application.GetContentStream%2A> класса <xref:System.Windows.Application>, передав URI типа Pack, который идентифицирует нужный файл содержимого.</span><span class="sxs-lookup"><span data-stu-id="18401-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="18401-158"><xref:System.Windows.Application.GetContentStream%2A> возвращает объект <xref:System.Windows.Resources.StreamResourceInfo>, который предоставляет файл содержимого как <xref:System.IO.Stream> и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="18401-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="18401-159">В следующем примере кода показано, как использовать <xref:System.Windows.Application.GetContentStream%2A> для загрузки <xref:System.Windows.Controls.Page>ного файла содержимого и задания его в качестве содержимого <xref:System.Windows.Controls.Frame> (`pageFrame`).</span><span class="sxs-lookup"><span data-stu-id="18401-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="18401-160">При вызове <xref:System.Windows.Application.GetContentStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить дополнительную работу по преобразованию в тип свойства, которое будет задано.</span><span class="sxs-lookup"><span data-stu-id="18401-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="18401-161">Вместо этого можно разрешить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream>, загрузив файл ресурсов непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="18401-161">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="18401-162">В следующем примере показано, как загрузить <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> (`pageFrame`) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="18401-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="18401-163">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="18401-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a><span data-ttu-id="18401-164">Файлы исходного узла</span><span class="sxs-lookup"><span data-stu-id="18401-164">Site of Origin Files</span></span>  
 <span data-ttu-id="18401-165">Файлы ресурсов имеют явную связь со сборками, которые они распределяют вместе, как определено <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span><span class="sxs-lookup"><span data-stu-id="18401-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="18401-166">Но иногда необходимо установить неявную либо несуществующую связь между сборкой и файлом данных приложения, например, в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="18401-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="18401-167">Файл не существует во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="18401-167">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="18401-168">Неизвестно, какие файлы потребуются для сборки до времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="18401-168">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="18401-169">Нужна возможность обновлять файлы без повторной компиляции сборки, связанной с ними.</span><span class="sxs-lookup"><span data-stu-id="18401-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="18401-170">Приложение использует большие файлы данных, такие как аудио и видео, и необходимо, чтобы пользователи могли их загружать только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="18401-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="18401-171">Эти типы файлов можно загрузить с помощью традиционных схем URI, таких как схемы file:///и http://.</span><span class="sxs-lookup"><span data-stu-id="18401-171">It is possible to load these types of files by using traditional URI schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="18401-172">Однако схемы file:/// и http:// требуют полного доверия приложения.</span><span class="sxs-lookup"><span data-stu-id="18401-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="18401-173">Если приложение является [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], которое было запущено из Интернета или интрасети, и запрашивает только набор разрешений, разрешенных для приложений, запускаемых из этих расположений, свободные файлы могут загружаться только с исходного узла приложения ( Расположение запуска).</span><span class="sxs-lookup"><span data-stu-id="18401-173">If your application is a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="18401-174">Такие файлы называются файлами *исходного узла* .</span><span class="sxs-lookup"><span data-stu-id="18401-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="18401-175">Файлы исходного узла являются единственным вариантом для приложений с частичным доверием, хотя и не ограничиваются такими приложениями.</span><span class="sxs-lookup"><span data-stu-id="18401-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="18401-176">Приложениям с полным доверием, возможно, все равно придется загружать файлы данных приложений, о которых они не знают во время построения. Хотя приложения с полным доверием могут использовать схему file:///, вероятнее всего, файлы данных приложения будут установлены в одну папку или вложенную папку со сборкой приложения.</span><span class="sxs-lookup"><span data-stu-id="18401-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="18401-177">В этом случае использовать ссылки на исходный узел проще, чем использовать file:///, так как последнее требует разработки полного пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="18401-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18401-178">Файлы исходного узла не кэшируются с [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] на клиентском компьютере, а файлы содержимого —.</span><span class="sxs-lookup"><span data-stu-id="18401-178">Site of origin files are not cached with an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] on a client machine, while content files are.</span></span> <span data-ttu-id="18401-179">Следовательно, они загружаются только по специальному запросу.</span><span class="sxs-lookup"><span data-stu-id="18401-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="18401-180">Если приложение [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] имеет большие файлы мультимедиа, то их настройка в качестве файлов исходного узла означает, что начальный запуск приложения выполняется гораздо быстрее, а файлы загружаются по требованию.</span><span class="sxs-lookup"><span data-stu-id="18401-180">If an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="18401-181">Настройка файлов исходного узла</span><span class="sxs-lookup"><span data-stu-id="18401-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="18401-182">Если файлы исходного сайта не существуют или неизвестны во время компиляции, необходимо использовать традиционные механизмы развертывания для обеспечения доступности необходимых файлов во время выполнения, в том числе с помощью `XCopy` программы командной строки или [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18401-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].</span></span>  
  
 <span data-ttu-id="18401-183">Если во время компиляции вы узнаете, какие файлы необходимо найти на исходном узле, но все равно хотите избежать явной зависимости, можно добавить эти файлы в проект MSBuild как `None` элемент.</span><span class="sxs-lookup"><span data-stu-id="18401-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="18401-184">Как и в случае с файлами содержимого, необходимо задать атрибут `CopyToOutputDirectory` MSBuild, чтобы указать, что файл исходного сайта копируется в расположение относительно сборки, указав либо значение `Always`, либо значение `PreserveNewest`.</span><span class="sxs-lookup"><span data-stu-id="18401-184">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
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
> <span data-ttu-id="18401-185">В Visual Studio создайте файл исходного узла, добавив файл в проект и задав для его `Build Action` значение `None`.</span><span class="sxs-lookup"><span data-stu-id="18401-185">In Visual Studio, you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="18401-186">При построении проекта MSBuild копирует указанные файлы в выходную папку сборки.</span><span class="sxs-lookup"><span data-stu-id="18401-186">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="18401-187">Использование файлов исходного узла</span><span class="sxs-lookup"><span data-stu-id="18401-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="18401-188">Чтобы загрузить файл исходного узла, можно вызвать метод <xref:System.Windows.Application.GetRemoteStream%2A> класса <xref:System.Windows.Application>, передав URI типа Pack, который идентифицирует нужный файл исходного узла.</span><span class="sxs-lookup"><span data-stu-id="18401-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="18401-189"><xref:System.Windows.Application.GetRemoteStream%2A> возвращает объект <xref:System.Windows.Resources.StreamResourceInfo>, который предоставляет файл исходного узла в качестве <xref:System.IO.Stream> и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="18401-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="18401-190">В следующем примере кода показано, как использовать <xref:System.Windows.Application.GetRemoteStream%2A> для загрузки <xref:System.Windows.Controls.Page> файла исходного узла и его установки в качестве содержимого <xref:System.Windows.Controls.Frame> (`pageFrame`).</span><span class="sxs-lookup"><span data-stu-id="18401-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="18401-191">При вызове <xref:System.Windows.Application.GetRemoteStream%2A> предоставляет доступ к <xref:System.IO.Stream>, необходимо выполнить дополнительную работу по преобразованию в тип свойства, которое будет задано.</span><span class="sxs-lookup"><span data-stu-id="18401-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="18401-192">Вместо этого можно разрешить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позаботиться об открытии и преобразовании <xref:System.IO.Stream>, загрузив файл ресурсов непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="18401-192">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="18401-193">В следующем примере показано, как загрузить <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> (`pageFrame`) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="18401-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="18401-194">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="18401-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="18401-195">Повторное построение после изменения типа построения</span><span class="sxs-lookup"><span data-stu-id="18401-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="18401-196">После изменения типа построения файла данных приложения необходимо перестроить все приложение, чтобы обеспечить применение этих изменений.</span><span class="sxs-lookup"><span data-stu-id="18401-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="18401-197">Если просто выполнить построение приложения, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="18401-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18401-198">См. также</span><span class="sxs-lookup"><span data-stu-id="18401-198">See also</span></span>

- [<span data-ttu-id="18401-199">URI типа "pack" в WPF</span><span class="sxs-lookup"><span data-stu-id="18401-199">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
