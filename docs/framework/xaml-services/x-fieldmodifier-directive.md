---
title: Директива x:FieldModifier
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: c20564bcf8a25b1b59887fbefe6419671e0d6c03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971871"
---
# <a name="xfieldmodifier-directive"></a>Директива x:FieldModifier
Изменяет поведение компиляции XAML таким образом, чтобы поля для ссылки на именованные объекты определяются с помощью <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> доступа вместо <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> поведение по умолчанию.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*Public*|Точная строка передается укажите <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от кода языка программирования, который используется. См. заметки.|  
  
## <a name="dependencies"></a>Зависимости  
 Если используется XAML рабочей `x:FieldModifier` в любом месте, необходимо объявить корневой элемент XAML производственные [директива x: Class](x-class-directive.md).  
  
## <a name="remarks"></a>Примечания  
 `x:FieldModifier` не относится к объявлению общего уровня доступа класса или его членов. Это касается только поведение обработки XAML в тех случаях, когда конкретного объекта XAML, который является частью рабочей XAML обрабатывается и становится объектом, который потенциально может быть доступен в графе объектов приложения. По умолчанию ссылка на поле в такой ситуации являются закрытыми, что предотвращает непосредственное изменение графа объектов пользователей элемента управления. Вместо этого управления потребители должны изменять граф объектов с помощью стандартных шаблонов, включенных по модели программирования, таких как путем получения корневым элементом макета, дочерний элемент коллекции, выделенные открытые свойства, и так далее.  
  
 Значение для `x:FieldModifier` атрибута различается в зависимости от языка программирования, и его назначение могут различаться в конкретных платформах. Строка, используемая зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и преобразователями типов, он возвращает для определения значений для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также является ли этот язык с учетом регистра.  
  
- Для C#, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> является `public`.  
  
- Для Microsoft Visual Basic .NET, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> является `Public`.  
  
- Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], нет целевых объектов для XAML в настоящее время существует; таким образом, строка, передаваемая не определено.  
  
 Можно также указать <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` в C#, `Friend` в Visual Basic) но указав <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> необычен поскольку `NotPublic` , поведение уже используется по умолчанию.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> значение по умолчанию, так как это редко, что кода за пределами сборки XAML требуется доступ к элементу XAML создан. Архитектура безопасности WPF вместе с поведение компиляции XAML не объявляйте поля, которые содержат экземпляры элементов как public, если только специально настроены, `x:FieldModifier` допускает открытый доступ.  
  
 `x:FieldModifier` применяется только для элементов с [директива x: Name](x-name-directive.md) так, как это имя используется для ссылки на поле после он является открытым.  
  
 По умолчанию разделяемый класс для корневого элемента является открытым; Тем не менее, вы может сделать его закрытым, с помощью [директива x: ClassModifier](x-classmodifier-directive.md). [Директива x: ClassModifier](x-classmodifier-directive.md) также влияет на уровень доступа для экземпляра класса корневого элемента. Вы можете поместить оба `x:Name` и `x:FieldModifier` на корневой элемент, но это только создается копия открытого поля корневого элемента, а значение true, корневой элемент класса уровень доступа по-прежнему управляет [директива x: ClassModifier](x-classmodifier-directive.md).  
  
## <a name="see-also"></a>См. также

- [Код XAML и пользовательские классы для WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Код программной части и XAML в WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Директива x:Name](x-name-directive.md)
- [Построение приложения WPF](../wpf/app-development/building-a-wpf-application-wpf.md)
- [Директива x:ClassModifier](x-classmodifier-directive.md)
