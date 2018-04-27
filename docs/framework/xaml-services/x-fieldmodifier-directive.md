---
title: Директива x:FieldModifier
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: 15
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eccad019bf18c56c23864c7a1559ce5076d954bb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="84048-102">Директива x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="84048-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="84048-103">Изменяет поведение компиляции XAML таким образом, чтобы определенных полей для ссылки на именованный объект с <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> доступа вместо <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="84048-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="84048-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="84048-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="84048-105">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="84048-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84048-106">*Public*</span><span class="sxs-lookup"><span data-stu-id="84048-106">*Public*</span></span>|<span data-ttu-id="84048-107">Точная строка передается укажите <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от кода языка программирования, который используется.</span><span class="sxs-lookup"><span data-stu-id="84048-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="84048-108">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="84048-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="84048-109">Зависимости</span><span class="sxs-lookup"><span data-stu-id="84048-109">Dependencies</span></span>  
 <span data-ttu-id="84048-110">Если рабочей среды XAML использует `x:FieldModifier` в любом месте, необходимо объявить корневой элемент XAML производственные [директива x: Class](../../../docs/framework/xaml-services/x-class-directive.md).</span><span class="sxs-lookup"><span data-stu-id="84048-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84048-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="84048-111">Remarks</span></span>  
 <span data-ttu-id="84048-112">`x:FieldModifier` не относится к объявлению общего уровня доступа класса или его члены.</span><span class="sxs-lookup"><span data-stu-id="84048-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="84048-113">Это касается только поведение обработки XAML, когда обрабатывается определенный объект XAML, который является частью рабочей среды XAML и становится объектом, который потенциально может быть доступен в графе объектов приложения.</span><span class="sxs-lookup"><span data-stu-id="84048-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="84048-114">По умолчанию ссылка на поле для такого объекта остается закрытой, что предотвращает непосредственное изменение графа объектов пользователей элемента управления.</span><span class="sxs-lookup"><span data-stu-id="84048-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="84048-115">Вместо этого потребители управления ожидаются изменения граф объектов с помощью стандартных шаблонов, которые включены по модели программирования, таких как путем получения корня макет дочерних коллекций элементов, выделенных открытых свойств и так далее.</span><span class="sxs-lookup"><span data-stu-id="84048-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="84048-116">Значение для `x:FieldModifier` атрибута различается в зависимости от языка программирования, и его назначение могут различаться в конкретных платформах.</span><span class="sxs-lookup"><span data-stu-id="84048-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="84048-117">Строка, используемая зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и преобразователей типов, он возвращает для определения значений для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, и является ли этот язык с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="84048-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="84048-118">Для C#, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> — `public`.</span><span class="sxs-lookup"><span data-stu-id="84048-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
-   <span data-ttu-id="84048-119">Для Microsoft Visual Basic .NET, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> — `Public`.</span><span class="sxs-lookup"><span data-stu-id="84048-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
-   <span data-ttu-id="84048-120">Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], целевые объекты не XAML в настоящее время существует; таким образом, строка, передаваемая не определено.</span><span class="sxs-lookup"><span data-stu-id="84048-120">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="84048-121">Можно также указать <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` в C# `Friend` в Visual Basic) но указание <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> маловероятна поскольку `NotPublic` уже поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="84048-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="84048-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> происходит по умолчанию, так как это редко, что кода за пределами сборки XAML необходим доступ к элемент создан в XAML.</span><span class="sxs-lookup"><span data-stu-id="84048-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="84048-123">Архитектура безопасности WPF вместе с поведение компиляции XAML не объявляйте поля, которые содержат экземпляры элементов как public, если только специально настроены, `x:FieldModifier` разрешен открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="84048-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="84048-124">`x:FieldModifier` применяется только для элементов с [директива x: Name](../../../docs/framework/xaml-services/x-name-directive.md) так, как это имя используется для ссылки на поле после он является открытым.</span><span class="sxs-lookup"><span data-stu-id="84048-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="84048-125">По умолчанию разделяемый класс для корневого элемента является открытым; Тем не менее, его можно сделать закрытым путем с помощью [директива x: ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span><span class="sxs-lookup"><span data-stu-id="84048-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span></span> <span data-ttu-id="84048-126">[Директива x: ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md) также влияет на уровень доступа для экземпляра класса корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="84048-126">The [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="84048-127">Можно поместить как `x:Name` и `x:FieldModifier` на корневой элемент, но это только создается копия открытого поля корневого элемента, а true корневой элемент класса уровень доступа по-прежнему управляется [директива x: ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span><span class="sxs-lookup"><span data-stu-id="84048-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84048-128">См. также</span><span class="sxs-lookup"><span data-stu-id="84048-128">See Also</span></span>  
 [<span data-ttu-id="84048-129">Код XAML и пользовательские классы для WPF</span><span class="sxs-lookup"><span data-stu-id="84048-129">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [<span data-ttu-id="84048-130">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="84048-130">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="84048-131">Директива x:Name</span><span class="sxs-lookup"><span data-stu-id="84048-131">x:Name Directive</span></span>](../../../docs/framework/xaml-services/x-name-directive.md)  
 [<span data-ttu-id="84048-132">Построение приложения WPF</span><span class="sxs-lookup"><span data-stu-id="84048-132">Building a WPF Application (WPF)</span></span>](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="84048-133">Директива x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="84048-133">x:ClassModifier Directive</span></span>](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
