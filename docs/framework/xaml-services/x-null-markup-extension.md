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
ms.openlocfilehash: 94cfaee9a0a9a9f3892b9df50ac59103709a3b14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562353"
---
# <a name="xnull-markup-extension"></a>Расширение разметки x:NULL
Указывает `null` как значение для элемента XAML.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово для пустую ссылку в C# и [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] имеет значение null. Ключевое слово Microsoft Visual Basic для пустая ссылка является `Nothing`, а всегда используют `{x:Null}` как использование XAML независимо от того, какой язык кода, нужно связать с XAML.  
  
 `x:Null` Расширение разметки получает отсутствуют задаваемые свойства.  
  
 Null использования часто связана с раскрытие член XAML CLR <xref:System.Nullable%601> значение.  
  
 `x:Null` Расширения разметки, например всех расширений разметки XAML использует фигурные скобки (`{,}`) для выходящей обработки значений атрибутов не литералов или ссылки на обработчик событий. Синтаксис атрибутов является синтаксисом, наиболее часто используемым с этим расширением разметки. Синтаксис элемента объекта `<x:Null />` технически возможно, но редко используется, поскольку `x:Null` расширения разметки не имеет позиционные параметры и аргументы построения.  
  
 Сведения о расширениях разметки см. в разделе [расширения разметки и WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 В службах XAML .NET Framework, определяется обработка для данного расширения разметки <xref:System.Windows.Markup.NullExtension> класса.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Обратите внимание, что `null` не обязательно начальное значение не задано для свойства зависимостей ссылочного типа. Начальное значение по умолчанию могут различаться для каждого свойства зависимости и могут быть основаны на метаданные, относящиеся к свойству. Многие свойства зависимостей не принимают `null` как значение, либо в разметке или в коде из-за их реализации обратного вызова проверки. Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [Общие сведения о языке XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Расширения разметки и XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
