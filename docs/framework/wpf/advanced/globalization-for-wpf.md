---
title: "Глобализация для WPF | Microsoft Docs"
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
  - "глобализация"
  - "международный интерфейс пользователя, XAML"
  - "XAML, глобализация"
  - "XAML, международный интерфейс пользователя"
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Глобализация для WPF
В этом разделе рассматриваются проблемы, на которые следует обратить внимание при написании приложений [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] для мирового рынка.  Элементы программирования, относящиеся к глобализации, определены в платформе [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] в пространстве имен `System.Globalization`.  
  
   
  
<a name="xaml_globalization"></a>   
## Глобализация и язык XAML  
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] основан на [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] и использует поддержку глобализации, определенную в спецификации [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  В следующих подразделах описаны некоторые возможности [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], на которые следует обратить внимание.  
  
<a name="char_reference"></a>   
### Ссылки на символы  
 Ссылка на символы дает код определенного символа [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]а, который она представляет \(в десятичном или шестнадцатеричном формате\).  В следующем примере показана ссылка на символы в десятичном формате.  
  
```  
Ϩ  
```  
  
 В этом примере показана ссылка на символы в шестнадцатеричном формате.  Обратите внимание, что в начале шестнадцатеричного числа стоит **x**.  
  
```  
Ϩ  
```  
  
<a name="encoding"></a>   
### Кодировка  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] поддерживает следующие кодировки: [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF\-16 и UTF\-8.  Оператор кодировки должен находиться в начале документа [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Если атрибут кодировки и метка порядка следования байтов не указаны, средство синтаксического анализа использует по умолчанию кодировку UTF\-8.  UTF\-8 и UTF\-16 — предпочитаемые кодировки.  Кодировка UTF\-7 не поддерживается.  В следующем примере демонстрируется указание кодировки UTF\-8 в файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
```  
?xml encoding="UTF-8"?  
```  
  
<a name="lang_attrib"></a>   
### Атрибут языка  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] использует [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) для представления атрибута языка элемента.  Чтобы воспользоваться преимуществами класса <xref:System.Globalization.CultureInfo>, значение атрибута языка должно являться одним из языков и региональных параметров, определенных классом <xref:System.Globalization.CultureInfo>.  [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) является наследуемым в дереве элементов \(по правилам XML, а не обязательно из\-за наследования свойств зависимостей\) и имеет в качестве значения по умолчанию пустую строку, если значение не назначено явно.  
  
 Атрибут языка очень полезен для указания вариантов языка.  Например, французский язык имеет различную орфографию, словарь и произношение во Франции, Квебеке, Бельгии и Швейцарии.  Также китайский, японский и корейский языки имеют общие кодовые точки в [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], но их идеограммы различны, и они используют полностью различные шрифты.  
  
 В следующем примере [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] используется атрибут языка `fr-CA` для указания языка "французский \(Канада\)".  
  
```  
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>  
```  
  
<a name="unicode"></a>   
### Unicode  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] поддерживает все возможности [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]а, включая суррогаты.  До тех пор, пока кодировка может быть сопоставлена с [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]ом, она поддерживается.  Например, GB18030 содержит некоторые символы, которые сопоставляются с китайским, японским и корейским \(CFK\) расширением языков A и B и суррогатными парами, поэтому она полностью поддерживается.  Приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может использовать <xref:System.Globalization.StringInfo> для обработки строк, не имея информации о том, имеют ли они суррогатные пары или несамостоятельные знаки.  
  
<a name="design_intl_ui_with_xaml"></a>   
## Разработка многоязыкового пользовательского интерфейса с помощью языка XAML  
 В этом подразделе описаны возможности [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], которые следует учитывать при написании приложений.  
  
<a name="intl_text"></a>   
### Многоязыковый текст  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает в себя встроенную обработку всех поддерживаемых платформой [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] систем письма.  
  
 В настоящее время поддерживаются следующие системы письма:  
  
-   Арабский  
  
-   бенгальский язык;  
  
-   деванагари;  
  
-   Кириллическая  
  
-   Греческий  
  
-   Гуджарати  
  
-   гурмукхи;  
  
-   Иврит  
  
-   Идеографические системы  
  
-   Каннада  
  
-   Лаосская  
  
-   Латинская  
  
-   малаялам;  
  
-   Монгольский  
  
-   Ория  
  
-   Сирийский  
  
-   Тамильский  
  
-   Телугу  
  
-   Таана  
  
-   Тайская\*  
  
-   Тибетская  
  
 \*В этом выпуске отображение и изменение текста на тайском языке поддерживается, но отсутствует разбиение по словам.  
  
 В настоящее время не поддерживаются следующие системы письма:  
  
-   Кхмерская  
  
-   Корейская \(старый вариант хангыль\)  
  
-   Мьянма  
  
-   Сингальская  
  
 Все обработчики систем письма поддерживают шрифты [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  Шрифты [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] могут включать таблицы макетов [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], которые позволяют создателям шрифтов разрабатывать более качественные международные и типографские шрифты.  Таблицы макетов шрифтов [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] содержат сведения о заменах и размещении глифов, выравнивании и размещении на базовом плане, что позволяет приложениям по обработке текста улучшить макет текста.  
  
 Шрифты [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] позволяют обрабатывать большие наборы глифов, используя кодировку [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)].  Такая кодировка позволяет обеспечить широкую многоязыковую поддержку, а также поддержку типографских вариантов глифов.  
  
 Отрисовка текста [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует субпиксельную технологию [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], которая обеспечивает независимость от разрешения.  Это значительно улучшает читаемость и предоставляет возможность поддержки документов журнального стиля высокого качества для всех систем письма.  
  
<a name="intl_layout"></a>   
### Международное письмо  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет очень удобный способ поддержки горизонтального, двунаправленного и вертикального письма.  В Presentation Framework свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> может быть использовано для определения направления.  Шаблонами направления являются:  
  
-   *LeftToRight* — горизонтальная разметка для латинского языка, восточноазиатских языков и т. д.  
  
-   *RightToLeft*— двунаправленная разметка для арабского языка, иврита и т. д.  
  
<a name="developing_localizable_apps"></a>   
## Разработка локализуемых приложений  
 При написании приложений для мирового рынка следует предусматривать возможность локализации приложения.  В следующих подразделах рассмотрены вопросы, которые следует учитывать.  
  
<a name="mui"></a>   
### Многоязыковой пользовательский интерфейс  
 Многоязыковые пользовательские интерфейсы \(MUI\) — это поддержка [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] для переключения [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] с одного языка на другой.  Приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует модель сборок для поддержки MUI.  Приложение содержит независимые от языка сборки, а также зависимые от языка, вспомогательные сборки ресурсов.  Точкой входа является управляемый EXE\-файл в основной сборке.  Загрузчик ресурсов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует диспетчер ресурсов [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] для поддержки поиска и резервирования ресурсов.  Многоязыковые вспомогательные сборки работают с одной и той же основной сборкой.  Загруженная сборка ресурса зависит от <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> текущего потока.  
  
<a name="localizable_ui"></a>   
### Локализуемый пользовательский интерфейс  
 Приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используют [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для определения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] позволяет разработчикам указывать иерархию объектов с набором свойств и логикой.  Основным применением [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] является разработка приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], но его можно также использовать для указания иерархии любых объектов [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  Большинство разработчиков используют [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для указания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложений и используют язык программирования, например [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], для реагирования на действия пользователя.  
  
 С точки зрения ресурса [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], разработанный для описания зависимого от языка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], является элементом ресурса и поэтому должна существовать возможность локализовать его окончательный распространяемый формат, с целью обеспечения многоязыковой поддержки.  Поскольку [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не может обрабатывать события, многие приложения, использующие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержат для этого блоки кода.  Дополнительные сведения см. в разделе [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  Когда файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] размечается в BALM\-форму языка XAML, код исключается и компилируется в разные двоичные файлы. Файлы, изображения и другие типы управляемых объектов ресурсов BALM\-формы языка XAML внедряются во вспомогательную сборку ресурсов, которая может быть локализована на другие языки, или в основную сборку, если локализация не требуется.  
  
> [!NOTE]
>  Приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают все ресурсы [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], включая таблицы строк, изображения и т.д.  
  
<a name="building_localizable_apps"></a>   
### Построение локализуемых приложений  
 Локализация означает настройку [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для различных языков и региональных параметров.  Чтобы предоставить возможность локализации приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], разработчики должны встроить все локализуемые ресурсы в сборку ресурсов.  Сборка ресурсов локализуется на разные языки, и фоновый код использует API управления ресурсами [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для загрузки.  Одним из файлов, необходимым для приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], является файл проекта \(PROJ\).  Все ресурсы, которые используются в приложении, должны быть включены в файл проекта.  Следующий пример из CSPROJ\-файла показывает, как это сделать.  
  
```  
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>  
```  
  
 Для использования ресурсов в приложении создайте экземпляр <xref:System.Resources.ResourceManager> и загрузите ресурс, который необходимо использовать.  В следующем примере показано, как это сделать.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]  
  
<a name="using_clickonce"></a>   
## Использование ClickOnce с локализованными приложениями  
 ClickOnce — это новая технология развертывания Windows Forms, которая будет поставляться с [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  Она позволяет устанавливать и обновлять веб\-приложения.  Когда приложение, которое было развернуто с помощью ClickOnce, локализовано, его можно просматривать только с применением языка и региональных параметров локализации.  Например, если развертываемое приложение локализовано на японский язык, его можно просматривать только на японском языке [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)], а не на английском языке [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  Это представляет собой проблему, поскольку для японских пользователей запускать английскую версию [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)] — это обычная ситуация.  
  
 Решением этой проблемы является задание резервного атрибута нейтрального языка.  Разработчик приложения может при необходимости удалить ресурсы из основной сборки и указать, что ресурсы можно найти во вспомогательной сборке, соответствующей определенному языку и региональным параметрам.  Для управления этим процессом используйте <xref:System.Resources.NeutralResourcesLanguageAttribute>.  Конструктор класса <xref:System.Resources.NeutralResourcesLanguageAttribute> имеет две сигнатуры, одна из которых принимает параметр <xref:System.Resources.UltimateResourceFallbackLocation>, чтобы указать расположение, в которое <xref:System.Resources.ResourceManager> должен извлечь резервные ресурсы: основную и вспомогательную сборки.  В следующем примере показано использование атрибута.  В качестве окончательного резервного расположения код вынуждает <xref:System.Resources.ResourceManager> искать ресурсы в подкаталоге "de" каталога, выполняющейся в данный момент сборки.  
  
```  
[assembly: NeutralResourcesLanguageAttribute(  
    "de" , UltimateResourceFallbackLocation.Satellite)]  
  
```  
  
## См. также  
 [Общие сведения о глобализации и локализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)