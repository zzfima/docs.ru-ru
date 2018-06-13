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
ms.openlocfilehash: 068a85a5fffd9b7463875695a4b494340ef66cd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548224"
---
# <a name="packaging-fonts-with-applications"></a>Упаковка шрифтов с приложениями
В этом разделе представлены общие сведения по пакета шрифтов с вашей [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложения.  
  
> [!NOTE]
>  Как и с большинством типов программного обеспечения, файлы шрифтов предоставляются по лицензии, а не продаются. Лицензии, регулирующие использование шрифтов, отличаются в зависимости от производителя, но в целом большинство лицензий, в том числе покрывающие шрифты [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] с приложениями и [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], не допускают шрифтов, внедренных в приложениях или в противном случае распространение. Ответственность разработчика состоит в том, чтобы гарантировать наличие требуемых лицензионных прав на любой шрифт, встраиваемый в приложение или распространяемый иными путями.  
  

  
<a name="introduction_to_packaging_fonts"></a>   
## <a name="introduction-to-packaging-fonts"></a>Общие сведения об упаковке шрифтов  
 Можно легко упаковать шрифты в качестве ресурсов в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого на основе приложений для отображения текста пользовательского интерфейса и другие типы текста. Шрифты могут быть отдельными от файлов сборки приложения или включенными в них. Можно также создать библиотеку шрифтов только для ресурсов, на которую может ссылаться приложение.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] и [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] шрифты содержат флаг типа Тип_файловой_системы, указывающее шрифта внедрение лицензирования правами для шрифта. Однако этот флаг типа относится только к внедренным шрифтам, хранящимся в документе; он не относится к шрифтам, внедренным в приложении. Вы можете получить права для шрифта на внедрение путем создания <xref:System.Windows.Media.GlyphTypeface> и ссылки на его <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> свойство. Обратитесь к разделу «OS/2 и Windows метрики» из [спецификации OpenType](http://www.microsoft.com/typography/otspec/os2.htm) Дополнительные сведения о Тип_файловой_системы флаг.  
  
 [Оформления Microsoft](http://www.microsoft.com/typography/links/) контактные данные, которые помогут вам найти поставщика шрифта или найти поставщика шрифтов для настраиваемого включает веб-сайта.  
  
<a name="adding_fonts_as_content_items"></a>   
## <a name="adding-fonts-as-content-items"></a>Добавление шрифтов как элементов содержимого  
 Вы можете добавить шрифты в приложение в виде элементов содержимого проекта, которые отделены от файлов сборки приложения. Это означает, что элементы содержимого не внедряются в сборку в качестве ресурсов. В следующем примере файла проекта показано, как определить элементы содержимого.  
  
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
  
 Чтобы приложение могло использовать шрифты во время выполнения, эти шрифты должны быть доступны в каталоге развертывания приложения. `<CopyToOutputDirectory>` Элемент в файл проекта приложения позволяет автоматически копировать шрифты в каталог развертывания приложения во время сборки. В следующем примере файла проекта показано, как скопировать шрифты в каталог развертывания.  
  
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
  
 В следующем примере кода показано, как ссылаться на шрифт приложения как на элемент содержимого: ссылочный элемент содержимого должен быть в том же каталоге, что и файлы сборки приложения.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## <a name="adding-fonts-as-resource-items"></a>Добавление шрифтов как элементов ресурсов  
 Вы можете добавить шрифты в приложение в виде элементов ресурсов проекта, которые внедряются в файлы сборки приложения. Использование отдельного подкаталога для ресурсов помогает упорядочить файлы проекта приложения. В следующем примере файла проекта показано, как определить шрифты в виде элементов ресурсов в отдельном подкаталоге.  
  
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
>  При добавлении шрифты как ресурсы в приложение, убедитесь, что вы настраиваете `<Resource>` элемент, а не `<EmbeddedResource>` элемент в файл проекта приложения. `<EmbeddedResource>` Элемент для действия сборки не поддерживается.  
  
 В следующем примере разметки показано, как ссылаться на ресурсы шрифтов приложения.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a>Ссылка на элементы ресурсов шрифтов из кода  
 Чтобы ссылаться на элементы ресурса шрифта из кода, необходимо указать ссылку на ресурс шрифта двух частей: базовый [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; и ссылка на размещение шрифта. Эти значения используются в качестве параметров для <xref:System.Windows.Media.FontFamily.%23ctor%2A> метод. В следующем примере кода показано, как ссылаться на ресурсы шрифта приложения в подкаталоге проекта с именем `resources`.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 Базовый [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] может содержать вложенную папку приложения, в котором находится данный ресурс шрифта. В этом случае ссылка на размещение шрифта не требует указания каталога, но будет иметь в начале пути символ "`./`», который показывает ресурс шрифта находится в том же каталоге, который указан с помощью базового [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. В следующем примере кода показан другой способ ссылки на элемент ресурса шрифта — он эквивалентен предыдущему примеру кода.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a>Ссылка на шрифты из одного подкаталога приложения  
 Вы можете разместить файл содержимого и файл ресурсов приложения в одном пользовательском подкаталоге проекта приложения. В следующем примере файла проекта показаны страница содержимого и ресурсы шрифтов, определенные в одном подкаталоге.  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 Поскольку содержимое приложения и шрифт находятся в одном подкаталоге, ссылка на шрифт указывается относительно содержимого приложения. В следующих примерах показывается, как ссылаться на ресурс шрифтов приложения, когда шрифт находится в том же каталоге, что и приложение.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a>Перечисление шрифтов в приложении  
 Для перечисления шрифтов как элементов ресурса в приложении, используйте <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> или <xref:System.Windows.Media.Fonts.GetTypefaces%2A> метод. В следующем примере показано, как использовать <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> метод, чтобы вернуть коллекцию <xref:System.Windows.Media.FontFamily> объекты из расположения приложения шрифтов. В данном случае приложение содержит подкаталог с именем resources.  
  
 [!code-csharp[FontSnippets#FontsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 В следующем примере показано, как использовать <xref:System.Windows.Media.Fonts.GetTypefaces%2A> метод, чтобы вернуть коллекцию <xref:System.Windows.Media.Typeface> объекты из расположения приложения шрифтов. В данном случае приложение содержит подкаталог с именем resources.  
  
 [!code-csharp[FontSnippets#FontsSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## <a name="creating-a-font-resource-library"></a>Создание библиотеки ресурсов шрифтов  
 Вы можете создать библиотеку только для ресурсов, которая содержит только шрифты; в проекте библиотеки этого типа никакой код не включается. Создание библиотеки ресурсов является общим приемом для разделения ресурсов и использующего их кода приложения. Это также позволяет включать сборку библиотеки в несколько проектов приложений. В следующем примере файла проекта показаны основные части проекта библиотеки ресурсов.  
  
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
  
### <a name="referencing-a-font-in-a-resource-library"></a>Ссылка на шрифт в библиотеке ресурсов  
 Чтобы сослаться на шрифт в библиотеке ресурсов из приложения, необходимо добавить в ссылку на шрифт префикс с именем сборки библиотеки. В данном случае сборкой ресурсов шрифтов является FontLibrary. Для отделения имени сборки от ссылки в сборке используйте символ «;». Добавив ключевое слово Component и ссылку на имя шрифта, вы получите полную ссылку на ресурс библиотеки шрифтов. В следующем примере кода показано, как сослаться на шрифт в сборке библиотеки ресурсов.  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  Этот пакет SDK содержит набор образцов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] шрифты, которые можно использовать с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений. Эти шрифты определяются в библиотеке ресурсов. Дополнительные сведения см. в разделе [Пакет образцов шрифтов OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>   
## <a name="limitations-on-font-usage"></a>Ограничения в использовании шрифтов  
 Ниже приведены некоторые ограничения по упаковке и использованию шрифтов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений:  
  
-   **Биты разрешений на внедрение шрифтов:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не проверяют и не применяют принудительно никакие биты разрешений на внедрение шрифтов. В разделе [Introduction_to_Packing шрифты](#introduction_to_packaging_fonts) Дополнительные сведения.  
  
-   **Шрифты узла источника:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не допускают выполнение ссылка на шрифт для http или ftp [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].  
  
-   **Абсолютный URI, с помощью пакета: нотации:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений не позволяют создавать <xref:System.Windows.Media.FontFamily> программно с помощью «пакет:» как часть Абсолютная [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] ссылка на шрифт. Например `"pack://application:,,,/resources/#Pericles Light"` является недопустимой ссылкой на шрифт.  
  
-   **Автоматическое внедрение шрифтов:** во время разработки не поддерживается поиск шрифтов, используемых приложением, и их автоматическое внедрение в ресурсы приложения.  
  
-   **Подмножества шрифтов:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения не поддерживают создание подмножеств шрифтов для нефиксированных документов.  
  
-   Если обнаруживается неправильная ссылка, приложение прибегает к использованию доступного шрифта.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Documents.Typography>  
 <xref:System.Windows.Media.FontFamily>  
 [Оформления Microsoft: Ссылки, новости и контакты](http://www.microsoft.com/typography/links/)  
 [Спецификация OpenType](http://www.microsoft.com/typography/otspec/)  
 [Возможности шрифта OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [Пакет образцов шрифтов OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)
