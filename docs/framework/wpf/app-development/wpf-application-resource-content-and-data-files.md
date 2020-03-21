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
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="50866-102">Ресурсы, Содержимое и Файлы данных WPF-приложения</span><span class="sxs-lookup"><span data-stu-id="50866-102">WPF Application Resource, Content, and Data Files</span></span>
<span data-ttu-id="50866-103">Приложения Microsoft Windows часто зависят от файлов, содержащих неисполняемые данные, такие как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]изображения, видео и аудио.</span><span class="sxs-lookup"><span data-stu-id="50866-103">Microsoft Windows applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="50866-104">Фонд презентации Windows (WPF) предлагает специальную поддержку для настройки, идентификации и использования этих типов файлов данных, которые называются файлами данных приложений.</span><span class="sxs-lookup"><span data-stu-id="50866-104">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="50866-105">Эта поддержка относится к определенному набору типов файлов данных приложения, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="50866-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="50866-106">**Файлы ресурсов**: Файлы данных, которые компилируются либо в исполняемой, либо в библиотеке WPF сборки.</span><span class="sxs-lookup"><span data-stu-id="50866-106">**Resource Files**: Data files that are compiled into either an executable or library WPF assembly.</span></span>  
  
- <span data-ttu-id="50866-107">**Файлы содержимого:** автономные файлы данных, которые имеют явную связь с исполняемой сборкой WPF.</span><span class="sxs-lookup"><span data-stu-id="50866-107">**Content Files**: Standalone data files that have an explicit association with an executable WPF assembly.</span></span>  
  
