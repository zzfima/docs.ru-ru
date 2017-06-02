---
title: "Упаковка шрифтов с приложениями | Microsoft Docs"
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
  - "приложения, упаковка шрифтов"
  - "шрифты, упаковка с приложениями"
  - "упаковка шрифтов с приложениями"
  - "оформление, упаковка шрифтов с приложениями"
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Упаковка шрифтов с приложениями
В этом разделе представлены общие сведения по упаковыванию шрифтов с приложением [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
> [!NOTE]
>  Как и для большинства типов программного обеспечения, файлы шрифтов подлежат лицензированию, а не продаже.  Лицензии, регулирующие использование шрифтов, отличаются в зависимости от производителя, но в целом большинство лицензий, в том числе покрывающие ресурсы шрифтов [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] с приложениями и [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], не разрешают внедрение шрифтов в приложения или распространение каким\-либо иным образом.  Ответственность разработчика состоит в том, чтобы гарантировать наличие требуемых лицензионных прав на любой шрифт, встраиваемый в приложение или распространяемый иными путями.  
  
   
  
<a name="introduction_to_packaging_fonts"></a>   
## Основные сведения об упаковке шрифтов  
 Можно легко упаковать шрифты в качестве ресурсов в создаваемых приложениях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для отображения текста интерфейса пользователя и других типов содержимого на основе текста.  Шрифты могут быть отделены от файлов сборки приложения или внедрены в них.  Также можно создать библиотеку шрифтов, содержащую только ресурсы, на которую может ссылаться приложение.  
  
 Шрифты [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] и [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] содержат флаг типа fsType, указывающий на наличие лицензионных прав на внедрение для конкретного шрифта.  Однако этот флаг типа ссылается только на внедренные шрифты, хранящиеся в документе, — он не ссылается на шрифты, внедренные в приложение.  Права на внедрение для шрифта можно извлечь, создав объект <xref:System.Windows.Media.GlyphTypeface> и ссылки на его свойство <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A>.  Дополнительные сведения о флаге fsType см. в разделе "Метрики OS\/2 и Windows" документа [Спецификации OpenType](http://www.microsoft.com/typography/otspec/OS2.htm).  
  
 Веб\-узел [Microsoft Typography](http://www.microsoft.com/typography/Links/) содержит контактные сведения, которые помогут найти поставщика определенного шрифта или найти поставщика шрифтов для создания специального шрифта.  
  
<a name="adding_fonts_as_content_items"></a>   
## Добавление шрифтов как элементов содержимого  
 Можно добавлять шрифты в приложение в виде элементов содержимого проекта, которые располагаются отдельно от файлов сборки приложения.  Это означает, что элементы содержимого не внедряются в качестве ресурсов в сборку.  В следующем примере файла проекта показано определение элементов содержимого.  
  
```  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 Чтобы убедиться, что приложение может использовать шрифты во время выполнения, шрифты должны быть доступны в папке развертывания приложения.  В файле проекта приложения элемент `<CopyToOutputDirectory>` позволяет во время процесса построения автоматически копировать шрифты в каталог развертывания приложения.  В следующем примере файла проекта показано, как скопировать шрифты в каталог развертывания.  
  
```  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 В следующем примере демонстрируется создание ссылки на шрифт приложения как на элемент содержимого \(элемент содержимого, на который указывает ссылка, должен быть в том же каталоге, что и файлы сборки приложения\).  
  
 [!code-xml[FontSnippets#FontPackageSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## Добавление шрифтов как элементов ресурса  
 Можно добавить шрифты в создаваемое приложение в виде элементов ресурсов проекта, которые внедрены в файлы сборки приложения.  Использование отдельного подкаталога для ресурсов помогает организовать файлы проекта приложения.  Следующий пример файла проекта показывает, как определить шрифты как элементы ресурса в отдельном подкаталоге.  
  
```  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
>  При добавлении в приложение шрифтов в качестве ресурсов, убедитесь, что в данном файле проекта приложения задается элемент `<Resource>`, а не элемент `<EmbeddedResource>`.  Элемент `<EmbeddedResource>` для действия построения не поддерживается.  
  
 В следующем примере разметки демонстрируется создание ссылки на ресурсы шрифта приложения.  
  
 [!code-xml[FontSnippets#FontPackageSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### Создание ссылок на элементы ресурса шрифта из кода  
 Чтобы из кода ссылаться на элементы ресурса шрифта, необходимо указать ссылку на ресурс шрифта, состоящую из двух частей: базового [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] и ссылки на размещение шрифта.  Эти значения используются в качестве параметров для метода <xref:System.Windows.Media.FontFamily.%23ctor%2A>.  В следующем примере кода демонстрируется создание ссылки на ресурсы шрифта приложения в подкаталоге проекта с именем `resources`.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 Базовый [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] может включать подкаталог приложения, где постоянно хранится ресурс шрифта.  В этом случае ссылка на размещение шрифта не требует указания каталога, но должна иметь в начале пути символ "`./`", который показывает, что ресурс шрифта находится в том же каталоге, что указан с помощью базового [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].  Следующий пример кода демонстрирует альтернативный способ ссылки на элементы ресурса шрифта — он эквивалентен предыдущему примеру кода.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### Создание ссылок на шрифты из одного подкаталога приложения  
 Можно поместить содержимое приложения и файлы ресурса в одном и том же, определяемом пользователем, подкаталоге проекта приложения.  Следующий пример файла проекта демонстрирует страницу содержимого и ресурсы шрифта, определенные в одном подкаталоге.  
  
```  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 Поскольку содержимое приложения и шрифт находятся в одном подкаталоге, ссылка шрифта относится к содержимому приложения.  В следующих примерах демонстрируется создание ссылки на ресурсы шрифта приложения, если шрифт находится в том же каталоге, что приложение.  
  
 [!code-xml[FontSnippets#FontPackageSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### Перечисление шрифтов в приложении  
 Для перечисления шрифтов как элементов ресурса в приложении используйте метод <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> или <xref:System.Windows.Media.Fonts.GetTypefaces%2A>.  В следующем примере показано использование метода <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> для возврата коллекции объектов <xref:System.Windows.Media.FontFamily> из папки, в которой размещается шрифт приложения.  В этом случае приложение содержит подкаталог с именем resources.  
  
 [!code-csharp[FontSnippets#FontsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 В следующем примере показано использование метода <xref:System.Windows.Media.Fonts.GetTypefaces%2A> для возврата коллекции объектов <xref:System.Windows.Media.Typeface> из папки, в которой размещается шрифт приложения.  В этом случае приложение содержит подкаталог с именем resources.  
  
 [!code-csharp[FontSnippets#FontsSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## Создание библиотеки ресурса шрифта  
 Можно создать библиотеку ресурса, которая содержит только шрифты \(код не является частью этого типа проекта библиотеки\).  Создание библиотеки ресурсов является общим приемом для разделения ресурсов и использующего их кода приложения.  Также это позволяет включать сборку библиотеки наряду с несколькими проектами приложений.  В следующем примере файла проекта показаны части ключа проекта библиотеки ресурса.  
  
```  
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
  
### Ссылка на шрифт в библиотеке ресурсов  
 Чтобы из приложения сослаться на шрифт в библиотеке ресурсов, необходимо поставить имя сборки библиотеки в начале ссылки на шрифт.  В этом случае сборкой ресурса шрифта является FontLibrary.  Чтобы в сборке отделить имя сборки от ссылки, используйте знак ";".  Добавление ключевого слова Component сразу за ссылкой на имя шрифта завершает полную ссылку на ресурс библиотеки шрифта.  В следующем примере демонстрируется создание ссылки на шрифт в сборке библиотеки ресурса.  
  
 [!code-xml[OpenTypeFontsSample#OpenTypeFontsSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  Этот набор SDK содержит набор образцов шрифтов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], которые можно использовать с приложениями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Шрифты определяются в библиотеке ресурса.  Дополнительные сведения см. в разделе [Образец пакета шрифтов OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>   
## Ограничения в использовании шрифта  
 В списке ниже приведены некоторые ограничения по упаковке и использованию шрифтов в приложениях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **биты разрешения внедрения шрифтов.** Приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не проверяют и не выполняют принудительно биты разрешения внедрения шрифта.  Дополнительные сведения см. в разделе [Общие\_сведения\_об\_упаковке\_шрифтов](#introduction_to_packaging_fonts);  
  
-   **шрифты узла источника.** Приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не позволяют шрифту ссылаться на [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] типа http или ftp;  
  
-   **абсолютный URI, использующий нотацию pack:.** Приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не позволяют программно создавать объект <xref:System.Windows.Media.FontFamily>, используя нотацию "pack:" в качестве части ссылки на шрифт в виде абсолютного [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].  Например, `"pack://application:,,,/resources/#Pericles Light"` является недопустимой ссылкой на шрифт;  
  
-   **автоматическое внедрение шрифтов.** Во время разработки не поддерживается поиск и использование шрифтов приложением, а также автоматическое внедрение шрифтов в ресурсы приложения;  
  
-   **подмножества шрифтов.** Приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не поддерживают создание подмножеств шрифта для нефиксированных документов.  
  
-   При наличии неправильной ссылки приложение возвращается к использованию доступного шрифта.  
  
## См. также  
 <xref:System.Windows.Documents.Typography>   
 <xref:System.Windows.Media.FontFamily>   
 [Microsoft Typography: Links, News, and Contacts](http://www.microsoft.com/typography/links/)   
 [OpenType Specification](http://www.microsoft.com/typography/otspec/)   
 [Возможности шрифта OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [Образец пакета шрифтов OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)