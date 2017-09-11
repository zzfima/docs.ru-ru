---
title: "event (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="event-c-reference"></a><span data-ttu-id="ce95b-102">event (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ce95b-102">event (C# Reference)</span></span>
<span data-ttu-id="ce95b-103">Ключевое слово `event` используется для объявления события в классе Publisher.</span><span class="sxs-lookup"><span data-stu-id="ce95b-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce95b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ce95b-104">Example</span></span>  
 <span data-ttu-id="ce95b-105">Следующий пример демонстрирует объявление и вызов события, которое использует <xref:System.EventHandler> как базовый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="ce95b-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="ce95b-106">Полный пример кода, демонстрирующий использование универсального типа делегата <xref:System.EventHandler%601>, создание подписки на событие и создание метода обработчика событий, см. в разделе [Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 <span data-ttu-id="ce95b-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ce95b-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span></span>  
  
 <span data-ttu-id="ce95b-108">События представляют собой специальный вид многоадресного делегата, который можно вызвать только из класса или структуры, в которых он объявлен (класс Publisher).</span><span class="sxs-lookup"><span data-stu-id="ce95b-108">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="ce95b-109">Если другие классы или структуры подписываются на событие, их методы обработчиков событий будут вызываться, когда класс Publisher будет вызывать событие.</span><span class="sxs-lookup"><span data-stu-id="ce95b-109">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="ce95b-110">Дополнительные сведения и примеры кода см. в разделах [События](../../../csharp/programming-guide/events/index.md) и [Делегаты](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-110">For more information and code examples, see [Events](../../../csharp/programming-guide/events/index.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="ce95b-111">События могут иметь пометку [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md) и [internal](../../../csharp/language-reference/keywords/internal.md) или `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="ce95b-111">Events can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="ce95b-112">Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к событию.</span><span class="sxs-lookup"><span data-stu-id="ce95b-112">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="ce95b-113">Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-113">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="ce95b-114">Ключевые слова и события</span><span class="sxs-lookup"><span data-stu-id="ce95b-114">Keywords and Events</span></span>  
 <span data-ttu-id="ce95b-115">Следующие ключевые слова применяются к событиям.</span><span class="sxs-lookup"><span data-stu-id="ce95b-115">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="ce95b-116">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="ce95b-116">Keyword</span></span>|<span data-ttu-id="ce95b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ce95b-117">Description</span></span>|<span data-ttu-id="ce95b-118">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ce95b-118">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="ce95b-119">static</span><span class="sxs-lookup"><span data-stu-id="ce95b-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="ce95b-120">Делает событие доступным для вызывающих объектов в любое время, даже если экземпляр класса не существует.</span><span class="sxs-lookup"><span data-stu-id="ce95b-120">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="ce95b-121">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="ce95b-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="ce95b-122">virtual</span><span class="sxs-lookup"><span data-stu-id="ce95b-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="ce95b-123">Позволяет производным классам переопределять поведение события с помощью ключевого слова [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-123">Allows derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span>|[<span data-ttu-id="ce95b-124">Наследование</span><span class="sxs-lookup"><span data-stu-id="ce95b-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="ce95b-125">sealed</span><span class="sxs-lookup"><span data-stu-id="ce95b-125">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="ce95b-126">Указывает, что для производных классов оно больше не является виртуальным.</span><span class="sxs-lookup"><span data-stu-id="ce95b-126">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="ce95b-127">abstract</span><span class="sxs-lookup"><span data-stu-id="ce95b-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="ce95b-128">Компилятор не будет создавать блоки доступа к событиям `add` и `remove`, и поэтому производные классы должны предоставлять собственную реализацию.</span><span class="sxs-lookup"><span data-stu-id="ce95b-128">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="ce95b-129">Событие может быть объявлено как статическое событие с помощью ключевого слова [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-129">An event may be declared as a static event by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="ce95b-130">Это делает событие доступным для вызывающих объектов в любое время, даже если экземпляр класса не существует.</span><span class="sxs-lookup"><span data-stu-id="ce95b-130">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="ce95b-131">Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-131">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="ce95b-132">Событие может быть помечено как виртуальное событие с помощью ключевого слова [virtual](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-132">An event can be marked as a virtual event by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="ce95b-133">Это позволяет производным классам переопределять поведение события с помощью ключевого слова [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-133">This enables derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="ce95b-134">Дополнительные сведения см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-134">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="ce95b-135">Событие, переопределяющее виртуальное событие, также может быть запечатанным ([sealed](../../../csharp/language-reference/keywords/sealed.md)), что указывает, что для производных классов оно больше не является виртуальным.</span><span class="sxs-lookup"><span data-stu-id="ce95b-135">An event overriding a virtual event can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="ce95b-136">И наконец, можно объявить событие абстрактным ([abstract](../../../csharp/language-reference/keywords/abstract.md)), что означает, что компилятор не будет создавать блоки доступа к событиям `add` и `remove`.</span><span class="sxs-lookup"><span data-stu-id="ce95b-136">Lastly, an event can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="ce95b-137">Поэтому производные классы должны предоставлять собственную реализацию.</span><span class="sxs-lookup"><span data-stu-id="ce95b-137">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ce95b-138">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ce95b-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce95b-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ce95b-139">See Also</span></span>  
 <span data-ttu-id="ce95b-140">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce95b-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ce95b-141">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce95b-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ce95b-142">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce95b-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ce95b-143">[add](../../../csharp/language-reference/keywords/add.md) </span><span class="sxs-lookup"><span data-stu-id="ce95b-143">[add](../../../csharp/language-reference/keywords/add.md) </span></span>  
 <span data-ttu-id="ce95b-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span><span class="sxs-lookup"><span data-stu-id="ce95b-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span></span>  
 <span data-ttu-id="ce95b-145">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="ce95b-145">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="ce95b-146">Практическое руководство. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="ce95b-146">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

