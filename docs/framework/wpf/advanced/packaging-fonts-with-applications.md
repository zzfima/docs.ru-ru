---
title: Упаковка шрифтов с приложениями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], packaging fonts with
- fonts [WPF], packaging with applications
- typography [WPF], packaging fonts with applications
- packaging fonts with applications [WPF]
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
ms.openlocfilehash: b5ad2280c832b62e043a1f65f082d5475697c38c
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545352"
---
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="9be46-102">Упаковка шрифтов с приложениями</span><span class="sxs-lookup"><span data-stu-id="9be46-102">Packaging Fonts with Applications</span></span>
<span data-ttu-id="9be46-103">В этом разделе приводятся общие сведения о том, как [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] упаковывать шрифты в приложение.</span><span class="sxs-lookup"><span data-stu-id="9be46-103">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9be46-104">Как и с большинством типов программного обеспечения, файлы шрифтов предоставляются по лицензии, а не продаются.</span><span class="sxs-lookup"><span data-stu-id="9be46-104">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="9be46-105">Лицензии, управляющие использованием шрифтов, отличаются от поставщиков поставщиками, но в целом большинство лицензий, включая те, которые [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] охватывают шрифты, поставляемые с приложениями и [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], не позволяют внедрять шрифты в приложения или иным способом. распространяться.</span><span class="sxs-lookup"><span data-stu-id="9be46-105">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] supplies with applications and [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="9be46-106">Ответственность разработчика состоит в том, чтобы гарантировать наличие требуемых лицензионных прав на любой шрифт, встраиваемый в приложение или распространяемый иными путями.</span><span class="sxs-lookup"><span data-stu-id="9be46-106">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  

