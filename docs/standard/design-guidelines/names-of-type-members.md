---
title: "Имена членов типа"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d489d4cf61adfe8550bd16b85cd658e0d545c861
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-type-members"></a><span data-ttu-id="e0f71-102">Имена членов типа</span><span class="sxs-lookup"><span data-stu-id="e0f71-102">Names of Type Members</span></span>
<span data-ttu-id="e0f71-103">Типы состоят из элементов: методы, свойства, события, конструкторы и поля.</span><span class="sxs-lookup"><span data-stu-id="e0f71-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="e0f71-104">В следующих разделах описаны соглашения об именах членов типа.</span><span class="sxs-lookup"><span data-stu-id="e0f71-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="e0f71-105">Имена методов</span><span class="sxs-lookup"><span data-stu-id="e0f71-105">Names of Methods</span></span>  
 <span data-ttu-id="e0f71-106">Поскольку методы являются средствами, выполнив действия, согласно правилам разработки необходимо, имена методов глаголы или фразы команды.</span><span class="sxs-lookup"><span data-stu-id="e0f71-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="e0f71-107">Приведенных ниже рекомендаций также служит для различения имена методов и введите имен, которые являются фраз существительное или прилагательное.</span><span class="sxs-lookup"><span data-stu-id="e0f71-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="e0f71-108">**✓ СДЕЛАТЬ** глаголы или фразы глагол имен методов.</span><span class="sxs-lookup"><span data-stu-id="e0f71-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="e0f71-109">Имена свойств</span><span class="sxs-lookup"><span data-stu-id="e0f71-109">Names of Properties</span></span>  
 <span data-ttu-id="e0f71-110">В отличие от других членов свойства должны быть даны субстантивное словосочетание или прилагательных имена.</span><span class="sxs-lookup"><span data-stu-id="e0f71-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="e0f71-111">Это, так как свойство ссылается на данные и соответствует имени свойства.</span><span class="sxs-lookup"><span data-stu-id="e0f71-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="e0f71-112">PascalCasing всегда используется в именах свойств.</span><span class="sxs-lookup"><span data-stu-id="e0f71-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="e0f71-113">**✓ СДЕЛАТЬ** имя свойства с помощью существительное, субстантивное словосочетание или прилагательное.</span><span class="sxs-lookup"><span data-stu-id="e0f71-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="e0f71-114">**X не** имеют свойства, которые соответствуют имени методы «Get», как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e0f71-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="e0f71-115">Этот шаблон обычно означает, что свойства должен быть метод.</span><span class="sxs-lookup"><span data-stu-id="e0f71-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="e0f71-116">**✓ СДЕЛАТЬ** имя свойства коллекции с во множественном числе фразу, описывающие элементы в коллекции, вместо того чтобы использовать существительные фразу, за которым следует «Список» или «Коллекция».</span><span class="sxs-lookup"><span data-stu-id="e0f71-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="e0f71-117">**СДЕЛАТЬ ✓** именах логических свойств голосами фразы (`CanSeek` вместо `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="e0f71-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="e0f71-118">При необходимости задать префикс логических свойств с «Is», «может» или «Имеет,» но только в том случае, когда он добавляет значение.</span><span class="sxs-lookup"><span data-stu-id="e0f71-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="e0f71-119">**✓ Попробуйте** присваивать свойству совпадает с именем его тип.</span><span class="sxs-lookup"><span data-stu-id="e0f71-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="e0f71-120">Например, следующее свойство правильно возвращает и задает значение перечисления с именем `Color`, поэтому свойство называется `Color`:</span><span class="sxs-lookup"><span data-stu-id="e0f71-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="e0f71-121">Имена событий</span><span class="sxs-lookup"><span data-stu-id="e0f71-121">Names of Events</span></span>  
 <span data-ttu-id="e0f71-122">События всегда относятся к один ситуацию, или один возникшей какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="e0f71-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="e0f71-123">Таким образом как и для методов, событий именуются с командами и дать команда используется для указания времени, когда событие вызывается.</span><span class="sxs-lookup"><span data-stu-id="e0f71-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="e0f71-124">**✓ СДЕЛАТЬ** имя события с командой или командной фразой.</span><span class="sxs-lookup"><span data-stu-id="e0f71-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="e0f71-125">Примеры включают `Clicked`, `Painting`, `DroppedDown`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="e0f71-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="e0f71-126">**✓ СДЕЛАТЬ** Присвойте имена событий с понятием до и после, используя отсутствуют, а времен в прошлом.</span><span class="sxs-lookup"><span data-stu-id="e0f71-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="e0f71-127">Например, закрыть событие, которое возникает перед закрытием окна будет вызываться `Closing`, и может быть вызвана, возникает после закрытия окна `Closed`.</span><span class="sxs-lookup"><span data-stu-id="e0f71-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="e0f71-128">**X не** использовать «До» или «После» префиксы или postfixes для указания до и после события.</span><span class="sxs-lookup"><span data-stu-id="e0f71-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="e0f71-129">Использование присутствует и времен ранее, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="e0f71-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="e0f71-130">**✓ СДЕЛАТЬ** имя с суффиксом «EventHandler» обработчиков событий (делегатов, используемые в качестве типов событий), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e0f71-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="e0f71-131">**СДЕЛАТЬ ✓** используйте два параметра с именем `sender` и `e` в обработчиках событий.</span><span class="sxs-lookup"><span data-stu-id="e0f71-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="e0f71-132">Параметр sender представляет объект, создавший событие.</span><span class="sxs-lookup"><span data-stu-id="e0f71-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="e0f71-133">Параметр sender обычно имеет тип `object`, даже если можно применять к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="e0f71-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="e0f71-134">**✓ СДЕЛАТЬ** имя события, классы аргументов с суффиксом «EventArgs».</span><span class="sxs-lookup"><span data-stu-id="e0f71-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="e0f71-135">Имена полей</span><span class="sxs-lookup"><span data-stu-id="e0f71-135">Names of Fields</span></span>  
 <span data-ttu-id="e0f71-136">Статические поля открытые и защищенные применяются правила именования полей.</span><span class="sxs-lookup"><span data-stu-id="e0f71-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="e0f71-137">Внутренних и закрытых полей не затрагиваются в инструкции и открытый или защищенный экземпляр поля не допускаются [рекомендации по разработке членов](../../../docs/standard/design-guidelines/member.md).</span><span class="sxs-lookup"><span data-stu-id="e0f71-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="e0f71-138">**✓ СДЕЛАТЬ** использовать PascalCasing в именах полей.</span><span class="sxs-lookup"><span data-stu-id="e0f71-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="e0f71-139">**✓ СДЕЛАТЬ** имя поля, с помощью существительное, субстантивное словосочетание или прилагательное.</span><span class="sxs-lookup"><span data-stu-id="e0f71-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="e0f71-140">**X не** использовать префикс для имен полей.</span><span class="sxs-lookup"><span data-stu-id="e0f71-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="e0f71-141">Например не используйте «g_» или «s_» для указания статического поля.</span><span class="sxs-lookup"><span data-stu-id="e0f71-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="e0f71-142">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e0f71-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e0f71-143">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e0f71-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f71-144">См. также</span><span class="sxs-lookup"><span data-stu-id="e0f71-144">See Also</span></span>  
 [<span data-ttu-id="e0f71-145">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="e0f71-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="e0f71-146">Правила именования</span><span class="sxs-lookup"><span data-stu-id="e0f71-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
