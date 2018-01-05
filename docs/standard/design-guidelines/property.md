---
title: "Разработка свойств"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8f9c65dc6265daa793656177f066b97373f48ab8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="property-design"></a><span data-ttu-id="463f3-102">Разработка свойств</span><span class="sxs-lookup"><span data-stu-id="463f3-102">Property Design</span></span>
<span data-ttu-id="463f3-103">Несмотря на то, что свойства технически очень похожи на методы, между ними есть различия с точки зрения сценариев их использования.</span><span class="sxs-lookup"><span data-stu-id="463f3-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="463f3-104">Они должны рассматриваться как смарт-поля.</span><span class="sxs-lookup"><span data-stu-id="463f3-104">They should be seen as smart fields.</span></span> <span data-ttu-id="463f3-105">У них синтаксис вызова полей и гибкость методов.</span><span class="sxs-lookup"><span data-stu-id="463f3-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="463f3-106">**✓ СДЕЛАТЬ** Создание свойства только для чтения, если вызывающий объект не следует изменять значение свойства.</span><span class="sxs-lookup"><span data-stu-id="463f3-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="463f3-107">Следует помнить, что если тип свойства является изменяемым ссылочным типом, можно изменить значение свойства, даже если свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="463f3-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="463f3-108">**X не** предоставить только для набора свойств или свойств задания, имеющих широкий доступ, нежели метод считывания.</span><span class="sxs-lookup"><span data-stu-id="463f3-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="463f3-109">Например не используйте свойства с общедоступным методом задания и защищенный метод получения.</span><span class="sxs-lookup"><span data-stu-id="463f3-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="463f3-110">Если метод считывания свойства не может быть указан, следует Реализуйте функцию как метод.</span><span class="sxs-lookup"><span data-stu-id="463f3-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="463f3-111">Начните имя метода с `Set` и следом за то, что вы будет имя свойства.</span><span class="sxs-lookup"><span data-stu-id="463f3-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="463f3-112">Например <xref:System.AppDomain> содержит метод с именем `SetCachePath` вместо свойство только для набора с именем `CachePath`.</span><span class="sxs-lookup"><span data-stu-id="463f3-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="463f3-113">**✓ СДЕЛАТЬ** предоставить значения по умолчанию для всех свойств, убедившись, что значения по умолчанию не приводят к брешь в системе безопасности или совсем неэффективный код.</span><span class="sxs-lookup"><span data-stu-id="463f3-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="463f3-114">**✓ СДЕЛАТЬ** позволяют устанавливать в любом порядке, даже если это приводит к временной недопустимое состояние объекта свойства.</span><span class="sxs-lookup"><span data-stu-id="463f3-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="463f3-115">Чаще всего два или несколько свойств быть взаимосвязанных к точке, где некоторые значения одно свойство может быть неверным данных значений других свойств того же объекта.</span><span class="sxs-lookup"><span data-stu-id="463f3-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="463f3-116">В таких случаях исключения, возникающие в результате в недопустимом состоянии должны быть отложены, пока взаимосвязанных свойства фактически используются совместно в объекте.</span><span class="sxs-lookup"><span data-stu-id="463f3-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="463f3-117">**✓ СДЕЛАТЬ** сохраняют предыдущее значение, если метод задания свойства вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="463f3-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="463f3-118">**X ИЗБЕГАЙТЕ** исключения из методов получения свойства.</span><span class="sxs-lookup"><span data-stu-id="463f3-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="463f3-119">Методы получения свойств должны быть простыми операциями и не должны иметь каких-либо условий.</span><span class="sxs-lookup"><span data-stu-id="463f3-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="463f3-120">Если метод получения может создавать исключения, он, скорее всего, быть переработан методом.</span><span class="sxs-lookup"><span data-stu-id="463f3-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="463f3-121">Обратите внимание, что это правило не применяется к индексаторы, где ожидается, что исключения, в результате проверки аргументов.</span><span class="sxs-lookup"><span data-stu-id="463f3-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="463f3-122">Разработка индексированных свойств</span><span class="sxs-lookup"><span data-stu-id="463f3-122">Indexed Property Design</span></span>  
 <span data-ttu-id="463f3-123">Индексированное свойство является особым свойством, которое может иметь параметры и может быть вызван с помощью специального синтаксиса, аналогично индексации массива.</span><span class="sxs-lookup"><span data-stu-id="463f3-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="463f3-124">Индексированные свойства, часто называют индексаторов.</span><span class="sxs-lookup"><span data-stu-id="463f3-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="463f3-125">Индексаторы можно использовать только в API-интерфейсы, которые обеспечивают доступ к элементам это логическая коллекция.</span><span class="sxs-lookup"><span data-stu-id="463f3-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="463f3-126">Например, строка — это совокупность символы и указатель на <xref:System.String?displayProperty=nameWithType> был добавлен для доступа к его символов.</span><span class="sxs-lookup"><span data-stu-id="463f3-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="463f3-127">**✓ Попробуйте** использовать индексаторы для предоставления доступа к данным, хранящимся во внутреннем массиве.</span><span class="sxs-lookup"><span data-stu-id="463f3-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="463f3-128">**✓ Попробуйте** обеспечить индексаторы для типов, представляющих коллекции элементов.</span><span class="sxs-lookup"><span data-stu-id="463f3-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="463f3-129">**X ИЗБЕГАЙТЕ** использование индексированных свойств с более чем одним параметром.</span><span class="sxs-lookup"><span data-stu-id="463f3-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="463f3-130">Если в программе требуется несколько параметров, пересмотрите ли свойство в действительности является методом доступа к логической коллекции.</span><span class="sxs-lookup"><span data-stu-id="463f3-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="463f3-131">В этом случае не следует используйте методы.</span><span class="sxs-lookup"><span data-stu-id="463f3-131">If it does not, use methods instead.</span></span> <span data-ttu-id="463f3-132">Начните имя метода с `Get` или `Set`.</span><span class="sxs-lookup"><span data-stu-id="463f3-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="463f3-133">**X ИЗБЕГАЙТЕ** индексаторы с типами параметров, отличных от <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, или перечисления.</span><span class="sxs-lookup"><span data-stu-id="463f3-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="463f3-134">Если для разработки требуются другие типы параметров, проверьте ли API в действительности является методом доступа к логической коллекции.</span><span class="sxs-lookup"><span data-stu-id="463f3-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="463f3-135">Если этого не произошло, используйте метод.</span><span class="sxs-lookup"><span data-stu-id="463f3-135">If it does not, use a method.</span></span> <span data-ttu-id="463f3-136">Начните имя метода с `Get` или `Set`.</span><span class="sxs-lookup"><span data-stu-id="463f3-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="463f3-137">**✓ ВЫПОЛНИТЕ** используйте имя `Item` для индексированных свойств при отсутствии очевидно, что более понятные имена (например, см. <xref:System.String.Chars%2A> свойство `System.String`).</span><span class="sxs-lookup"><span data-stu-id="463f3-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="463f3-138">В C# Индексаторы доступны по умолчанию имя элемента.</span><span class="sxs-lookup"><span data-stu-id="463f3-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="463f3-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute> Можно использовать для настройки этого имени.</span><span class="sxs-lookup"><span data-stu-id="463f3-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="463f3-140">**X не** предоставляют индексатор и методы, которые семантически эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="463f3-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="463f3-141">**X не** предоставляют более одного семейства перегруженных индексаторов в одном типе.</span><span class="sxs-lookup"><span data-stu-id="463f3-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="463f3-142">Это требование с помощью компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="463f3-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="463f3-143">**X не** нестандартное использование индексированных свойств.</span><span class="sxs-lookup"><span data-stu-id="463f3-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="463f3-144">Это требование с помощью компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="463f3-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="463f3-145">События уведомления об изменении свойства</span><span class="sxs-lookup"><span data-stu-id="463f3-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="463f3-146">Иногда полезно создать событие уведомления пользователя об изменениях значения свойства.</span><span class="sxs-lookup"><span data-stu-id="463f3-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="463f3-147">Например `System.Windows.Forms.Control` вызывает `TextChanged` событий после изменения значения его `Text` измененное свойство.</span><span class="sxs-lookup"><span data-stu-id="463f3-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="463f3-148">**✓ Попробуйте** вызов изменения события уведомления при изменении значений свойств в API высокого уровня (обычно компонентов конструктора).</span><span class="sxs-lookup"><span data-stu-id="463f3-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="463f3-149">Если хорошо сценарий для пользователю возможность узнать, при изменении свойства объекта, объект должен вызывать событие уведомления об изменении свойства.</span><span class="sxs-lookup"><span data-stu-id="463f3-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="463f3-150">Однако это правило, не стоит издержки для создания таких событий для низкоуровневого API, например базовых типов или коллекций.</span><span class="sxs-lookup"><span data-stu-id="463f3-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="463f3-151">Например <xref:System.Collections.Generic.List%601> не приведет к возникновению таких событий, когда элемент добавляется в список и `Count` изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="463f3-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="463f3-152">**✓ Попробуйте** вызов изменения события уведомления при изменении значения свойства через внешних событий.</span><span class="sxs-lookup"><span data-stu-id="463f3-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="463f3-153">При изменении значения свойства через некоторые внешние force (таким образом, отличных от путем вызова методов в объекте), создает события указывают разработчику, что значение изменяется и был изменен.</span><span class="sxs-lookup"><span data-stu-id="463f3-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="463f3-154">Хорошим примером является `Text` свойство элемента управления текстового поля.</span><span class="sxs-lookup"><span data-stu-id="463f3-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="463f3-155">Когда пользователь вводит текст в `TextBox`, автоматически изменяет значение свойства.</span><span class="sxs-lookup"><span data-stu-id="463f3-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="463f3-156">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="463f3-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="463f3-157">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="463f3-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="463f3-158">См. также</span><span class="sxs-lookup"><span data-stu-id="463f3-158">See Also</span></span>  
 [<span data-ttu-id="463f3-159">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="463f3-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="463f3-160">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="463f3-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
