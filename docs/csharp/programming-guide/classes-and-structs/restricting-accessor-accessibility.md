---
title: "Ограничение доступности методов доступа (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accesibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: 26
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
ms.openlocfilehash: 347fffa4f612c5cb674a6529e46c0b1785670c95
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="eb119-102">Ограничение доступности методов доступа (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="eb119-102">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="eb119-103">Выражения [get](../../../csharp/language-reference/keywords/get.md) и [set](../../../csharp/language-reference/keywords/set.md) свойства или индексатора называются *методами доступа*.</span><span class="sxs-lookup"><span data-stu-id="eb119-103">The [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="eb119-104">По умолчанию они имеют такие же уровни видимости или доступа, что и свойство или индексатор, которым они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="eb119-104">By default these accessors have the same visibility, or access level: that of the property or indexer to which they belong.</span></span> <span data-ttu-id="eb119-105">Дополнительные сведения см. в разделе [Уровни доступа](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="eb119-105">For more information, see [accessibility levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="eb119-106">Тем не менее в некоторых случаях рекомендуется ограничить уровни доступа для этих методов.</span><span class="sxs-lookup"><span data-stu-id="eb119-106">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="eb119-107">Как правило, в этом случае ограничивается уровень доступа для метода `set`, тогда как метод `get` остается общедоступным.</span><span class="sxs-lookup"><span data-stu-id="eb119-107">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="eb119-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="eb119-108">For example:</span></span>  
  
 <span data-ttu-id="eb119-109">[!code-cs[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb119-109">[!code-cs[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]</span></span>  
  
 <span data-ttu-id="eb119-110">В этом примере свойство `Name` определяет методы доступа `get` и `set`.</span><span class="sxs-lookup"><span data-stu-id="eb119-110">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="eb119-111">Метод доступа `get` получает уровень доступа самого свойства (в этом случае `public`), а к методу `set` явным образом применяется модификатор доступа [protected](../../../csharp/language-reference/keywords/protected.md).</span><span class="sxs-lookup"><span data-stu-id="eb119-111">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../../csharp/language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="eb119-112">Ограничения модификаторов доступа для методов доступа</span><span class="sxs-lookup"><span data-stu-id="eb119-112">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="eb119-113">При использовании модификаторов доступа для свойств или индексаторов необходимо соблюдать следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="eb119-113">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
-   <span data-ttu-id="eb119-114">Модификаторы доступа нельзя использовать в интерфейсе или явной реализации элемента [interface](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="eb119-114">You cannot use accessor modifiers on an interface or an explicit [interface](../../../csharp/language-reference/keywords/interface.md) member implementation.</span></span>  
  
-   <span data-ttu-id="eb119-115">Модификаторы доступа можно использовать только в том случае, если для свойства или индексатора определены одновременно методы доступа `set` и `get`.</span><span class="sxs-lookup"><span data-stu-id="eb119-115">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="eb119-116">В этом случае модификатор может применяться только к одному из двух методов доступа.</span><span class="sxs-lookup"><span data-stu-id="eb119-116">In this case, the modifier is permitted on one only of the two accessors.</span></span>  
  
-   <span data-ttu-id="eb119-117">Если свойству или индексатору назначен модификатор [override](../../../csharp/language-reference/keywords/override.md), модификатор доступа должен соответствовать методу доступа для переопределенного метода доступа, если такой существует.</span><span class="sxs-lookup"><span data-stu-id="eb119-117">If the property or indexer has an [override](../../../csharp/language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
-   <span data-ttu-id="eb119-118">Уровень доступности для метода доступа должен быть более строгим по сравнению с уровнем доступа самого свойства или идентификатора.</span><span class="sxs-lookup"><span data-stu-id="eb119-118">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="eb119-119">Модификаторы доступа при переопределении методов доступа</span><span class="sxs-lookup"><span data-stu-id="eb119-119">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="eb119-120">При переопределении свойства или индексатора переопределенные методы доступа должны быть доступны коду переопределения.</span><span class="sxs-lookup"><span data-stu-id="eb119-120">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="eb119-121">Кроме того, уровни доступа свойства/индексатора и соответствующих методов доступа должны совпадать с уровнями переопределенных свойства/индексатора и методов доступа.</span><span class="sxs-lookup"><span data-stu-id="eb119-121">Also, the accessibility level of both the property/indexer, and that of the accessors must match the corresponding overridden property/indexer and the accessors.</span></span> <span data-ttu-id="eb119-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="eb119-122">For example:</span></span>  
  
 <span data-ttu-id="eb119-123">[!code-cs[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb119-123">[!code-cs[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]</span></span>  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="eb119-124">Реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="eb119-124">Implementing Interfaces</span></span>  
 <span data-ttu-id="eb119-125">Методы доступа, которые используются для реализации интерфейса, не могут иметь модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="eb119-125">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="eb119-126">Тем не менее при реализации интерфейса с использованием одного метода доступа (например, `get`) другой метод доступа может иметь модификатор доступа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="eb119-126">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 <span data-ttu-id="eb119-127">[!code-cs[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb119-127">[!code-cs[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]</span></span>  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="eb119-128">Домен доступности для метода доступа</span><span class="sxs-lookup"><span data-stu-id="eb119-128">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="eb119-129">При использовании модификатора доступа для метода доступа этот модификатор определяет [домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md) для такого метода.</span><span class="sxs-lookup"><span data-stu-id="eb119-129">If you use an access modifier on the accessor, the [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="eb119-130">Если к методу доступа не применяется модификатор доступа, домен доступности этого метода определяется уровнем доступности свойства или индексатора.</span><span class="sxs-lookup"><span data-stu-id="eb119-130">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb119-131">Пример</span><span class="sxs-lookup"><span data-stu-id="eb119-131">Example</span></span>  
 <span data-ttu-id="eb119-132">В следующем примере определяются три класса: `BaseClass`, `DerivedClass` и `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="eb119-132">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="eb119-133">В классе `BaseClass` для обоих классов определены свойства `Name` и `Id`.</span><span class="sxs-lookup"><span data-stu-id="eb119-133">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="eb119-134">В этом примере демонстрируется, как свойство `Id` класса `DerivedClass` может быть скрыто свойством `Id` класса `BaseClass` при использовании ограничивающего модификатора доступа, такого как [protected](../../../csharp/language-reference/keywords/protected.md) или [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="eb119-134">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../../csharp/language-reference/keywords/protected.md) or [private](../../../csharp/language-reference/keywords/private.md).</span></span> <span data-ttu-id="eb119-135">Таким образом, при присвоении значений этому свойству вместо него вызывается свойство класса `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="eb119-135">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="eb119-136">Чтобы сделать это свойство доступным, необходимо заменить модификатор доступа на [public](../../../csharp/language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="eb119-136">Replacing the access modifier by [public](../../../csharp/language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="eb119-137">В этом примере также демонстрируется, что ограничивающий модификатор доступа (`private` или `protected`) для метода доступа `set` свойства `Name` в классе `DerivedClass` запрещает доступ к этому методу и при попытке присвоить ему значение возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="eb119-137">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 <span data-ttu-id="eb119-138">[!code-cs[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb119-138">[!code-cs[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="eb119-139">Комментарии</span><span class="sxs-lookup"><span data-stu-id="eb119-139">Comments</span></span>  
 <span data-ttu-id="eb119-140">Обратите внимание, что если заменить объявление `new private string Id` на `new public string Id`, будут получены следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="eb119-140">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="eb119-141">См. также</span><span class="sxs-lookup"><span data-stu-id="eb119-141">See Also</span></span>  
 <span data-ttu-id="eb119-142">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb119-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="eb119-143">[Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="eb119-143">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="eb119-144">[Индексаторы](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb119-144">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="eb119-145">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="eb119-145">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)

