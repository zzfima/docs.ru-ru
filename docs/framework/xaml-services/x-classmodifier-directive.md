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
ms.openlocfilehash: cc9e866f859192e1fa13ead24dc44a7b9d286877
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58026779"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="d1364-102">Директива x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="d1364-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="d1364-103">Изменяет поведение компиляции XAML при `x:Class` также предоставляется.</span><span class="sxs-lookup"><span data-stu-id="d1364-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="d1364-104">В частности, вместо того чтобы создавать частичной `class` с `Public` обращаться к уровню (по умолчанию), предоставленный `x:Class` создается с `NotPublic` уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="d1364-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="d1364-105">Это поведение влияет на уровень доступа для класса в созданных сборок.</span><span class="sxs-lookup"><span data-stu-id="d1364-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d1364-106">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="d1364-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d1364-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="d1364-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1364-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="d1364-108">*NotPublic*</span></span>|<span data-ttu-id="d1364-109">Точная строка для указания <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от кода языка программирования, используемом.</span><span class="sxs-lookup"><span data-stu-id="d1364-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="d1364-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="d1364-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="d1364-111">Зависимости</span><span class="sxs-lookup"><span data-stu-id="d1364-111">Dependencies</span></span>  
 <span data-ttu-id="d1364-112">[x: Class](x-class-directive.md) также должен быть предоставлен в том же элементе, и этот элемент должен быть корневым элементом страницы.</span><span class="sxs-lookup"><span data-stu-id="d1364-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="d1364-113">Дополнительные сведения см. в разделе [ \[MS-XAML\] разделе 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="d1364-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1364-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1364-114">Remarks</span></span>  
 <span data-ttu-id="d1364-115">Значение `x:ClassModifier` в службах XAML .NET Framework использования зависит от языка программирования.</span><span class="sxs-lookup"><span data-stu-id="d1364-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="d1364-116">Строка, используемая зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и преобразователями типов, он возвращает для определения значений для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также является ли этот язык с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="d1364-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="d1364-117">Для C#, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> является `internal`.</span><span class="sxs-lookup"><span data-stu-id="d1364-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="d1364-118">Для Microsoft Visual Basic .NET, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> является `Friend`.</span><span class="sxs-lookup"><span data-stu-id="d1364-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="d1364-119">Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], целевые объекты не существуют, поддерживающие компиляции XAML; таким образом, не указано значение для передачи.</span><span class="sxs-lookup"><span data-stu-id="d1364-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="d1364-120">Можно также указать <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` в C# `Public` в Visual Basic), однако указание <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> делается нечасто, потому, что <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1364-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="d1364-121">Другие значения, с помощью эквивалентных пользовательский код доступа уровня ограничения, такие как `private` в C#, не являются значимыми для `x:ClassModifier` так, как вложенный класс ссылки не поддерживаются в XAML и, следовательно, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> модификатор имеет тот же эффект.</span><span class="sxs-lookup"><span data-stu-id="d1364-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="d1364-122">Заметки о безопасности</span><span class="sxs-lookup"><span data-stu-id="d1364-122">Security Notes</span></span>  
 <span data-ttu-id="d1364-123">Уровень доступа, как объявлено в `x:ClassModifier` интерпретируется по-прежнему с определенными платформами и их возможности.</span><span class="sxs-lookup"><span data-stu-id="d1364-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="d1364-124">WPF включает возможности для загрузки и создания экземпляров типов где `x:ClassModifier` является `internal`, если этот класс ссылается ресурс WPF с помощью пакета URI-ссылка.</span><span class="sxs-lookup"><span data-stu-id="d1364-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="d1364-125">В результате этот случай и другие пользователи, как и реализацией других платформ, не следует полагаться исключительно на `x:ClassModifier` блокировать создание экземпляра все возможные попытки.</span><span class="sxs-lookup"><span data-stu-id="d1364-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1364-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d1364-126">See also</span></span>
- [<span data-ttu-id="d1364-127">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="d1364-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="d1364-128">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="d1364-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="d1364-129">Директива x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="d1364-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="d1364-130">Безопасность (WPF)</span><span class="sxs-lookup"><span data-stu-id="d1364-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="d1364-131">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="d1364-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
