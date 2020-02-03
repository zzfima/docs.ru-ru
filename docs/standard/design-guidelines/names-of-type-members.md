---
title: Имена членов типа
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: 81c837bd045992043208a59f6ee16803c1d6eb3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744178"
---
# <a name="names-of-type-members"></a><span data-ttu-id="aded4-102">Имена членов типа</span><span class="sxs-lookup"><span data-stu-id="aded4-102">Names of Type Members</span></span>
<span data-ttu-id="aded4-103">Типы состоят из элементов: методов, свойств, событий, конструкторов и полей.</span><span class="sxs-lookup"><span data-stu-id="aded4-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="aded4-104">В следующих разделах приведены рекомендации по именованию элементов типа.</span><span class="sxs-lookup"><span data-stu-id="aded4-104">The following sections describe guidelines for naming type members.</span></span>

## <a name="names-of-methods"></a><span data-ttu-id="aded4-105">Имена методов</span><span class="sxs-lookup"><span data-stu-id="aded4-105">Names of Methods</span></span>
 <span data-ttu-id="aded4-106">Так как методы служат для выполнения действий, при разработке рекомендуется задавать их имена глаголами или глагольными фразами.</span><span class="sxs-lookup"><span data-stu-id="aded4-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="aded4-107">Следование этой рекомендации также помогает отличать имена методов от имен типов и свойств, использующих фразы, где главное слово — существительное или прилагательное.</span><span class="sxs-lookup"><span data-stu-id="aded4-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>

 <span data-ttu-id="aded4-108">✔️ предоставляют имена методов, которые являются глаголами или фразами глаголов.</span><span class="sxs-lookup"><span data-stu-id="aded4-108">✔️ DO give methods names that are verbs or verb phrases.</span></span>

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a><span data-ttu-id="aded4-109">Имена свойств</span><span class="sxs-lookup"><span data-stu-id="aded4-109">Names of Properties</span></span>
 <span data-ttu-id="aded4-110">В отличие от других элементов, свойства должны иметь имена в виде фраз на основе существительного или прилагательных.</span><span class="sxs-lookup"><span data-stu-id="aded4-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="aded4-111">Причина в том, что свойство ссылается на данные, и это должно быть отражено в его имени.</span><span class="sxs-lookup"><span data-stu-id="aded4-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="aded4-112">В именах свойств всегда используется PascalCase.</span><span class="sxs-lookup"><span data-stu-id="aded4-112">PascalCasing is always used for property names.</span></span>

 <span data-ttu-id="aded4-113">✔️ имена свойств, используя существительное, фразу существительное или прилагательную.</span><span class="sxs-lookup"><span data-stu-id="aded4-113">✔️ DO name properties using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="aded4-114">❌ не имеют свойств, соответствующих именам методов Get, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="aded4-114">❌ DO NOT have properties that match the name of "Get" methods as in the following example:</span></span>

 <span data-ttu-id="aded4-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span><span class="sxs-lookup"><span data-stu-id="aded4-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span></span>

 <span data-ttu-id="aded4-116">Обычно это означает, что свойство целесообразно сделать методом.</span><span class="sxs-lookup"><span data-stu-id="aded4-116">This pattern typically indicates that the property should really be a method.</span></span>

 <span data-ttu-id="aded4-117">✔️ свойства коллекции имен со множественной фразой, описывающей элементы в коллекции, вместо использования единственной фразы, за которой следует "List" или "Collection".</span><span class="sxs-lookup"><span data-stu-id="aded4-117">✔️ DO name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>

 <span data-ttu-id="aded4-118">✔️ имена логических свойств с помощью фразы голосами подтверждающими (`CanSeek` вместо `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="aded4-118">✔️ DO name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="aded4-119">При необходимости можно также добавить префиксы логических свойств с помощью "-", "Can" или "with", но только там, где он добавляет значение.</span><span class="sxs-lookup"><span data-stu-id="aded4-119">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>

 <span data-ttu-id="aded4-120">✔️ Рассмотрите возможность присвоения свойству того же имени, что и его тип.</span><span class="sxs-lookup"><span data-stu-id="aded4-120">✔️ CONSIDER giving a property the same name as its type.</span></span>

 <span data-ttu-id="aded4-121">Например, следующее свойство должным образом получает и задает значение перечисления с именем `Color`, поэтому свойство имеет имя `Color`:</span><span class="sxs-lookup"><span data-stu-id="aded4-121">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a><span data-ttu-id="aded4-122">Имена событий</span><span class="sxs-lookup"><span data-stu-id="aded4-122">Names of Events</span></span>
 <span data-ttu-id="aded4-123">События всегда ссылаются на какое-то действие, которое происходит или уже произошло.</span><span class="sxs-lookup"><span data-stu-id="aded4-123">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="aded4-124">Следовательно, события, как и методы, следует называть с помощью глаголов, а время глагола (настоящее или прошедшее) будет указывать на время возникновения события.</span><span class="sxs-lookup"><span data-stu-id="aded4-124">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>

 <span data-ttu-id="aded4-125">✔️ события имени с помощью глагола или фразы глагола.</span><span class="sxs-lookup"><span data-stu-id="aded4-125">✔️ DO name events with a verb or a verb phrase.</span></span>

 <span data-ttu-id="aded4-126">Примеры: `Clicked`, `Painting`, `DroppedDown` и т. д.</span><span class="sxs-lookup"><span data-stu-id="aded4-126">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>

 <span data-ttu-id="aded4-127">✔️ присвоить имена событиям концепцию до и после, используя текущее и прошедшее время.</span><span class="sxs-lookup"><span data-stu-id="aded4-127">✔️ DO give events names with a concept of before and after, using the present and past tenses.</span></span>

 <span data-ttu-id="aded4-128">Например, событие закрытия, которое происходит перед закрытием окна, может называться `Closing`, а которое после — `Closed`.</span><span class="sxs-lookup"><span data-stu-id="aded4-128">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>

 <span data-ttu-id="aded4-129">❌ не используйте префиксы "до" и "после", чтобы указать события до и после событий.</span><span class="sxs-lookup"><span data-stu-id="aded4-129">❌ DO NOT use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="aded4-130">Используйте настоящее и прошедшее время, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="aded4-130">Use present and past tenses as just described.</span></span>

 <span data-ttu-id="aded4-131">✔️ имена обработчиков событий (делегатов, используемых в качестве типов событий) с суффиксом EventHandler, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="aded4-131">✔️ DO name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 <span data-ttu-id="aded4-132">✔️ использовать два параметра с именами `sender` и `e` в обработчиках событий.</span><span class="sxs-lookup"><span data-stu-id="aded4-132">✔️ DO use two parameters named `sender` and `e` in event handlers.</span></span>

 <span data-ttu-id="aded4-133">Параметр sender обозначает объект, который вызвал событие.</span><span class="sxs-lookup"><span data-stu-id="aded4-133">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="aded4-134">Этот параметр обычно имеет тип `object`, даже если можно использовать более конкретный тип.</span><span class="sxs-lookup"><span data-stu-id="aded4-134">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>

 <span data-ttu-id="aded4-135">✔️ имена классов аргументов событий с суффиксом "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="aded4-135">✔️ DO name event argument classes with the "EventArgs" suffix.</span></span>

## <a name="names-of-fields"></a><span data-ttu-id="aded4-136">Имена полей</span><span class="sxs-lookup"><span data-stu-id="aded4-136">Names of Fields</span></span>
 <span data-ttu-id="aded4-137">Рекомендации по именованию полей относятся к статическим открытым и защищенным полям.</span><span class="sxs-lookup"><span data-stu-id="aded4-137">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="aded4-138">Рекомендации не охватывают внутренние и закрытые поля, а использование открытых полей или полей защищенных экземпляров запрещено [правилами разработки элементов](../../../docs/standard/design-guidelines/member.md).</span><span class="sxs-lookup"><span data-stu-id="aded4-138">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>

 <span data-ttu-id="aded4-139">✔️ использовать Паскалкасинг в именах полей.</span><span class="sxs-lookup"><span data-stu-id="aded4-139">✔️ DO use PascalCasing in field names.</span></span>

 <span data-ttu-id="aded4-140">✔️ поля имени с помощью существительного, фразы существительное или прилагательные.</span><span class="sxs-lookup"><span data-stu-id="aded4-140">✔️ DO name fields using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="aded4-141">❌ не используйте префикс для имен полей.</span><span class="sxs-lookup"><span data-stu-id="aded4-141">❌ DO NOT use a prefix for field names.</span></span>

 <span data-ttu-id="aded4-142">Например, не используйте "g_" или "s_" для указания, что поле является статическим.</span><span class="sxs-lookup"><span data-stu-id="aded4-142">For example, do not use "g_" or "s_" to indicate static fields.</span></span>

 <span data-ttu-id="aded4-143">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="aded4-143">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="aded4-144">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="aded4-144">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="aded4-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aded4-145">See also</span></span>

- [<span data-ttu-id="aded4-146">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="aded4-146">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="aded4-147">Правила именования</span><span class="sxs-lookup"><span data-stu-id="aded4-147">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