<a name="introduction_to_packaging_fonts"></a>   
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="9be46-107">Общие сведения об упаковке шрифтов</span><span class="sxs-lookup"><span data-stu-id="9be46-107">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="9be46-108">Можно легко упаковывать шрифты в виде ресурсов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениях для показа текста пользовательского интерфейса и других типов содержимого на основе текста.</span><span class="sxs-lookup"><span data-stu-id="9be46-108">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="9be46-109">Шрифты могут быть отдельными от файлов сборки приложения или включенными в них.</span><span class="sxs-lookup"><span data-stu-id="9be46-109">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="9be46-110">Можно также создать библиотеку шрифтов только для ресурсов, на которую может ссылаться приложение.</span><span class="sxs-lookup"><span data-stu-id="9be46-110">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 <span data-ttu-id="9be46-111">OpenType и [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] шрифты содержат флаг типа фстипе, который указывает лицензионные права на внедрение шрифтов для шрифта.</span><span class="sxs-lookup"><span data-stu-id="9be46-111">OpenType and [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="9be46-112">Однако этот флаг типа относится только к внедренным шрифтам, хранящимся в документе; он не относится к шрифтам, внедренным в приложении.</span><span class="sxs-lookup"><span data-stu-id="9be46-112">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="9be46-113">Права на внедрение шрифта для шрифта можно получить, создав <xref:System.Windows.Media.GlyphTypeface> объект и ссылаясь на его <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="9be46-113">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="9be46-114">Дополнительные сведения о флаге Фстипе см. в разделе "метрики OS/2 и Windows" [спецификации OpenType](https://www.microsoft.com/typography/otspec/os2.htm) .</span><span class="sxs-lookup"><span data-stu-id="9be46-114">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="9be46-115">На веб-сайте [Microsoft оформления](https://docs.microsoft.com/typography/) имеются контактные данные, которые помогут найти конкретного поставщика шрифтов или найти поставщика шрифтов для пользовательской работы.</span><span class="sxs-lookup"><span data-stu-id="9be46-115">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>   
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="9be46-116">Добавление шрифтов как элементов содержимого</span><span class="sxs-lookup"><span data-stu-id="9be46-116">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="9be46-117">Вы можете добавить шрифты в приложение в виде элементов содержимого проекта, которые отделены от файлов сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-117">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="9be46-118">Это означает, что элементы содержимого не внедряются в сборку в качестве ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9be46-118">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="9be46-119">В следующем примере файла проекта показано, как определить элементы содержимого.</span><span class="sxs-lookup"><span data-stu-id="9be46-119">The following project file example shows how to define content items.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 <span data-ttu-id="9be46-120">Чтобы приложение могло использовать шрифты во время выполнения, эти шрифты должны быть доступны в каталоге развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-120">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="9be46-121">`<CopyToOutputDirectory>` Элемент в файле проекта приложения позволяет автоматически копировать шрифты в каталог развертывания приложения в процессе сборки.</span><span class="sxs-lookup"><span data-stu-id="9be46-121">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="9be46-122">В следующем примере файла проекта показано, как скопировать шрифты в каталог развертывания.</span><span class="sxs-lookup"><span data-stu-id="9be46-122">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
```xml  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 <span data-ttu-id="9be46-123">В следующем примере кода показано, как ссылаться на шрифт приложения как на элемент содержимого: ссылочный элемент содержимого должен быть в том же каталоге, что и файлы сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-123">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="9be46-124">Добавление шрифтов как элементов ресурсов</span><span class="sxs-lookup"><span data-stu-id="9be46-124">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="9be46-125">Вы можете добавить шрифты в приложение в виде элементов ресурсов проекта, которые внедряются в файлы сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-125">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="9be46-126">Использование отдельного подкаталога для ресурсов помогает упорядочить файлы проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-126">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="9be46-127">В следующем примере файла проекта показано, как определить шрифты в виде элементов ресурсов в отдельном подкаталоге.</span><span class="sxs-lookup"><span data-stu-id="9be46-127">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
>  <span data-ttu-id="9be46-128">При добавлении шрифтов в качестве ресурсов в приложение убедитесь, что вы задаете `<Resource>` элемент, а `<EmbeddedResource>` не элемент в файле проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-128">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="9be46-129">`<EmbeddedResource>` Элемент для действия сборки не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9be46-129">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="9be46-130">В следующем примере разметки показано, как ссылаться на ресурсы шрифтов приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-130">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="9be46-131">Ссылка на элементы ресурсов шрифтов из кода</span><span class="sxs-lookup"><span data-stu-id="9be46-131">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="9be46-132">Чтобы ссылаться на элементы ресурса шрифта из кода, необходимо предоставить ссылку на ресурс шрифта из двух частей: Base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], а также ссылку на расположение шрифта.</span><span class="sxs-lookup"><span data-stu-id="9be46-132">In order to reference font resource items from code, you must supply a two-part font resource reference: the base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; and the font location reference.</span></span> <span data-ttu-id="9be46-133">Эти значения используются в качестве параметров для <xref:System.Windows.Media.FontFamily.%23ctor%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="9be46-133">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="9be46-134">В следующем примере кода показано, как ссылаться на ресурсы шрифта приложения в подкаталоге проекта с именем `resources`.</span><span class="sxs-lookup"><span data-stu-id="9be46-134">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="9be46-135">База [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] может включать подкаталог приложения, в котором находится ресурс Font.</span><span class="sxs-lookup"><span data-stu-id="9be46-135">The base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="9be46-136">В этом случае в ссылке на расположение шрифта не нужно указывать каталог, но необходимо включить в начале "`./`", что означает, что ресурс шрифта находится в том же каталоге, что и базовый. [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be46-136">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span></span> <span data-ttu-id="9be46-137">В следующем примере кода показан другой способ ссылки на элемент ресурса шрифта — он эквивалентен предыдущему примеру кода.</span><span class="sxs-lookup"><span data-stu-id="9be46-137">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="9be46-138">Ссылка на шрифты из одного подкаталога приложения</span><span class="sxs-lookup"><span data-stu-id="9be46-138">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="9be46-139">Вы можете разместить файл содержимого и файл ресурсов приложения в одном пользовательском подкаталоге проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-139">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="9be46-140">В следующем примере файла проекта показаны страница содержимого и ресурсы шрифтов, определенные в одном подкаталоге.</span><span class="sxs-lookup"><span data-stu-id="9be46-140">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="9be46-141">Поскольку содержимое приложения и шрифт находятся в одном подкаталоге, ссылка на шрифт указывается относительно содержимого приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-141">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="9be46-142">В следующих примерах показывается, как ссылаться на ресурс шрифтов приложения, когда шрифт находится в том же каталоге, что и приложение.</span><span class="sxs-lookup"><span data-stu-id="9be46-142">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="9be46-143">Перечисление шрифтов в приложении</span><span class="sxs-lookup"><span data-stu-id="9be46-143">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="9be46-144">Чтобы перечислить шрифты как элементы ресурсов в приложении, используйте либо <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> <xref:System.Windows.Media.Fonts.GetTypefaces%2A> метод, либо.</span><span class="sxs-lookup"><span data-stu-id="9be46-144">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="9be46-145">В следующем примере показано, как использовать <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> метод для возврата <xref:System.Windows.Media.FontFamily> коллекции объектов из расположения шрифта приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-145">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="9be46-146">В данном случае приложение содержит подкаталог с именем resources.</span><span class="sxs-lookup"><span data-stu-id="9be46-146">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="9be46-147">В следующем примере показано, как использовать <xref:System.Windows.Media.Fonts.GetTypefaces%2A> метод для возврата <xref:System.Windows.Media.Typeface> коллекции объектов из расположения шрифта приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-147">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="9be46-148">В данном случае приложение содержит подкаталог с именем resources.</span><span class="sxs-lookup"><span data-stu-id="9be46-148">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="9be46-149">Создание библиотеки ресурсов шрифтов</span><span class="sxs-lookup"><span data-stu-id="9be46-149">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="9be46-150">Вы можете создать библиотеку только для ресурсов, которая содержит только шрифты; в проекте библиотеки этого типа никакой код не включается.</span><span class="sxs-lookup"><span data-stu-id="9be46-150">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="9be46-151">Создание библиотеки ресурсов является общим приемом для разделения ресурсов и использующего их кода приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-151">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="9be46-152">Это также позволяет включать сборку библиотеки в несколько проектов приложений.</span><span class="sxs-lookup"><span data-stu-id="9be46-152">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="9be46-153">В следующем примере файла проекта показаны основные части проекта библиотеки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9be46-153">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
```xml  
<PropertyGroup>  
  <AssemblyName>FontLibrary</AssemblyName>  
  <OutputType>library</OutputType>  
  ...  
</PropertyGroup>  
...  
<ItemGroup>  
  <Resource Include="Kooten.ttf" />  
  <Resource Include="Pesca.ttf" />  
</ItemGroup  
```  
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="9be46-154">Ссылка на шрифт в библиотеке ресурсов</span><span class="sxs-lookup"><span data-stu-id="9be46-154">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="9be46-155">Чтобы сослаться на шрифт в библиотеке ресурсов из приложения, необходимо добавить в ссылку на шрифт префикс с именем сборки библиотеки.</span><span class="sxs-lookup"><span data-stu-id="9be46-155">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="9be46-156">В данном случае сборкой ресурсов шрифтов является FontLibrary.</span><span class="sxs-lookup"><span data-stu-id="9be46-156">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="9be46-157">Для отделения имени сборки от ссылки в сборке используйте символ «;».</span><span class="sxs-lookup"><span data-stu-id="9be46-157">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="9be46-158">Добавив ключевое слово Component и ссылку на имя шрифта, вы получите полную ссылку на ресурс библиотеки шрифтов.</span><span class="sxs-lookup"><span data-stu-id="9be46-158">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="9be46-159">В следующем примере кода показано, как сослаться на шрифт в сборке библиотеки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9be46-159">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  <span data-ttu-id="9be46-160">Этот пакет SDK содержит набор образцов шрифтов OpenType, которые можно использовать с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениями.</span><span class="sxs-lookup"><span data-stu-id="9be46-160">This SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="9be46-161">Эти шрифты определяются в библиотеке ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9be46-161">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="9be46-162">Дополнительные сведения см. в разделе [Пакет образцов шрифтов OpenType](sample-opentype-font-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9be46-162">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>   
## <a name="limitations-on-font-usage"></a><span data-ttu-id="9be46-163">Ограничения в использовании шрифтов</span><span class="sxs-lookup"><span data-stu-id="9be46-163">Limitations on Font Usage</span></span>  
 <span data-ttu-id="9be46-164">В следующем списке описаны некоторые ограничения на упаковку и использование шрифтов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениях.</span><span class="sxs-lookup"><span data-stu-id="9be46-164">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
- <span data-ttu-id="9be46-165">**Биты разрешений на внедрение шрифтов:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не проверяют и не применяют принудительно никакие биты разрешений на внедрение шрифтов.</span><span class="sxs-lookup"><span data-stu-id="9be46-165">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="9be46-166">Дополнительные сведения см. в разделе [шрифты Introduction_to_Packing](#introduction_to_packaging_fonts) .</span><span class="sxs-lookup"><span data-stu-id="9be46-166">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
- <span data-ttu-id="9be46-167">**Шрифты исходного узла:** приложения не поддерживают ссылку на шрифт для HTTP или FTP [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be46-167">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span></span>  
  
- <span data-ttu-id="9be46-168">**Абсолютный URI, использующий нотацию типа "Pack** :": приложения не позволяют <xref:System.Windows.Media.FontFamily> создавать объект программно с помощью "Pack:" в составе абсолютной [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] ссылки на шрифт. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be46-168">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] reference to a font.</span></span> <span data-ttu-id="9be46-169">Например, `"pack://application:,,,/resources/#Pericles Light"` является недопустимой ссылкой на шрифт.</span><span class="sxs-lookup"><span data-stu-id="9be46-169">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
- <span data-ttu-id="9be46-170">**Автоматическое внедрение шрифтов:** Во время разработки не поддерживается поиск шрифтов приложения и автоматическое встраивание шрифтов в ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="9be46-170">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
- <span data-ttu-id="9be46-171">**Подмножества шрифтов:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не поддерживают создание подмножеств шрифтов для нефиксированных документов.</span><span class="sxs-lookup"><span data-stu-id="9be46-171">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
- <span data-ttu-id="9be46-172">Если обнаруживается неправильная ссылка, приложение прибегает к использованию доступного шрифта.</span><span class="sxs-lookup"><span data-stu-id="9be46-172">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be46-173">См. также</span><span class="sxs-lookup"><span data-stu-id="9be46-173">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [<span data-ttu-id="9be46-174">Типография Майкрософт: Ссылки, Новости и контакты</span><span class="sxs-lookup"><span data-stu-id="9be46-174">Microsoft Typography: Links, News, and Contacts</span></span>](https://docs.microsoft.com/typography/)
- [<span data-ttu-id="9be46-175">Спецификация OpenType</span><span class="sxs-lookup"><span data-stu-id="9be46-175">OpenType Specification</span></span>](https://www.microsoft.com/typography/otspec/)
- [<span data-ttu-id="9be46-176">Возможности шрифта OpenType</span><span class="sxs-lookup"><span data-stu-id="9be46-176">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="9be46-177">Пакет образцов шрифтов OpenType</span><span class="sxs-lookup"><span data-stu-id="9be46-177">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
