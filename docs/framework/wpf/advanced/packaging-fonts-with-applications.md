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
ms.openlocfilehash: cef2ae26ec4fccd25ca193ba7d441969f36b25a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187093"
---
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="f3cd7-102">Упаковка шрифтов с приложениями</span><span class="sxs-lookup"><span data-stu-id="f3cd7-102">Packaging Fonts with Applications</span></span>
<span data-ttu-id="f3cd7-103">В этой теме содержится обзор того, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] как упаковать шрифты с вашим приложением.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-103">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3cd7-104">Как и с большинством типов программного обеспечения, файлы шрифтов предоставляются по лицензии, а не продаются.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-104">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="f3cd7-105">Лицензии, регулирующие использование шрифтов, варьируются от поставщика к поставщику, но в целом большинство лицензий, включая лицензии, охватывающие шрифты, которые поставляются Microsoft с приложениями и Windows, не позволяют встраиваться в приложения или иным образом перераспределяться.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-105">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts Microsoft supplies with applications and Windows, do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="f3cd7-106">Ответственность разработчика состоит в том, чтобы гарантировать наличие требуемых лицензионных прав на любой шрифт, встраиваемый в приложение или распространяемый иными путями.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-106">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="f3cd7-107">Общие сведения об упаковке шрифтов</span><span class="sxs-lookup"><span data-stu-id="f3cd7-107">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="f3cd7-108">Вы можете легко упаковать шрифты в качестве ресурсов в приложениях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для отображения текста пользовательского интерфейса и других типов содержимого на основе текста.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-108">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="f3cd7-109">Шрифты могут быть отдельными от файлов сборки приложения или включенными в них.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-109">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="f3cd7-110">Можно также создать библиотеку шрифтов только для ресурсов, на которую может ссылаться приложение.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-110">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 <span data-ttu-id="f3cd7-111">Шрифты OpenType и TrueType® содержат флаг типа, fsType, который указывает на шрифт, встраивающий лицензионные права на шрифт.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-111">OpenType and TrueType® fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="f3cd7-112">Однако этот флаг типа относится только к внедренным шрифтам, хранящимся в документе; он не относится к шрифтам, внедренным в приложении.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-112">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="f3cd7-113">Вы можете получить права на встраивание шрифта <xref:System.Windows.Media.GlyphTypeface> для шрифта, <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> создав объект и ссылаясь на его свойство.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-113">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="f3cd7-114">Для получения дополнительной информации о флаге fsType обратитесь в раздел "OS/2 и Windows Metrics" [спецификации OpenType.](https://www.microsoft.com/typography/otspec/os2.htm)</span><span class="sxs-lookup"><span data-stu-id="f3cd7-114">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="f3cd7-115">Веб-узел [Microsoft Typography](https://docs.microsoft.com/typography/) содержит контактную информацию, которая может помочь вам найти конкретного поставщика шрифтов или найти поставщика шрифтов для работы на заказ.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-115">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="f3cd7-116">Добавление шрифтов как элементов содержимого</span><span class="sxs-lookup"><span data-stu-id="f3cd7-116">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="f3cd7-117">Вы можете добавить шрифты в приложение в виде элементов содержимого проекта, которые отделены от файлов сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-117">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="f3cd7-118">Это означает, что элементы содержимого не внедряются в сборку в качестве ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-118">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="f3cd7-119">В следующем примере файла проекта показано, как определить элементы содержимого.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-119">The following project file example shows how to define content items.</span></span>  
  
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
  
 <span data-ttu-id="f3cd7-120">Чтобы приложение могло использовать шрифты во время выполнения, эти шрифты должны быть доступны в каталоге развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-120">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="f3cd7-121">Элемент `<CopyToOutputDirectory>` в файле проекта приложения позволяет автоматически копировать шрифты в каталог развертывания приложения во время процесса сборки.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-121">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="f3cd7-122">В следующем примере файла проекта показано, как скопировать шрифты в каталог развертывания.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-122">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
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
  
 <span data-ttu-id="f3cd7-123">В следующем примере кода показано, как ссылаться на шрифт приложения как на элемент содержимого: ссылочный элемент содержимого должен быть в том же каталоге, что и файлы сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-123">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="f3cd7-124">Добавление шрифтов как элементов ресурсов</span><span class="sxs-lookup"><span data-stu-id="f3cd7-124">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="f3cd7-125">Вы можете добавить шрифты в приложение в виде элементов ресурсов проекта, которые внедряются в файлы сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-125">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="f3cd7-126">Использование отдельного подкаталога для ресурсов помогает упорядочить файлы проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-126">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="f3cd7-127">В следующем примере файла проекта показано, как определить шрифты в виде элементов ресурсов в отдельном подкаталоге.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-127">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
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
> <span data-ttu-id="f3cd7-128">При добавлении шрифтов в качестве ресурсов в `<Resource>` приложение убедитесь, `<EmbeddedResource>` что вы устанавливаете элемент, а не элемент в файле проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-128">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="f3cd7-129">Элемент `<EmbeddedResource>` для действия сборки не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-129">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="f3cd7-130">В следующем примере разметки показано, как ссылаться на ресурсы шрифтов приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-130">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="f3cd7-131">Ссылка на элементы ресурсов шрифтов из кода</span><span class="sxs-lookup"><span data-stu-id="f3cd7-131">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="f3cd7-132">Для того, чтобы ссылаться на элементы ресурса шрифта из кода, необходимо предоставить ссылку на ресурсы из двух частей: базовый единый идентификатор ресурсов (URI); и ссылка на местоположение шрифта.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-132">In order to reference font resource items from code, you must supply a two-part font resource reference: the base uniform resource identifier (URI); and the font location reference.</span></span> <span data-ttu-id="f3cd7-133">Эти значения используются в качестве <xref:System.Windows.Media.FontFamily.%23ctor%2A> параметров для метода.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-133">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="f3cd7-134">Следующий пример кода показывает, как ссылаться на ресурсы шрифта приложения в подсобном `resources`запросе проекта.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-134">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="f3cd7-135">Базовый единый идентификатор ресурсов (URI) может включать в себя субдиректорию приложения, в которой находится ресурс шрифта.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-135">The base uniform resource identifier (URI) can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="f3cd7-136">В этом случае ссылка на местоположение шрифта не должна указывать каталог,`./`но должна будет включать ведущий ", который указывает, что ресурс шрифта находится в том же каталоге, указанном базовым единым идентификатором ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="f3cd7-136">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base uniform resource identifier (URI).</span></span> <span data-ttu-id="f3cd7-137">В следующем примере кода показан другой способ ссылки на элемент ресурса шрифта — он эквивалентен предыдущему примеру кода.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-137">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="f3cd7-138">Ссылка на шрифты из одного подкаталога приложения</span><span class="sxs-lookup"><span data-stu-id="f3cd7-138">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="f3cd7-139">Вы можете разместить файл содержимого и файл ресурсов приложения в одном пользовательском подкаталоге проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-139">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="f3cd7-140">В следующем примере файла проекта показаны страница содержимого и ресурсы шрифтов, определенные в одном подкаталоге.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-140">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="f3cd7-141">Поскольку содержимое приложения и шрифт находятся в одном подкаталоге, ссылка на шрифт указывается относительно содержимого приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-141">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="f3cd7-142">В следующих примерах показывается, как ссылаться на ресурс шрифтов приложения, когда шрифт находится в том же каталоге, что и приложение.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-142">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="f3cd7-143">Перечисление шрифтов в приложении</span><span class="sxs-lookup"><span data-stu-id="f3cd7-143">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="f3cd7-144">Чтобы перечислить шрифты в качестве элементов ресурса <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> <xref:System.Windows.Media.Fonts.GetTypefaces%2A> в приложении, используйте либо метод.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-144">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="f3cd7-145">В следующем примере показано, как использовать <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> <xref:System.Windows.Media.FontFamily> метод для возвращения коллекции объектов из местоположения шрифта приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-145">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="f3cd7-146">В данном случае приложение содержит подкаталог с именем resources.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-146">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="f3cd7-147">В следующем примере показано, как использовать <xref:System.Windows.Media.Fonts.GetTypefaces%2A> <xref:System.Windows.Media.Typeface> метод для возвращения коллекции объектов из местоположения шрифта приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-147">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="f3cd7-148">В данном случае приложение содержит подкаталог с именем resources.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-148">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="f3cd7-149">Создание библиотеки ресурсов шрифтов</span><span class="sxs-lookup"><span data-stu-id="f3cd7-149">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="f3cd7-150">Вы можете создать библиотеку только для ресурсов, которая содержит только шрифты; в проекте библиотеки этого типа никакой код не включается.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-150">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="f3cd7-151">Создание библиотеки ресурсов является общим приемом для разделения ресурсов и использующего их кода приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-151">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="f3cd7-152">Это также позволяет включать сборку библиотеки в несколько проектов приложений.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-152">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="f3cd7-153">В следующем примере файла проекта показаны основные части проекта библиотеки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-153">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
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
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="f3cd7-154">Ссылка на шрифт в библиотеке ресурсов</span><span class="sxs-lookup"><span data-stu-id="f3cd7-154">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="f3cd7-155">Чтобы сослаться на шрифт в библиотеке ресурсов из приложения, необходимо добавить в ссылку на шрифт префикс с именем сборки библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-155">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="f3cd7-156">В данном случае сборкой ресурсов шрифтов является FontLibrary.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-156">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="f3cd7-157">Для отделения имени сборки от ссылки в сборке используйте символ «;».</span><span class="sxs-lookup"><span data-stu-id="f3cd7-157">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="f3cd7-158">Добавив ключевое слово Component и ссылку на имя шрифта, вы получите полную ссылку на ресурс библиотеки шрифтов.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-158">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="f3cd7-159">В следующем примере кода показано, как сослаться на шрифт в сборке библиотеки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-159">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
> <span data-ttu-id="f3cd7-160">Этот SDK содержит набор образцов шрифтов OpenType, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] которые можно использовать с помощью приложений.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-160">This SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="f3cd7-161">Эти шрифты определяются в библиотеке ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-161">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="f3cd7-162">Дополнительные сведения см. в разделе [Пакет образцов шрифтов OpenType](sample-opentype-font-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f3cd7-162">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a><span data-ttu-id="f3cd7-163">Ограничения в использовании шрифтов</span><span class="sxs-lookup"><span data-stu-id="f3cd7-163">Limitations on Font Usage</span></span>  
 <span data-ttu-id="f3cd7-164">В следующем списке описаны некоторые ограничения на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] упаковку и использование шрифтов в приложениях:</span><span class="sxs-lookup"><span data-stu-id="f3cd7-164">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
