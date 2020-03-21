---
title: Код-позади и XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 32283d5b81bf92999a97711ded13a8b533ae3028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145349"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Код программной части и XAML в WPF
<a name="introduction"></a>Code-behind — это термин, используемый для описания кода, который [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] соединен с объектами, определяемыми разметкой, когда страница компилируется разметкой. Эта тема описывает требования к код-за, а также альтернативный механизм внестроки кода для кода в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Этот раздел состоит из следующих подразделов.  
  
- [Предварительные требования](#Prerequisites)  
  
- [Код-позади и язык XAML](#codebehind_and_the_xaml_language)  
  
- [Требования к код-закутанию, обработчику событий и частичному классу в WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Код](#x_Code)  
  
- [Ограничения в коде inline](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Эта тема предполагает, что вы прочитали [обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) и имеете некоторые базовые знания clR и объектно-ориентированного программирования.  
  
<a name="codebehind_and_the_xaml_language"></a>
## <a name="code-behind-and-the-xaml-language"></a>Код-позади и язык XAML  
 Язык XAML включает функции языкового уровня, которые позволяют связать файлы кода с файлами разметки со стороны файла разметки. В частности, язык XAML определяет языковые функции [x:Class Directive,](../../../desktop-wpf/xaml-services/xclass-directive.md) [x:Subclass Directive](../../../desktop-wpf/xaml-services/xsubclass-directive.md)и [x:ClassModifier Directive.](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md) То, как именно должен быть подготовлен код и как интегрировать разметку и код, не является частью того, что указывает язык XAML. Это остается до таких рамок, как WPF, чтобы определить, как интегрировать код, как использовать XAML в приложениях и программировании моделей, а также действия сборки или другую поддержку, что все это требует.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Требования к код-закутанию, обработчику событий и частичному классу в WPF  
  
- Частичный класс должен происходить от типа, который поддерживает корневой элемент.  
  
- Обратите внимание, что при поведении по умолчанию составных действий сборки разметки можно оставить производнете пустым в частичном определении класса на стороне кода. Компилированный результат будет считать, что тип поддержки корней страницы будет основой для частичного класса, даже если он не указан. Однако, опираясь на такое поведение не является лучшей практикой.  
  
- Обработчики событий, которые вы записываете в коде, должны быть методами экземпляра и не могут быть статичными методами. Эти методы должны быть определены частичным классом `x:Class`в пространстве имен CLR, идентифицированным . Вы не можете квалифицировать имя обработчика событий, чтобы поручить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработчику для поиска обработчика событий для проводки событий в другой области класса.  
  
- Обработчик должен соответствовать делегату для соответствующего события в системе резервного типа.  
  
- Специально для базового языка Microsoft Visual Можно `Handles` использовать ключевое слово для обработчиков с случаями и событиями в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]декларации обработчика, вместо того, чтобы прикреплять обработчики с атрибутами в . Однако этот метод имеет некоторые `Handles` ограничения, поскольку ключевое слово [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не может поддерживать все специфические функции системы событий, такие как определенные маршрутизированные сценарии событий или прилагаемые события. Для получения подробной информации [см.](visual-basic-and-wpf-event-handling.md)  
  
<a name="x_Code"></a>
## <a name="xcode"></a>x:Код  
 [x:Код](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) является директивным [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]элементом, определенным в . Элемент `x:Code` директивы может содержать код внее программирования. Код, который определен в строке, может взаимодействовать с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] на одной и той же странице. Ниже приводится пример, иллюстрирующий вонючий код C-кода. Обратите внимание, что `x:Code` код находится внутри элемента и `<CDATA[`что код должен быть окружен ... `]]>` чтобы избежать содержимого для XML, так что [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор (интерпретация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] либо схемы или схемы) не будет пытаться интерпретировать содержимое буквально как XML.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>
## <a name="inline-code-limitations"></a>Ограничения в коде inline  
 Следует обдумать возможность избежать или ограничить использование вненужного кода. С точки зрения архитектуры и философии кодирования, поддержание разделения между разметкой и код-за держит дизайнера и разработчика ролей гораздо более четко. На более техническом уровне код, который вы пишете для вонюнного кода, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может быть неудобно писать, потому что вы всегда пишете в сгенерированный частичный класс и можете использовать только отображение пространства имен по умолчанию XML. Поскольку вы `using` не можете добавлять операторы, необходимо полностью квалифицировать многие вызовы API, которые вы делаете. Отображение по умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает большинство, но не [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] все пространства имен CLR, которые присутствуют в сборках; вам придется полностью квалифицировать вызовы к типам и членам, содержащимся в других областях имен CLR. Вы также не можете определить что-либо, кроме частичного класса в вонном коде, и все сущности кода пользователя, на которые вы ссылаетесь, должны существовать как член или переменная в сгенерированном частичном классе. Другие специфические языковые `#ifdef` функции программирования, такие как макросы или против глобальных переменных или переменные сборки, также недоступны. Для получения дополнительной [информации см.](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)  
  
## <a name="see-also"></a>См. также раздел

- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Встроенный тип XAML x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [Построение приложения WPF](../app-development/building-a-wpf-application-wpf.md)
- [Подробное описание синтаксиса XAML](xaml-syntax-in-detail.md)
