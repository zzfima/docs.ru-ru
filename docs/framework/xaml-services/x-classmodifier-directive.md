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
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837237"
---
# <a name="xclassmodifier-directive"></a>Директива x:ClassModifier
Изменяет поведение компиляции XAML, когда также предоставляется `x:Class`. В частности, вместо создания частичного `class` с уровнем доступа `Public` (по умолчанию), предоставленный `x:Class` создается с `NotPublic` уровнем доступа. Это поведение влияет на уровень доступа для класса в создаваемых сборках.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*нотпублик*|Точная строка, которую необходимо передать для указания <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, зависит от используемого языка программирования кода программной части. См. заметки.|  
  
## <a name="dependencies"></a>Зависимости  
 [x:Class](x-class-directive.md) также должен быть указан в том же элементе, и этот элемент должен быть корневым элементом на странице. Дополнительные сведения см. в [разделе\[MS-XAML\] 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="remarks"></a>Заметки  
 Значение `x:ClassModifier` в .NET Framework использовании служб XAML зависит от языка программирования. Используемая строка зависит от того, как каждый язык реализует свой <xref:System.CodeDom.Compiler.CodeDomProvider> и Преобразователи типов, которые он возвращает для определения значений <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также от того, учитывается ли регистр в этом языке.  
  
- Для C#строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, `internal`.  
  
- Для Microsoft Visual Basic .NET строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, является `Friend`.  
  
- Для C++/CLI не существует целей, поддерживающих компиляцию XAML; Поэтому значение для передачи не указано.  
  
 Можно также указать <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` в C#, `Public` в Visual Basic); Однако указание <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> выполняется редко, так как <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.  
  
 Другие значения с эквивалентными ограничениями уровня доступа для пользовательского кода, например `private` C#в, не важны для `x:ClassModifier`, так как ссылки на вложенные классы не поддерживаются в XAML, поэтому модификатор <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> имеет тот же результат.  
  
## <a name="security-notes"></a>Примечания по безопасности  
 Уровень доступа, объявленный в `x:ClassModifier`, по-прежнему подвергается интерпретации определенными платформами и их возможностями. WPF включает возможности для загрузки и создания экземпляров типов, где `x:ClassModifier` `internal`, если на этот класс имеется ссылка из ресурса WPF через ссылку на URI типа "Pack". Как следствие этого, и другие, например, реализованные другими платформами, не полагаются исключительно на `x:ClassModifier` для блокировки всех возможных попыток создания экземпляров.  
  
## <a name="see-also"></a>См. также:

- [Директива x:Class](x-class-directive.md)
- [Код программной части и XAML в WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Директива x:FieldModifier](x-fieldmodifier-directive.md)
- [Безопасность (WPF)](../wpf/security-wpf.md)
- [Типы, перенесенные из WPF в System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
