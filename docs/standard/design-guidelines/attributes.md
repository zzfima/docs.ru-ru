---
title: Attributes1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86fa2556e6b8fb82e31a7d4753354aa2dff627ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="attributes"></a><span data-ttu-id="6176f-102">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6176f-102">Attributes</span></span>
<span data-ttu-id="6176f-103"><xref:System.Attribute?displayProperty=nameWithType>базовый класс, используемый для определения настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6176f-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="6176f-104">Атрибуты представляют собой заметки, которые могут быть добавлены программным элементам, например сборок, типов, членов и параметров.</span><span class="sxs-lookup"><span data-stu-id="6176f-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="6176f-105">Они хранятся в метаданных сборки и может быть доступен во время выполнения с помощью API отражения.</span><span class="sxs-lookup"><span data-stu-id="6176f-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="6176f-106">Например, платформа определяет <xref:System.ObsoleteAttribute>, который может применяться на тип или член, чтобы указать, что тип или член является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="6176f-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="6176f-107">Атрибуты могут иметь одно или несколько свойств, которые используются для передачи дополнительных данных, связанный с атрибутом.</span><span class="sxs-lookup"><span data-stu-id="6176f-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="6176f-108">Например `ObsoleteAttribute` может содержать дополнительную информацию о версии, в которой есть устаревшие тип или член и описание новых интерфейсов API, заменив устаревшего API.</span><span class="sxs-lookup"><span data-stu-id="6176f-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="6176f-109">При применении атрибута, необходимо указать некоторые свойства атрибута.</span><span class="sxs-lookup"><span data-stu-id="6176f-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="6176f-110">Эти называются необходимые свойства или обязательных аргументов, так как они представлены в виде конструктор позиционных параметров.</span><span class="sxs-lookup"><span data-stu-id="6176f-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="6176f-111">Например <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> свойство <xref:System.Diagnostics.ConditionalAttribute> является обязательным свойством.</span><span class="sxs-lookup"><span data-stu-id="6176f-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="6176f-112">Свойства, которые не обязательно быть указаны при применении атрибута, называются дополнительных свойств (или необязательные аргументы).</span><span class="sxs-lookup"><span data-stu-id="6176f-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="6176f-113">Они представлены устанавливаемые свойства.</span><span class="sxs-lookup"><span data-stu-id="6176f-113">They are represented by settable properties.</span></span> <span data-ttu-id="6176f-114">Компиляторы содержат специальный синтаксис для установки этих свойств при применении атрибута.</span><span class="sxs-lookup"><span data-stu-id="6176f-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="6176f-115">Например <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> свойство представляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="6176f-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="6176f-116">**✓ СДЕЛАТЬ** имя классы настраиваемых атрибутов с суффиксом «Attribute».</span><span class="sxs-lookup"><span data-stu-id="6176f-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="6176f-117">**СДЕЛАТЬ ✓** применить <xref:System.AttributeUsageAttribute> для настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6176f-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="6176f-118">**✓ СДЕЛАТЬ** предоставляют настраиваемые свойства для необязательных аргументов.</span><span class="sxs-lookup"><span data-stu-id="6176f-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="6176f-119">**✓ СДЕЛАТЬ** обеспечения обязательные аргументы свойства только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6176f-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="6176f-120">**✓ СДЕЛАТЬ** предоставляют параметры конструктора для инициализации свойства, соответствующие обязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="6176f-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="6176f-121">Каждый параметр должен иметь то же имя (хотя и с разным регистром) как соответствующее свойство.</span><span class="sxs-lookup"><span data-stu-id="6176f-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="6176f-122">**X ИЗБЕГАЙТЕ** указав аргументы конструктора для инициализации свойства, соответствующие необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="6176f-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="6176f-123">Другими словами не имеют свойства, которые могут быть установлены с конструктор и метод задания.</span><span class="sxs-lookup"><span data-stu-id="6176f-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="6176f-124">Данное правило позволяет явным образом указать, какие аргументы являются необязательными и какие необходимы, позволяет избежать необходимости два способа сделать то же самое.</span><span class="sxs-lookup"><span data-stu-id="6176f-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="6176f-125">**X ИЗБЕГАЙТЕ** перегрузку конструкторов настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6176f-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="6176f-126">Явно имеющие только один конструктор сообщает пользователю, какие аргументы являются обязательными, а какие нет.</span><span class="sxs-lookup"><span data-stu-id="6176f-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="6176f-127">**✓ СДЕЛАТЬ** запечатать классы настраиваемых атрибутов, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="6176f-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="6176f-128">Ускоряется подстановки для атрибута.</span><span class="sxs-lookup"><span data-stu-id="6176f-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="6176f-129">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="6176f-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6176f-130">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6176f-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6176f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="6176f-131">See Also</span></span>  
 [<span data-ttu-id="6176f-132">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="6176f-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="6176f-133">Рекомендации по использованию</span><span class="sxs-lookup"><span data-stu-id="6176f-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
