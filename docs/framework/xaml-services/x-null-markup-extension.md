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
ms.openlocfilehash: ff82b0bfc1983240431e582dbd78778dc4469241
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459942"
---
# <a name="xnull-markup-extension"></a>Расширение разметки x:NULL
Указывает `null` как значение для элемента XAML.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Заметки  
 Ключевое слово для пустой ссылки в C# параметре и C++ равно null. Ключевое слово Microsoft Visual Basic для пустой ссылки имеет `Nothing`, но в качестве использования XAML всегда используется `{x:Null}`, независимо от того, какой язык кода программной части связан с XAML.  
  
 Расширение разметки `x:Null` не имеет устанавливаемых свойств.  
  
 Использование значения NULL часто связано с выкрытием члена XAML <xref:System.Nullable%601> значение CLR.  
  
 Расширение разметки `x:Null`, как и все расширения разметки XAML, использует фигурные скобки (`{,}`) для экранирования обработки значений атрибутов, отличных от литералов или ссылок обработчиков событий. Синтаксис атрибутов — это синтаксис, который чаще всего используется с этим расширением разметки. Синтаксис объектного элемента `<x:Null />` технически возможно, но редко используется, поскольку у расширения разметки `x:Null` нет позиционированных параметров или аргументов создания.  
  
 Дополнительные сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 В .NET Framework службах XAML обработка этого расширения разметки определяется классом <xref:System.Windows.Markup.NullExtension>.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Обратите внимание, что `null` не обязательно является начальным значением свойства зависимости ссылочного типа. Начальное значение по умолчанию может различаться для каждого свойства зависимости и может быть основано на метаданных, относящихся к свойству. Многие свойства зависимостей не принимают `null` в качестве значения с помощью разметки или кода из-за реализаций обратного вызова проверки. Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Общие сведения о языке XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
