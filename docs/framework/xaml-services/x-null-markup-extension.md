---
title: Расширение разметки x:NULL
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7dbea2c7d4010d8defc572dbdc14a0dfd6d7601e
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484711"
---
# <a name="xnull-markup-extension"></a>Расширение разметки x:NULL
Задает `null` в качестве значения для элемента XAML.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово для пустой ссылки в C# параметре и C++ равно null. Ключевое слово Microsoft Visual Basic для пустой ссылки — `Nothing`это, но всегда используется `{x:Null}` как использование XAML, независимо от того, какой язык кода программной части связан с XAML.  
  
 Расширение `x:Null` разметки не имеет устанавливаемых свойств.  
  
 Использование значения NULL часто связано с выдержкой из XAML-элемента в значении CLR <xref:System.Nullable%601> .  
  
 Расширение разметки, как и все расширения разметки XAML, использует фигурные`{,}`скобки () для экранирования обработки значений атрибутов, отличных от литералов или ссылок обработчиков событий. `x:Null` Синтаксис атрибутов — это синтаксис, который чаще всего используется с этим расширением разметки. Синтаксис `<x:Null />` объектного элемента технически возможен, но редко используется, `x:Null` так как расширение разметки не имеет параметров позиционирования или аргументов конструкции.  
  
 Дополнительные сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 В .NET Framework службах XAML обработка этого расширения разметки определяется <xref:System.Windows.Markup.NullExtension> классом.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Обратите `null` внимание, что не обязательно является начальным значением свойства зависимости ссылочного типа. Начальное значение по умолчанию может различаться для каждого свойства зависимости и может быть основано на метаданных, относящихся к свойству. Многие свойства зависимостей не принимаются `null` в качестве значения с помощью разметки или кода из-за реализаций обратного вызова проверки. Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Общие сведения о языке XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
