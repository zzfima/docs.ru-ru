---
title: Атрибутов1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51aa91b1acbae9f1a15ac12441090dd4c1c2dcb1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259510"
---
# <a name="attributes"></a><span data-ttu-id="9b56a-102">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b56a-102">Attributes</span></span>
<span data-ttu-id="9b56a-103"><xref:System.Attribute?displayProperty=nameWithType> базовый класс, используемый для определения настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9b56a-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="9b56a-104">Атрибуты представляют собой заметки, которые могут добавляться для элементов программирования, включая сборки, типов, членов и параметров.</span><span class="sxs-lookup"><span data-stu-id="9b56a-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="9b56a-105">Они хранятся в метаданных сборки и может осуществляться во время выполнения с помощью интерфейсов API отражения.</span><span class="sxs-lookup"><span data-stu-id="9b56a-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="9b56a-106">Например, платформа Framework определяет <xref:System.ObsoleteAttribute>, который может применяться на тип или член, чтобы указать, что тип или член является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="9b56a-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="9b56a-107">Атрибуты могут иметь одно или несколько свойств, которые используются для передачи дополнительных данных, связанный с атрибутом.</span><span class="sxs-lookup"><span data-stu-id="9b56a-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="9b56a-108">Например `ObsoleteAttribute` может содержать дополнительную информацию о выпуске, в который получили нерекомендуемым типом или членом и приводится описание новых интерфейсов API, заменяя устаревший API.</span><span class="sxs-lookup"><span data-stu-id="9b56a-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="9b56a-109">Некоторые свойства атрибута должны быть заданы, при применении атрибута.</span><span class="sxs-lookup"><span data-stu-id="9b56a-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="9b56a-110">Они называются как обязательные свойства или требуемые аргументы, так как они отображаются в виде параметров позиционные конструктора.</span><span class="sxs-lookup"><span data-stu-id="9b56a-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="9b56a-111">Например <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> свойство <xref:System.Diagnostics.ConditionalAttribute> является обязательным свойством.</span><span class="sxs-lookup"><span data-stu-id="9b56a-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="9b56a-112">Свойства, которые не обязательно указывать при применении атрибута, называются необязательные свойства (или необязательные аргументы).</span><span class="sxs-lookup"><span data-stu-id="9b56a-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="9b56a-113">Они представлены устанавливаемые свойства.</span><span class="sxs-lookup"><span data-stu-id="9b56a-113">They are represented by settable properties.</span></span> <span data-ttu-id="9b56a-114">Компиляторы предоставляют специального синтаксиса для установки этих свойств, когда применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="9b56a-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="9b56a-115">Например <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> свойство представляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="9b56a-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="9b56a-116">**✓ DO** имя классы настраиваемых атрибутов с суффиксом «Attribute».</span><span class="sxs-lookup"><span data-stu-id="9b56a-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="9b56a-117">**✓ DO** применить <xref:System.AttributeUsageAttribute> для настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9b56a-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="9b56a-118">**✓ DO** предоставляют настраиваемые свойства для необязательных аргументов.</span><span class="sxs-lookup"><span data-stu-id="9b56a-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="9b56a-119">**✓ DO** обеспечения обязательные аргументы свойства только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9b56a-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="9b56a-120">**✓ DO** предоставляют параметры конструктора для инициализации свойства, соответствующие обязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="9b56a-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="9b56a-121">Каждый параметр должен иметь имя, совпадающее (хотя и с разным регистром) как соответствующее свойство.</span><span class="sxs-lookup"><span data-stu-id="9b56a-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="9b56a-122">**X AVOID** указав аргументы конструктора для инициализации свойства, соответствующие необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="9b56a-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="9b56a-123">Другими словами не имеют свойств, которые можно передавать в конструктор и метод задания.</span><span class="sxs-lookup"><span data-stu-id="9b56a-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="9b56a-124">Это правило позволяет явным образом, какие аргументы являются необязательными, и которой являются обязательными и позволяет избежать необходимости два способа сделать то же самое.</span><span class="sxs-lookup"><span data-stu-id="9b56a-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="9b56a-125">**X AVOID** перегрузку конструкторов настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9b56a-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="9b56a-126">Явно наличие только один конструктор сообщает пользователю, какие аргументы являются обязательными, а какие — дополнительными.</span><span class="sxs-lookup"><span data-stu-id="9b56a-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="9b56a-127">**✓ DO** запечатать классы настраиваемых атрибутов, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="9b56a-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="9b56a-128">Это ускоряет поиск для атрибута.</span><span class="sxs-lookup"><span data-stu-id="9b56a-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="9b56a-129">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="9b56a-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9b56a-130">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9b56a-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b56a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9b56a-131">See also</span></span>

- [<span data-ttu-id="9b56a-132">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="9b56a-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="9b56a-133">Правила использования</span><span class="sxs-lookup"><span data-stu-id="9b56a-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
