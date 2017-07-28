---
title: "Код программной части и XAML в WPF | Microsoft Docs"
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
  - "файлы с выделенным кодом, XAML"
  - "XAML, выделенный код"
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Код программной части и XAML в WPF
<a name="introduction"></a> Выделенный код – это термин, используемый для описания кода, который объединяется с объектами, определенными разметкой, когда страница [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] является страницей с компилированной разметкой.  В данном разделе описываются требования для выделенного кода, а также альтернативный механизм встроенного кода для кода в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Предварительные требования](#Prerequisites)  
  
-   [Выделенный код и язык XAML](#codebehind_and_the_xaml_language)  
  
-   [Требования для выделенного кода, обработчика событий и разделяемого класса в WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [x:Code](#x_Code)  
  
-   [Ограничения встроенного кода](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## Предварительные требования  
 Для понимания данного раздела необходимо ознакомиться с [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) и иметь базовые знания о [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] и объектно\-ориентированном программировании.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## Выделенный код и язык XAML  
 Язык XAML включает функции на уровне языка, которые делают возможным сопоставление файлов кода с файлами разметки, со стороны файла разметки.  В частности, язык XAML задает функции языка [Директива x:Class](../../../../docs/framework/xaml-services/x-class-directive.md), [Директива x:Subclass](../../../../docs/framework/xaml-services/x-subclass-directive.md) и [Директива x:ClassModifier](../../../../docs/framework/xaml-services/x-classmodifier-directive.md).  То, как код должен создаваться, и как следует объединять код и разметку, не является тем, что задает язык XAML.  Определение, каким образом следует объединять код, как использовать язык XAML в приложениях и программных моделях, а также действия построения и другая поддержка, которая все это требует, оставлены платформам, таким как WPF.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## Требования для выделенного кода, обработчика событий и разделяемого класса в WPF  
  
-   Разделяемый класс должен быть производным от типа, который возвращает корневой элемент.  
  
-   Следует отметить, что при использовании поведения действий построения компилированной разметки, установленного по умолчанию, можно оставить наследование пустым в определении разделяемого класса на стороне выделенного кода.  Компилированный результат будет предполагать, что резервный тип корня страницы будет базовым для разделяемого класса, даже если он не указан.  Однако полагаться на это поведение не рекомендуется.  
  
-   Обработчики событий, прописанные в выделенном коде, должны быть методами экземпляров, и не могут быть статическими методами.  Эти методы должны быть определены разделяемым классом в пространстве имен среды CLR, идентифицированным по `x:Class`.  Нельзя уточнить имя обработчика событий, чтобы указать процессору [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] искать этот обработчик для события, написанного в другой области класса.  
  
-   Обработчик должен соответствовать делегату для соответствующего события в системе резервного типа.  
  
-   Специально для языка [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] можно использовать ключевое слово \(конкретно для этого языка\) `Handles`, чтобы связать обработчики с экземплярами и событиями в объявлении обработчика, вместо присоединения обработчиков с атрибутами в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Однако этот метод имеет некоторые ограничения, поскольку ключевое слово `Handles` не поддерживает все особые функции системы событий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как определенные сценарии перенаправленных событий или вложенные события.  Дополнительные сведения см. в разделе [Обработка событий в Visual Basic и WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## x:Code  
 [x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) является элементом директивы, заданным в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Элемент директивы `x:Code` может содержать встроенный программный код.  Код, определенный встроенным образом, может взаимодействовать с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] на той же странице.  В следующем примере продемонстрирован встроенный код [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)].  Обратите внимание, что код находится внутри элемента `x:Code` и код должен быть заключен в `<CDATA[`... `]]>`, чтобы избежать содержимого для [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], так что обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(интерпретирующий либо схему [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], либо схему [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\) не будет пытаться интерпретировать содержимое политерально, как [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## Ограничения встроенного кода  
 Следует избегать или ограничивать использование встроенного кода.  В терминах архитектуры и философии кодирования обеспечение разделения между разметкой и выделенным кодом лучше разделяет роли конструктора и разработчика.  На более техническом уровне код, написанный для встроенного кода, может быть неудобным в плане записи, поскольку разработчик всегда пишет в создаваемом разделяемом классе [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и может использовать только сопоставления пространства имен XML по умолчанию.  Поскольку нельзя добавить операторы `using`, следует полностью определять множество производимых вызовов [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].  Сопоставления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию включают большинство, но не все пространства имен [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], присутствующие в сборках [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]; понадобится указывать полные имена в вызовах типов и элементов, содержащихся в других пространствах имен среды CLR.  Также во встроенном коде нельзя определить что\-либо за пределами разделяемого класса, и все сущности пользовательского кода должны существовать в качестве членов или переменных внутри созданного разделяемого класса.  Другие зависимые от конкретного языка программирования возможности, такие как макросы или `#ifdef` применительно к глобальным переменным или переменным построения, также недоступны.  Дополнительные сведения см. в разделе [Встроенный тип XAML x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md).  
  
## См. также  
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Встроенный тип XAML x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)   
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)