- <span data-ttu-id="f3cd7-165">**Биты разрешений на внедрение шрифтов:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не проверяют и не применяют принудительно никакие биты разрешений на внедрение шрифтов.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-165">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="f3cd7-166">Для получения дополнительной информации смотрите раздел [Introduction_to_Packing шрифтов.](#introduction_to_packaging_fonts)</span><span class="sxs-lookup"><span data-stu-id="f3cd7-166">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
- <span data-ttu-id="f3cd7-167">**Шрифты сайта происхождения:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не позволяют ссылку шрифта на идентификатор единого ресурса http или ftp (URI).</span><span class="sxs-lookup"><span data-stu-id="f3cd7-167">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp uniform resource identifier (URI).</span></span>  
  
- <span data-ttu-id="f3cd7-168">**Абсолютный URI с помощью пакета: нотация:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не позволяют создавать <xref:System.Windows.Media.FontFamily> объект программно с помощью "пак:" как часть абсолютного единого идентификатора ресурса (URI) ссылки на шрифт.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-168">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute uniform resource identifier (URI) reference to a font.</span></span> <span data-ttu-id="f3cd7-169">Например, `"pack://application:,,,/resources/#Pericles Light"` является недействительным шрифтом ссылки.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-169">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
- <span data-ttu-id="f3cd7-170">**Автоматическое внедрение шрифтов:** во время разработки не поддерживается поиск шрифтов, используемых приложением, и их автоматическое внедрение в ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-170">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
- <span data-ttu-id="f3cd7-171">**Подмножества шрифтов:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не поддерживают создание подмножеств шрифтов для нефиксированных документов.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-171">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
- <span data-ttu-id="f3cd7-172">Если обнаруживается неправильная ссылка, приложение прибегает к использованию доступного шрифта.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-172">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3cd7-173">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3cd7-173">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [<span data-ttu-id="f3cd7-174">Microsoft Typography: ссылки, новости и контакты</span><span class="sxs-lookup"><span data-stu-id="f3cd7-174">Microsoft Typography: Links, News, and Contacts</span></span>](https://docs.microsoft.com/typography/)
- [<span data-ttu-id="f3cd7-175">Спецификация OpenType</span><span class="sxs-lookup"><span data-stu-id="f3cd7-175">OpenType Specification</span></span>](https://www.microsoft.com/typography/otspec/)
- [<span data-ttu-id="f3cd7-176">Возможности шрифта OpenType</span><span class="sxs-lookup"><span data-stu-id="f3cd7-176">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="f3cd7-177">Образец пакета шрифтов OpenType</span><span class="sxs-lookup"><span data-stu-id="f3cd7-177">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
