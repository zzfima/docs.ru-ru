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
ms.openlocfilehash: 5f0856f50e73a090d0ef624e2fb894d68b73c07e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553325"
---
# <a name="xnull-markup-extension"></a>Расширение разметки x:NULL
Указывает `null` как значение для элемента XAML.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово для ссылкой на null в C# и [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] имеет значение null. Ключевое слово Microsoft Visual Basic, ссылку на null является `Nothing`, но всегда `{x:Null}` как XAML использование независимо от того, какой язык кода, нужно связать с XAML.  
  
 `x:Null` Расширение разметки получает отсутствуют задаваемые свойства.  
  
 Null использования часто связывается с возможностью доступа члена XAML среды CLR <xref:System.Nullable%601> значение.  
  
 `x:Null` Расширения разметки, как и все расширения разметки XAML, используются фигурные скобки (`{,}`) для экранирования обработки значений атрибута не литералы или ссылки на обработчик событий. Синтаксис атрибута является синтаксис, наиболее часто используемый с этим расширением разметки. Синтаксис элемента объекта `<x:Null />` технически возможно, но используется редко, так как `x:Null` расширения разметки не имеет позиционные параметры и аргументы построения.  
  
 Сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 В службах XAML .NET Framework, обработка данного расширения разметки определяется <xref:System.Windows.Markup.NullExtension> класса.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Обратите внимание, что `null` не обязательно начальное значение не задано для свойства зависимостей ссылочного типа. Начальное значение по умолчанию могут различаться для каждого свойства зависимости и могут быть основаны на метаданные, относящиеся к свойствам. Многие свойства зависимостей не принимают `null` как значение, либо через разметки или кода из-за их реализации обратного вызова проверки. Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Общие сведения о языке XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Расширения разметки и XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
