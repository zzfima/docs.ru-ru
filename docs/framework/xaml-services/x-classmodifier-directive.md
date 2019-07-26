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
# <a name="xclassmodifier-directive"></a><span data-ttu-id="d97b9-102">Директива x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="d97b9-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="d97b9-103">Изменяет поведение компиляции XAML, если `x:Class` также предоставляется.</span><span class="sxs-lookup"><span data-stu-id="d97b9-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="d97b9-104">В частности, вместо создания частичного `class` уровня, `Public` имеющего уровень доступа (по умолчанию), `x:Class` `NotPublic` предоставленный объект создается с уровнем доступа.</span><span class="sxs-lookup"><span data-stu-id="d97b9-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="d97b9-105">Это поведение влияет на уровень доступа для класса в создаваемых сборках.</span><span class="sxs-lookup"><span data-stu-id="d97b9-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d97b9-106">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="d97b9-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d97b9-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="d97b9-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d97b9-108">*нотпублик*</span><span class="sxs-lookup"><span data-stu-id="d97b9-108">*NotPublic*</span></span>|<span data-ttu-id="d97b9-109">Точная строка, которую необходимо передать в <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> параметре, и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от используемого языка программирования кода программной части.</span><span class="sxs-lookup"><span data-stu-id="d97b9-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="d97b9-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="d97b9-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="d97b9-111">Зависимости</span><span class="sxs-lookup"><span data-stu-id="d97b9-111">Dependencies</span></span>  
 <span data-ttu-id="d97b9-112">[x:Class](x-class-directive.md) также должен быть указан в том же элементе, и этот элемент должен быть корневым элементом на странице.</span><span class="sxs-lookup"><span data-stu-id="d97b9-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="d97b9-113">Дополнительные сведения см [ \[. в разделе 4.3.1.8 в\] MS-XAML](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="d97b9-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d97b9-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d97b9-114">Remarks</span></span>  
 <span data-ttu-id="d97b9-115">Значение `x:ClassModifier` в .NET Framework службах XAML зависит от языка программирования.</span><span class="sxs-lookup"><span data-stu-id="d97b9-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="d97b9-116">Используемая строка зависит от того, как каждый язык реализует <xref:System.CodeDom.Compiler.CodeDomProvider> его и какие преобразователи типов он возвращает, чтобы определить значения для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также указать, учитывается ли регистр в этом языке.</span><span class="sxs-lookup"><span data-stu-id="d97b9-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="d97b9-117">Для C#строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , —. `internal`</span><span class="sxs-lookup"><span data-stu-id="d97b9-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="d97b9-118">Для Microsoft Visual Basic .NET строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , — это. `Friend`</span><span class="sxs-lookup"><span data-stu-id="d97b9-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="d97b9-119">Для C++/CLI не существует целей, поддерживающих компиляцию XAML; Поэтому значение для передачи не указано.</span><span class="sxs-lookup"><span data-stu-id="d97b9-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="d97b9-120"><xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Можно также указать (`public` в C#, `Public` в Visual Basic), однако указание <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> выполняется редко, так как <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d97b9-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="d97b9-121">Другие значения с эквивалентными ограничениями уровня доступа для пользовательского кода, `private` например C#в, не являются значимыми для `x:ClassModifier` , поскольку ссылки на вложенные классы не поддерживаются <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> в XAML, поэтому модификатор имеет тот же результат. .</span><span class="sxs-lookup"><span data-stu-id="d97b9-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="d97b9-122">Примечания по безопасности</span><span class="sxs-lookup"><span data-stu-id="d97b9-122">Security Notes</span></span>  
 <span data-ttu-id="d97b9-123">Уровень доступа, объявленный в `x:ClassModifier` , по-прежнему подвергается интерпретации определенными платформами и их возможностями.</span><span class="sxs-lookup"><span data-stu-id="d97b9-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="d97b9-124">WPF включает возможности для загрузки и создания экземпляров типов, `x:ClassModifier` где `internal`имеет значение, если на этот класс имеется ссылка из ресурса WPF через ссылку на URI типа "Pack".</span><span class="sxs-lookup"><span data-stu-id="d97b9-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="d97b9-125">Как следствие этого случая и другие, например, реализованные другими платформами, не полагайтесь исключительно на `x:ClassModifier` блокировку всех возможных попыток создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d97b9-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97b9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d97b9-126">See also</span></span>

- [<span data-ttu-id="d97b9-127">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="d97b9-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="d97b9-128">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="d97b9-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="d97b9-129">Директива x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="d97b9-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="d97b9-130">Безопасность (WPF)</span><span class="sxs-lookup"><span data-stu-id="d97b9-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="d97b9-131">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="d97b9-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
