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
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45514084"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="c166d-102">Директива x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="c166d-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="c166d-103">Изменяет поведение компиляции XAML при `x:Class` также предоставляется.</span><span class="sxs-lookup"><span data-stu-id="c166d-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="c166d-104">В частности, вместо того чтобы создавать частичной `class` с `Public` обращаться к уровню (по умолчанию), предоставленный `x:Class` создается с `NotPublic` уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="c166d-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="c166d-105">Это поведение влияет на уровень доступа для класса в созданных сборок.</span><span class="sxs-lookup"><span data-stu-id="c166d-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c166d-106">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="c166d-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c166d-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="c166d-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c166d-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="c166d-108">*NotPublic*</span></span>|<span data-ttu-id="c166d-109">Точная строка для указания <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от кода языка программирования, используемом.</span><span class="sxs-lookup"><span data-stu-id="c166d-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="c166d-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="c166d-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="c166d-111">Зависимости</span><span class="sxs-lookup"><span data-stu-id="c166d-111">Dependencies</span></span>  
 <span data-ttu-id="c166d-112">[x: Class](../../../docs/framework/xaml-services/x-class-directive.md) также должен быть предоставлен в том же элементе, и этот элемент должен быть корневым элементом страницы.</span><span class="sxs-lookup"><span data-stu-id="c166d-112">[x:Class](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="c166d-113">Дополнительные сведения см. в разделе [ \[MS-XAML\] разделе 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="c166d-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c166d-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c166d-114">Remarks</span></span>  
 <span data-ttu-id="c166d-115">Значение `x:ClassModifier` в службах XAML .NET Framework использования зависит от языка программирования.</span><span class="sxs-lookup"><span data-stu-id="c166d-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="c166d-116">Строка, используемая зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и преобразователями типов, он возвращает для определения значений для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также является ли этот язык с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="c166d-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="c166d-117">Для C#, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> является `internal`.</span><span class="sxs-lookup"><span data-stu-id="c166d-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="c166d-118">Для Microsoft Visual Basic .NET, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> является `Friend`.</span><span class="sxs-lookup"><span data-stu-id="c166d-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="c166d-119">Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], целевые объекты не существуют, поддерживающие компиляции XAML; таким образом, не указано значение для передачи.</span><span class="sxs-lookup"><span data-stu-id="c166d-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="c166d-120">Можно также указать <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` в C# `Public` в Visual Basic), однако указание <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> делается нечасто, потому, что <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c166d-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="c166d-121">Другие значения, с помощью эквивалентных пользовательский код доступа уровня ограничения, такие как `private` в C#, не являются значимыми для `x:ClassModifier` так, как вложенный класс ссылки не поддерживаются в XAML и, следовательно, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> модификатор имеет тот же эффект.</span><span class="sxs-lookup"><span data-stu-id="c166d-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="c166d-122">Заметки о безопасности</span><span class="sxs-lookup"><span data-stu-id="c166d-122">Security Notes</span></span>  
 <span data-ttu-id="c166d-123">Уровень доступа, как объявлено в `x:ClassModifier` интерпретируется по-прежнему с определенными платформами и их возможности.</span><span class="sxs-lookup"><span data-stu-id="c166d-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="c166d-124">WPF включает возможности для загрузки и создания экземпляров типов где `x:ClassModifier` является `internal`, если этот класс ссылается ресурс WPF с помощью пакета URI-ссылка.</span><span class="sxs-lookup"><span data-stu-id="c166d-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="c166d-125">В результате этот случай и другие пользователи, как и реализацией других платформ, не следует полагаться исключительно на `x:ClassModifier` блокировать создание экземпляра все возможные попытки.</span><span class="sxs-lookup"><span data-stu-id="c166d-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c166d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c166d-126">See Also</span></span>  
 [<span data-ttu-id="c166d-127">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="c166d-127">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="c166d-128">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="c166d-128">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="c166d-129">Директива x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="c166d-129">x:FieldModifier Directive</span></span>](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [<span data-ttu-id="c166d-130">Безопасность (WPF)</span><span class="sxs-lookup"><span data-stu-id="c166d-130">Security (WPF)</span></span>](../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="c166d-131">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="c166d-131">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