- <span data-ttu-id="50866-108">**Файлы сайта Origin:** автономные файлы данных, не имеющие связи с исполняемой сборкой WPF.</span><span class="sxs-lookup"><span data-stu-id="50866-108">**Site of Origin Files**: Standalone data files that have no association with an executable WPF assembly.</span></span>  
  
 <span data-ttu-id="50866-109">Важным отличием между этими тремя типами файлов является то, что файлы ресурсов и файлы содержимого известны во время построения. Сборка содержит информацию о них.</span><span class="sxs-lookup"><span data-stu-id="50866-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="50866-110">Однако для файлов сайта происхождения сборка может вообще не знать их или неявных знаний через ссылку на единый ресурсный идентификатор (URI); в случае последнего нет никакой гарантии того, что ссылки на сайт происхождения файл на самом деле существует.</span><span class="sxs-lookup"><span data-stu-id="50866-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="50866-111">Для ссылки на файлы данных приложений, Windows Презентация Фонд (WPF) использует пакет единообразного ресурса идентификатора (URI) Схема, которая подробно описана в [pack URIs в WPF](pack-uris-in-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="50866-111">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="50866-112">В этом разделе описывается настройка и использование файлов данных приложения.</span><span class="sxs-lookup"><span data-stu-id="50866-112">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>
## <a name="resource-files"></a><span data-ttu-id="50866-113">Файлы ресурсов</span><span class="sxs-lookup"><span data-stu-id="50866-113">Resource Files</span></span>  
 <span data-ttu-id="50866-114">Если файл данных приложения всегда должен быть доступен для приложения, то единственный способ гарантировать доступность — скомпилировать его в главную исполняемую сборку приложения или в одну из его указанных ссылками сборок.</span><span class="sxs-lookup"><span data-stu-id="50866-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="50866-115">Этот тип файла данных приложения известен как *файл ресурсов.*</span><span class="sxs-lookup"><span data-stu-id="50866-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="50866-116">Нужно использовать файлы ресурсов, если:</span><span class="sxs-lookup"><span data-stu-id="50866-116">You should use resource files when:</span></span>  
  
- <span data-ttu-id="50866-117">Не нужно обновлять содержимое файла ресурсов после его компиляции в сборку.</span><span class="sxs-lookup"><span data-stu-id="50866-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="50866-118">Необходимо упростить распространение приложения за счет уменьшения количества зависимостей между файлами.</span><span class="sxs-lookup"><span data-stu-id="50866-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="50866-119">Файл данных приложения должен быть локализован (см. Обзор глобализации [и локализации WPF).](../advanced/wpf-globalization-and-localization-overview.md)</span><span class="sxs-lookup"><span data-stu-id="50866-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50866-120">Файлы ресурсов, описанные в этом разделе, отличаются от файлов ресурсов, описанных в [XAML Resources,](../../../desktop-wpf/fundamentals/xaml-resources-define.md) и отличаются от встроенных или связанных ресурсов, описанных в [Ресурсах приложений управления (.NET).](/visualstudio/ide/managing-application-resources-dotnet)</span><span class="sxs-lookup"><span data-stu-id="50866-120">The resource files described in this section are different than the resource files described in [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="50866-121">Настройка файлов ресурсов</span><span class="sxs-lookup"><span data-stu-id="50866-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="50866-122">В WPF файл ресурсов — это файл, включенный в проект движка `Resource` сборки Майкрософт (MSBuild) в качестве элемента.</span><span class="sxs-lookup"><span data-stu-id="50866-122">In WPF, a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
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
> <span data-ttu-id="50866-123">В Visual Studio вы создаете файл ресурса, добавляя `Build Action` `Resource`файл в проект и устанавливая его для .</span><span class="sxs-lookup"><span data-stu-id="50866-123">In Visual Studio, you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="50866-124">Когда проект построен, MSBuild компилирует ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="50866-124">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="50866-125">Использование файлов ресурсов</span><span class="sxs-lookup"><span data-stu-id="50866-125">Using Resource Files</span></span>  
 <span data-ttu-id="50866-126">Для загрузки файла ресурса <xref:System.Windows.Application.GetResourceStream%2A> можно <xref:System.Windows.Application> вызвать метод класса, передав пакет URI, который идентифицирует нужный файл ресурса.</span><span class="sxs-lookup"><span data-stu-id="50866-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="50866-127"><xref:System.Windows.Application.GetResourceStream%2A>возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который разоблачает <xref:System.IO.Stream> файл ресурса как тип содержимого и описывает его.</span><span class="sxs-lookup"><span data-stu-id="50866-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="50866-128">Например, следующий код показывает, <xref:System.Windows.Application.GetResourceStream%2A> как <xref:System.Windows.Controls.Page> использовать для загрузки файла <xref:System.Windows.Controls.Frame> ресурса и установить его в качестве содержимого (`pageFrame`</span><span class="sxs-lookup"><span data-stu-id="50866-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="50866-129">При <xref:System.Windows.Application.GetResourceStream%2A> вызове дает <xref:System.IO.Stream>вам доступ к, вам нужно выполнить дополнительную работу по преобразованию его в тип свойства, что вы будете устанавливать его с.</span><span class="sxs-lookup"><span data-stu-id="50866-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="50866-130">Вместо этого вы можете позволить WPF позаботиться об открытии и преобразовании <xref:System.IO.Stream> файла ресурса непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="50866-130">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="50866-131">Ниже приведен о том, <xref:System.Windows.Controls.Page> как <xref:System.Windows.Controls.Frame> загрузить`pageFrame`непосредственно в ( ) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="50866-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="50866-132">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="50866-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="50866-133">Файлы кода приложения как файлы ресурсов</span><span class="sxs-lookup"><span data-stu-id="50866-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="50866-134">Специальный набор файлов кода приложения WPF можно ссылаться с помощью пакетных URIs, включая окна, страницы, документы потока и словари ресурсов.</span><span class="sxs-lookup"><span data-stu-id="50866-134">A special set of WPF application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="50866-135">Например, можно настроить <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> свойство пакетом URI, который ссылается на окно или страницу, которую вы хотели бы загрузить при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="50866-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="50866-136">Это можно сделать, когда файл XAML включен в `Page` проект MSBuild в качестве элемента.</span><span class="sxs-lookup"><span data-stu-id="50866-136">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
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
> <span data-ttu-id="50866-137">В Visual Studio, вы <xref:System.Windows.Window> <xref:System.Windows.Navigation.NavigationWindow>добавляете новый , <xref:System.Windows.Controls.Page>, , <xref:System.Windows.Documents.FlowDocument>, или <xref:System.Windows.ResourceDictionary> в проект, `Build Action` для файла разметки будет по `Page`умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50866-137">In Visual Studio, you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="50866-138">Когда компилируется проект `Page` с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементами, элементы преобразуются в двоичный формат и компилируются в связанную сборку.</span><span class="sxs-lookup"><span data-stu-id="50866-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="50866-139">Следовательно, эти файлы можно использовать таким же образом, как и обычные файлы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="50866-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50866-140">Если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл настроен как `Resource` элемент и не имеет файла с кодом, сырье [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] компилируется в сборку, а не в двоичную версию товара. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50866-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>
## <a name="content-files"></a><span data-ttu-id="50866-141">Файлы с содержимым</span><span class="sxs-lookup"><span data-stu-id="50866-141">Content Files</span></span>  
 <span data-ttu-id="50866-142">*Файл содержимого* распространяется как свободный файл вместе с исполняемой сборкой.</span><span class="sxs-lookup"><span data-stu-id="50866-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="50866-143">Несмотря на то, что они не компилируются в сборку, сборки компилируются с метаданными, которые устанавливают связь с каждым файлом содержимого.</span><span class="sxs-lookup"><span data-stu-id="50866-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="50866-144">Файлы содержимого необходимо использовать, если приложению требуется определенный набор файлов данных приложения, которые нужно обновлять без повторной компиляции использующей их сборки.</span><span class="sxs-lookup"><span data-stu-id="50866-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="50866-145">Настройка файлов содержимого</span><span class="sxs-lookup"><span data-stu-id="50866-145">Configuring Content Files</span></span>  
 <span data-ttu-id="50866-146">Чтобы добавить файл содержимого в проект, файл данных приложения должен быть включен в качестве элемента. `Content`</span><span class="sxs-lookup"><span data-stu-id="50866-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="50866-147">Кроме того, поскольку файл содержимого не компилируется непосредственно `CopyToOutputDirectory` в сборку, необходимо установить элемент метаданных MSBuild, чтобы указать, что файл содержимого копируется в место, относительно построенной сборки.</span><span class="sxs-lookup"><span data-stu-id="50866-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="50866-148">Если при каждом построении проекта ресурс копируется в папку вывода `CopyToOutputDirectory` сборки, вы `Always` установите элемент метаданных со значением.</span><span class="sxs-lookup"><span data-stu-id="50866-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="50866-149">В противном случае можно гарантировать, что только новейшая версия ресурса `PreserveNewest` будет скопирована в папку вывода сборки с помощью значения.</span><span class="sxs-lookup"><span data-stu-id="50866-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="50866-150">Ниже показан файл, настроенный как файл содержимого, который копируется в папку выходных данных построения только при добавлении новой версии ресурса в проект.</span><span class="sxs-lookup"><span data-stu-id="50866-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
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
> <span data-ttu-id="50866-151">В Visual Studio, вы создаете файл содержимого, добавляя файл в проект и `Always`установив `Copy if newer` его `PreserveNewest` `Build Action` `Content` `Copy to Output Directory` `Copy always` на , и установить его (так же, как ) и (так же, как ).</span><span class="sxs-lookup"><span data-stu-id="50866-151">In Visual Studio, you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="50866-152">Когда проект построен, <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> атрибут компилируется в метаданные сборки для каждого файла содержимого.</span><span class="sxs-lookup"><span data-stu-id="50866-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="50866-153">Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> значения подразумевает путь к файлу содержимого относительно его положения в проекте.</span><span class="sxs-lookup"><span data-stu-id="50866-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="50866-154">Например, если файл содержимого находится в подфайле проекта, дополнительная информация о пути будет включена в <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> значение.</span><span class="sxs-lookup"><span data-stu-id="50866-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="50866-155">Значение <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> также значение пути к файлу содержимого в папке вывода сборки.</span><span class="sxs-lookup"><span data-stu-id="50866-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="50866-156">Использование файлов содержимого</span><span class="sxs-lookup"><span data-stu-id="50866-156">Using Content Files</span></span>  
 <span data-ttu-id="50866-157">Чтобы загрузить файл содержимого, <xref:System.Windows.Application.GetContentStream%2A> можно вызвать метод <xref:System.Windows.Application> класса, передав пакет URI, который идентифицирует нужный файл содержимого.</span><span class="sxs-lookup"><span data-stu-id="50866-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="50866-158"><xref:System.Windows.Application.GetContentStream%2A>возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл содержимого как <xref:System.IO.Stream> и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="50866-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="50866-159">В качестве примера, следующий <xref:System.Windows.Application.GetContentStream%2A> код показывает, как использовать для загрузки файла <xref:System.Windows.Controls.Page> содержимого и установить его в качестве содержания <xref:System.Windows.Controls.Frame> (`pageFrame`</span><span class="sxs-lookup"><span data-stu-id="50866-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="50866-160">При <xref:System.Windows.Application.GetContentStream%2A> вызове дает <xref:System.IO.Stream>вам доступ к, вам нужно выполнить дополнительную работу по преобразованию его в тип свойства, что вы будете устанавливать его с.</span><span class="sxs-lookup"><span data-stu-id="50866-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="50866-161">Вместо этого вы можете позволить WPF позаботиться об открытии и преобразовании <xref:System.IO.Stream> файла ресурса непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="50866-161">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="50866-162">Ниже приведен о том, <xref:System.Windows.Controls.Page> как <xref:System.Windows.Controls.Frame> загрузить`pageFrame`непосредственно в ( ) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="50866-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="50866-163">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="50866-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a><span data-ttu-id="50866-164">Файлы исходного узла</span><span class="sxs-lookup"><span data-stu-id="50866-164">Site of Origin Files</span></span>  
 <span data-ttu-id="50866-165">Файлы ресурсов имеют явную связь с сборками, которые они <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>распространяются вместе, как это определено в .</span><span class="sxs-lookup"><span data-stu-id="50866-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="50866-166">Но иногда необходимо установить неявную либо несуществующую связь между сборкой и файлом данных приложения, например, в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="50866-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="50866-167">Файл не существует во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="50866-167">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="50866-168">Неизвестно, какие файлы потребуются для сборки до времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="50866-168">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="50866-169">Нужна возможность обновлять файлы без повторной компиляции сборки, связанной с ними.</span><span class="sxs-lookup"><span data-stu-id="50866-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="50866-170">Приложение использует большие файлы данных, такие как аудио и видео, и необходимо, чтобы пользователи могли их загружать только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="50866-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="50866-171">Загружать эти типы файлов можно с помощью традиционных схем URI, таких как file:/// и http:// схем.</span><span class="sxs-lookup"><span data-stu-id="50866-171">It is possible to load these types of files by using traditional URI schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="50866-172">Однако схемы file:/// и http:// требуют полного доверия приложения.</span><span class="sxs-lookup"><span data-stu-id="50866-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="50866-173">Если ваше приложение является браузерным приложением XAML (XBAP), которое было запущено из Интернета или интрасети, и оно запрашивает только набор разрешений, которые разрешены для приложений, запущенных из этих мест, свободные файлы могут быть загружены только из сайта происхождения (место запуска).</span><span class="sxs-lookup"><span data-stu-id="50866-173">If your application is a XAML browser application (XBAP) that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="50866-174">Такие файлы известны как файлы *происхождения.*</span><span class="sxs-lookup"><span data-stu-id="50866-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="50866-175">Файлы исходного узла являются единственным вариантом для приложений с частичным доверием, хотя и не ограничиваются такими приложениями.</span><span class="sxs-lookup"><span data-stu-id="50866-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="50866-176">Приложениям с полным доверием, возможно, все равно придется загружать файлы данных приложений, о которых они не знают во время построения. Хотя приложения с полным доверием могут использовать схему file:///, вероятнее всего, файлы данных приложения будут установлены в одну папку или вложенную папку со сборкой приложения.</span><span class="sxs-lookup"><span data-stu-id="50866-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="50866-177">В этом случае использовать ссылки на исходный узел проще, чем использовать file:///, так как последнее требует разработки полного пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="50866-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50866-178">Файлы происхождения сайта не кэшируются с помощью браузерного приложения XAML (XBAP) на клиентской машине, в то время как файлы содержимого.</span><span class="sxs-lookup"><span data-stu-id="50866-178">Site of origin files are not cached with an XAML browser application (XBAP) on a client machine, while content files are.</span></span> <span data-ttu-id="50866-179">Следовательно, они загружаются только по специальному запросу.</span><span class="sxs-lookup"><span data-stu-id="50866-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="50866-180">Если приложение браузера XAML (XBAP) имеет большие медиафайлы, настройка их как файлов сайта происхождения означает, что первоначальный запуск приложения происходит гораздо быстрее, а файлы загружаются только по запросу.</span><span class="sxs-lookup"><span data-stu-id="50866-180">If an XAML browser application (XBAP) application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="50866-181">Настройка файлов исходного узла</span><span class="sxs-lookup"><span data-stu-id="50866-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="50866-182">Если файлы исходного сайта отсутствуют или неизвестны во время компиляции, необходимо использовать традиционные механизмы развертывания для `XCopy` обеспечения доступности необходимых файлов во время выполнения, включая использование либо командной строки, либо установки Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="50866-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the Microsoft Windows Installer.</span></span>  
  
 <span data-ttu-id="50866-183">Если вы знаете во время компиляции файлы, которые вы хотели бы быть расположены на сайте происхождения, но все `None` еще хотите, чтобы избежать явной зависимости, вы можете добавить эти файлы в проект MSBuild в качестве элемента.</span><span class="sxs-lookup"><span data-stu-id="50866-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="50866-184">Как и в случае с файлами `CopyToOutputDirectory` содержимого, необходимо установить атрибут MSBuild, чтобы указать, что файл сайта `Always` происхождения `PreserveNewest` скопирован в место, относительно построенной сборки, указав либо значение, либо значение.</span><span class="sxs-lookup"><span data-stu-id="50866-184">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
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
> <span data-ttu-id="50866-185">В Visual Studio вы создаете файл происхождения сайта, добавляя `Build Action` `None`файл в проект и устанавливая его.</span><span class="sxs-lookup"><span data-stu-id="50866-185">In Visual Studio, you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="50866-186">Когда проект построен, MSBuild копирует указанные файлы в папку вывода сборки.</span><span class="sxs-lookup"><span data-stu-id="50866-186">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="50866-187">Использование файлов исходного узла</span><span class="sxs-lookup"><span data-stu-id="50866-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="50866-188">Чтобы загрузить файл исходного сайта, <xref:System.Windows.Application.GetRemoteStream%2A> можно вызвать метод <xref:System.Windows.Application> класса, передав пакет URI, который идентифицирует нужный файл сайта происхождения.</span><span class="sxs-lookup"><span data-stu-id="50866-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="50866-189"><xref:System.Windows.Application.GetRemoteStream%2A>возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл происхождения <xref:System.IO.Stream> сайта как и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="50866-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="50866-190">В качестве примера, следующий <xref:System.Windows.Application.GetRemoteStream%2A> код показывает, как использовать для загрузки <xref:System.Windows.Controls.Page> файла происхождения сайта и установить его в качестве содержания (`pageFrame` <xref:System.Windows.Controls.Frame></span><span class="sxs-lookup"><span data-stu-id="50866-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="50866-191">При <xref:System.Windows.Application.GetRemoteStream%2A> вызове дает <xref:System.IO.Stream>вам доступ к, вам нужно выполнить дополнительную работу по преобразованию его в тип свойства, что вы будете устанавливать его с.</span><span class="sxs-lookup"><span data-stu-id="50866-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="50866-192">Вместо этого вы можете позволить WPF позаботиться об открытии и преобразовании <xref:System.IO.Stream> файла ресурса непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="50866-192">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="50866-193">Ниже приведен о том, <xref:System.Windows.Controls.Page> как <xref:System.Windows.Controls.Frame> загрузить`pageFrame`непосредственно в ( ) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="50866-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="50866-194">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="50866-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="50866-195">Повторное построение после изменения типа построения</span><span class="sxs-lookup"><span data-stu-id="50866-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="50866-196">После изменения типа построения файла данных приложения необходимо перестроить все приложение, чтобы обеспечить применение этих изменений.</span><span class="sxs-lookup"><span data-stu-id="50866-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="50866-197">Если просто выполнить построение приложения, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="50866-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50866-198">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="50866-198">See also</span></span>

- [<span data-ttu-id="50866-199">URI типа "pack" в WPF</span><span class="sxs-lookup"><span data-stu-id="50866-199">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
