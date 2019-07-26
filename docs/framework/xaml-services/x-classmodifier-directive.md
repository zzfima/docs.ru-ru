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
ms.openlocfilehash: c3c08f61b49a6367663cf02099dda86d1a692284
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484750"
---
# <a name="xclassmodifier-directive"></a>Директива x:ClassModifier
Изменяет поведение компиляции XAML, если `x:Class` также предоставляется. В частности, вместо создания частичного `class` уровня, `Public` имеющего уровень доступа (по умолчанию), `x:Class` `NotPublic` предоставленный объект создается с уровнем доступа. Это поведение влияет на уровень доступа для класса в создаваемых сборках.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*нотпублик*|Точная строка, которую необходимо передать в <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> параметре, и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от используемого языка программирования кода программной части. См. заметки.|  
  
## <a name="dependencies"></a>Зависимости  
 [x:Class](x-class-directive.md) также должен быть указан в том же элементе, и этот элемент должен быть корневым элементом на странице. Дополнительные сведения см [ \[. в разделе 4.3.1.8 в\] MS-XAML](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Примечания  
 Значение `x:ClassModifier` в .NET Framework службах XAML зависит от языка программирования. Используемая строка зависит от того, как каждый язык реализует <xref:System.CodeDom.Compiler.CodeDomProvider> его и какие преобразователи типов он возвращает, чтобы определить значения для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также указать, учитывается ли регистр в этом языке.  
  
- Для C#строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , —. `internal`  
  
- Для Microsoft Visual Basic .NET строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , — это. `Friend`  
  
- Для C++/CLI не существует целей, поддерживающих компиляцию XAML; Поэтому значение для передачи не указано.  
  
 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Можно также указать (`public` в C#, `Public` в Visual Basic), однако указание <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> выполняется редко, так как <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.  
  
 Другие значения с эквивалентными ограничениями уровня доступа для пользовательского кода, `private` например C#в, не являются значимыми для `x:ClassModifier` , поскольку ссылки на вложенные классы не поддерживаются <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> в XAML, поэтому модификатор имеет тот же результат. .  
  
## <a name="security-notes"></a>Примечания по безопасности  
 Уровень доступа, объявленный в `x:ClassModifier` , по-прежнему подвергается интерпретации определенными платформами и их возможностями. WPF включает возможности для загрузки и создания экземпляров типов, `x:ClassModifier` где `internal`имеет значение, если на этот класс имеется ссылка из ресурса WPF через ссылку на URI типа "Pack". Как следствие этого случая и другие, например, реализованные другими платформами, не полагайтесь исключительно на `x:ClassModifier` блокировку всех возможных попыток создания экземпляров.  
  
## <a name="see-also"></a>См. также

- [Директива x:Class](x-class-directive.md)
- [Код программной части и XAML в WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Директива x:FieldModifier](x-fieldmodifier-directive.md)
- [Безопасность (WPF)](../wpf/security-wpf.md)
- [Типы, перенесенные из WPF в System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
