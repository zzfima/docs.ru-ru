---
title: "Универсальные шаблоны в XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 05eaab4497949231d32ceab0ba696b9f252d67ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="generics-in-xaml"></a>Универсальные шаблоны в XAML
Служб .NET Framework XAML, как он реализован в сборке System.Xaml обеспечивает поддержку с помощью универсальных типов среды CLR. Эта поддержка включает Указание ограничений универсальных типов в качестве аргумента типа и применение ограничения путем вызова соответствующего `Add` метод для универсальных коллекций. В этом разделе описываются аспекты использования и ссылки на универсальных типов в XAML.  
  
## <a name="xtypearguments"></a>x: TypeArguments  
 `x:TypeArguments`является директивой, определенной в языке XAML. Когда она используется в качестве члена типа XAML, универсальный тип, поддерживаемый `x:TypeArguments` передает аргументы универсального резервному конструктору типов ограничений. Для синтаксиса ссылки, относящиеся к службами XAML .NET Framework использование `x:TypeArguments`, включая примеры синтаксиса см. в разделе [директива x: TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Поскольку `x:TypeArguments` принимает строку и обладает резервированием преобразователя типов, обычно он объявляется в использовании XAML как атрибут.  
  
 В потоке узлов XAML сведения, объявленные атрибутом `x:TypeArguments` можно получить из <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> в `StartObject` позицию в потоке узлов. Возвращаемое значение <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> приведен список <xref:System.Xaml.XamlType> значения. Определение, является ли тип XAML представляет универсальный тип можно сделать путем вызова <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Правила и соглашения о синтаксисе для универсальных типов в XAML  
 В XAML универсальный тип всегда должны быть представлены как ограниченного универсальным; произвольные универсальным никогда не присутствует в системе типов XAML или в потоке узлов XAML и не могут быть представлены в разметке XAML. Универсальный можно ссылаться в пределах синтаксиса атрибутов XAML, в случае, если ограничение вложенного типа, на который ссылается универсального `x:TypeArguments`, или в случаях, где `x:Type` предоставляет ссылку типа CLR для универсального типа. Эта возможность поддерживается через <xref:System.Xaml.Schema.XamlTypeTypeConverter> класса, определенного в службах XAML .NET Framework.  
  
 Включаемые форма синтаксиса атрибутов XAML <xref:System.Xaml.Schema.XamlTypeTypeConverter> изменяет типичные MSIL / CLR синтаксис соглашение, которое использует угловые скобки для типов и ограничений универсальных типов, а вместо этого заменяет круглые скобки контейнером ограничения. Пример см. в разделе [директива x: TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Универсальные типы и возможности XAML 2009 г.  
 При использовании XAML 2009 вместо сопоставления CLR базовые типы для получения типов XAML для общих примитивов языка, можно использовать [встроенные типы XAML 2009](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) сведения в виде элементов `x:TypeArguments`. Например, можно объявить следующее (префикс сопоставления не отображаются, но `x` находится в пространстве имен XAML языка XAML для XAML 2009 г.):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Поддержка универсальных типов в WPF и других платформах версии 3.5  
 Для использования XAML 2006 при нацеливании WPF, в частности [x: Class](../../../docs/framework/xaml-services/x-class-directive.md) также должен быть предоставлен в том же элементе, как `x:TypeArguments`, и этот элемент должен быть корневым элементом документа XAML. Корневой элемент необходимо сопоставить с по крайней мере один аргумент типа универсального типа. Например, <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Возможные обходные пути для поддержки использований универсальных типов включают определение пользовательского расширения разметки, можно возвращать универсальные типы, или указать обертки, является производным от универсального типа, но выполняет сведение универсальное ограничение в определении класса определения класса.  
  
 В WPF и предназначенных для [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], можно использовать возможности XAML 2009 вместе с `x:TypeArguments`, но только для свободного XAML (XAML, который не является компилированной разметки). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.  
  
 Пользовательские рабочие процессы в [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] для [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] не поддерживают универсальное использование XAML.  
  
## <a name="see-also"></a>См. также  
 [Директива x:TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md)  
 [Директива x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Встроенные типы для общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
