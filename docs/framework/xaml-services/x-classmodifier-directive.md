---
title: Директива x:ClassModifier
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 5a3bbd1d4d75c84dda741d382c8dd7568dbb474b
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271745"
---
# <a name="xclassmodifier-directive"></a>Директива x:ClassModifier
Изменяет поведение компиляции XAML при `x:Class` также предоставляется. В частности, вместо того чтобы создавать частичной `class` с `Public` обращаться к уровню (по умолчанию), предоставленный `x:Class` создается с `NotPublic` уровень доступа. Это поведение влияет на уровень доступа для класса в созданных сборок.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*NotPublic*|Точная строка для указания <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от кода языка программирования, используемом. См. заметки.|  
  
## <a name="dependencies"></a>Зависимости  
 [x: Class](../../../docs/framework/xaml-services/x-class-directive.md) также должен быть предоставлен в том же элементе, и этот элемент должен быть корневым элементом страницы. Дополнительные сведения см. в разделе [ \[MS-XAML\] разделе 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Примечания  
 Значение `x:ClassModifier` в службах XAML .NET Framework использования зависит от языка программирования. Строка, используемая зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и преобразователями типов, он возвращает для определения значений для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также является ли этот язык с учетом регистра.  
  
-   Для C#, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> является `internal`.  
  
-   Для Microsoft Visual Basic .NET, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> является `Friend`.  
  
-   Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], целевые объекты не существуют, поддерживающие компиляции XAML; таким образом, не указано значение для передачи.  
  
 Можно также указать <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` в C# `Public` в Visual Basic), однако указание <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> делается нечасто, потому, что <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.  
  
 Другие значения, с помощью эквивалентных пользовательский код доступа уровня ограничения, такие как `private` в C#, не являются значимыми для `x:ClassModifier` так, как вложенный класс ссылки не поддерживаются в XAML и, следовательно, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> модификатор имеет тот же эффект.  
  
## <a name="security-notes"></a>Заметки о безопасности  
 Уровень доступа, как объявлено в `x:ClassModifier` интерпретируется по-прежнему с определенными платформами и их возможности. WPF включает возможности для загрузки и создания экземпляров типов где `x:ClassModifier` является `internal`, если этот класс ссылается ресурс WPF с помощью пакета URI-ссылка. В результате этот случай и другие пользователи, как и реализацией других платформ, не следует полагаться исключительно на `x:ClassModifier` блокировать создание экземпляра все возможные попытки.  
  
## <a name="see-also"></a>См. также  
 [Директива x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Код программной части и XAML в WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Директива x:FieldModifier](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [Безопасность (WPF)](../../../docs/framework/wpf/security-wpf.md)  
 [Типы, перенесенные из WPF в System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
