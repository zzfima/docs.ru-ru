---
title: Универсальные шаблоны в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: ddd094d5acb1eea5bf45984c27df93d1de3d53fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491315"
---
# <a name="generics-in-xaml"></a>Универсальные шаблоны в XAML
Службы .NET Framework XAML, реализованное в System.Xaml обеспечивает поддержку использования универсальных типов среды CLR. Эта поддержка включает Указание ограничений универсальных типов в качестве аргумента типа и устанавливающий ограничение, вызвав соответствующий `Add` метод для универсальных коллекций. В этом разделе описаны аспекты использования и ссылки на универсальные типы в XAML.  
  
## <a name="xtypearguments"></a>x: TypeArguments  
 `x:TypeArguments` является директивой, определенной в языке XAML. При использовании в качестве члена типа XAML, который поддерживается службой универсального типа, `x:TypeArguments` передает аргументы универсального резервному конструктору типов ограничений. Для синтаксиса ссылки, относящиеся к службами XAML .NET Framework использовать `x:TypeArguments`, включая примеры синтаксиса, см. в разделе [x: TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Так как `x:TypeArguments` принимает строку и обладает резервированием преобразователя типов, обычно он объявляется в использовании XAML как атрибут.  
  
 В потоке узлов XAML, сведения, объявленные атрибутом `x:TypeArguments` можно получить из <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> в `StartObject` позицию в потоке узлов. Возвращаемое значение <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> приведен список <xref:System.Xaml.XamlType> значения. Определение универсального типа представляет ли тип XAML можно сделать, вызвав <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Правила и соглашения о синтаксисе для универсальных типов в XAML  
 В XAML универсальный тип всегда должно быть представлено как ограниченное универсальным; без ограничений универсального никогда не присутствует в системе типов XAML или поток узлов XAML и не могут быть представлены в разметке XAML. Универсальный можно ссылаться в синтаксисе атрибутов XAML для случаев, когда он является ограничение вложенный тип, на которую ссылается универсальный `x:TypeArguments`, или в случаях, где `x:Type` предоставляет ссылку на тип CLR для универсального типа. Это согласуется с <xref:System.Xaml.Schema.XamlTypeTypeConverter> класса, определенного службами XAML платформы .NET Framework.  
  
 Форма синтаксиса, включаемые атрибутов XAML <xref:System.Xaml.Schema.XamlTypeTypeConverter> изменяет типичный MSIL / CLR синтаксис соглашение, которое использует угловые скобки для типов и ограничений универсальных типов и вместо этого заменяет круглые скобки контейнером ограничения. Например, см. в разделе [x: TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Универсальные типы и возможности XAML 2009  
 При использовании XAML 2009 вместо сопоставление среды CLR базовые типы для получения типов XAML для общих примитивов языка, можно использовать [встроенные типы XAML 2009](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) сведения в виде элементов `x:TypeArguments`. Например, можно объявить следующее (сопоставления префиксов не показаны, но `x` является пространство имен XAML языка XAML для XAML 2009 г.):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Поддержка универсальных типов в WPF и других платформах версии 3.5  
 Для использования XAML 2006 при создается специально для WPF [x: Class](../../../docs/framework/xaml-services/x-class-directive.md) также должен быть предоставлен в том же элементе, как `x:TypeArguments`, и этот элемент должен быть корневым в документе XAML. Корневой элемент необходимо сопоставить с хотя бы один тип аргумента универсального типа. Например, <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Возможных решений для поддержки универсального использования включают определение пользовательского расширения разметки, можно возвращать универсальные типы, или предоставляя обертки определение, является производным от универсального типа, но смягчает универсальное ограничение в свой собственный класс определения класса.  
  
 В WPF и определение целевых объектов [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], можно использовать возможности XAML 2009 вместе с `x:TypeArguments`, но только для свободного XAML (XAML, который не является компилированной разметкой). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.  
  
 Пользовательские рабочие процессы в Windows Workflow Foundation для [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] не поддерживают универсального использования XAML.  
  
## <a name="see-also"></a>См. также
- [Директива x:TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md)
- [Директива x:Class](../../../docs/framework/xaml-services/x-class-directive.md)
- [Встроенные типы для общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
