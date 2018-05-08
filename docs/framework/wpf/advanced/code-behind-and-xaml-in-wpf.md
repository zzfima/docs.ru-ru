---
title: Код программной части и XAML в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 09d4f010ca53c5e3d2d9dede172e7ae2102261b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="code-behind-and-xaml-in-wpf"></a>Код программной части и XAML в WPF
<a name="introduction"></a> Выделенный код — это термин, используемый для описания кода, который объединяется с объектами, определенными разметкой, при [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы, скомпилированного с разметкой. В этом разделе описываются требования для кода, а также альтернативный механизм встроенного кода для кода в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Необходимые компоненты](#Prerequisites)  
  
-   [Код программной части и языка XAML](#codebehind_and_the_xaml_language)  
  
-   [Кода, обработчик событий и требования разделяемого класса в WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [x: Code](#x_Code)  
  
-   [Ограничения встроенного кода](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе предполагается, что вы прочитали [Обзор XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) и иметь базовые знания о [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] и объектно ориентированного программирования.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Код программной части и языка XAML  
 Язык XAML включает возможности языка, упрощающие можно связать с файлами разметки, со стороны файла разметки файлы кода. В частности, язык XAML задает функции языка [директива x: Class](../../../../docs/framework/xaml-services/x-class-directive.md), [директива x: Subclass](../../../../docs/framework/xaml-services/x-subclass-directive.md), и [директива x: ClassModifier](../../../../docs/framework/xaml-services/x-classmodifier-directive.md). Точно как код должен создаваться и как интегрировать разметку и код, не является частью указывает языка XAML. Он остается до платформы, например WPF, чтобы определить, как интегрировать в коде, как для использования XAML в приложении и моделей программирования и построение действия или другие поддерживать, все это требуется.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Кода, обработчик событий и требования разделяемого класса в WPF  
  
-   Разделяемый класс должен быть производным от типа, который возвращает корневой элемент.  
  
-   Обратите внимание, что в группе по умолчанию поведение действий сборки компиляции разметки, можно оставить наследование пустым в определении разделяемого класса на стороне кода. Скомпилированный результат будет считать резервного типа корневой страницы, чтобы служить основой для разделяемого класса, даже если он не указан. Однако полагаться на это поведение не рекомендуется.  
  
-   Обработчики событий, создаваемых в коде должны быть методами экземпляра и не может быть статические методы. Эти методы должны быть определены разделяемым классом в пространстве имен среды CLR, определяемый `x:Class`. Нельзя уточнить имя обработчика событий, чтобы указать [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора для поиска для обработчика событий для события, написанного в другой области класса.  
  
-   Обработчик должен соответствовать делегату для соответствующего события в системе резервных типов.  
  
-   Для языка Microsoft Visual Basic в частности, можно использовать конкретного языка `Handles` ключевое слово, чтобы связать обработчики с экземплярами и событиями в объявлении обработчика, вместо присоединения обработчиков с атрибутами в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Однако этот метод имеет некоторые ограничения, так как `Handles` ключевое слово не поддерживает все особые функции [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] системы событий, такие как определенные сценарии перенаправленных событий или вложенные события. Дополнительные сведения см. в разделе [Visual Basic и обработка событий WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x: Code  
 [x: Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) определен элемент директивы в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. `x:Code` Директива может содержать встроенный программный код. Код, определенный встроенным может взаимодействовать с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] на одной странице. В следующем примере показано встроенного кода C#. Обратите внимание, что код внутри `x:Code` элемент, и что код должен быть заключен в `<CDATA[`... `]]>` Чтобы избежать содержимого для [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], после чего [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора (либо Интерпретация [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] схемы или [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] схемы) не будет пытаться интерпретировать содержимое буквально как [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Ограничения встроенного кода  
 Следует избегать или ограничивать использование встроенного кода. С точки зрения архитектуры и философии кодирования обеспечение разделения между разметки и кода сохраняет роли конструктора и разработчика гораздо более четкое. На более техническом уровне код, написанный для встроенного кода может быть неудобно записи, поскольку разработчик всегда пишет в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] созданный разделяемый класс и может использовать только сопоставления пространства имен XML по умолчанию. Так как не удается добавить `using` инструкций, необходимо указывать полное многие [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] вызовов. Значение по умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сопоставления включают большинство, но не все [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] пространства имен, которые присутствуют в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сборки; необходимо будет полностью определить вызовы типы и члены, содержащиеся в других пространствах имен среды CLR. Также любых других разделяемый класс нельзя определить во встроенном коде, и все сущности пользовательского кода, ссылки на которые должны существовать в качестве членов или переменных внутри созданного разделяемого класса. Другие программирования функции для конкретных языков, такими как макросы или `#ifdef` глобальные переменные или переменные сборки, не также доступны. Дополнительные сведения см. в разделе [встроенный тип XAML x: Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Встроенный тип XAML x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)  
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
