---
title: Руководство по программированию на C#. Использование индексаторов
ms.date: 10/03/2018
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: 17162a0dc959a85c03a5cb5757e2b91fe10b0ab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628167"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="cbef8-102">Использование индексаторов. Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cbef8-102">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="cbef8-103">Применение индексаторов упрощает работу с синтаксисом, позволяя создавать [классы](../../language-reference/keywords/class.md), [структуры](../../language-reference/builtin-types/struct.md) и [интерфейсы](../../language-reference/keywords/interface.md), к которым клиентские приложения могут обращаться так же, как к массиву.</span><span class="sxs-lookup"><span data-stu-id="cbef8-103">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access just as an array.</span></span> <span data-ttu-id="cbef8-104">Индексаторы чаще всего реализуются в типах, предназначенных преимущественно для инкапсуляции внутренней коллекции или массива.</span><span class="sxs-lookup"><span data-stu-id="cbef8-104">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="cbef8-105">Допустим, у вас есть класс `TempRecord`, представляющий журнал с 10 измерениями температуры по шкале Фаренгейта за период в 24 часа.</span><span class="sxs-lookup"><span data-stu-id="cbef8-105">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24 hour period.</span></span> <span data-ttu-id="cbef8-106">Этот класс содержит массив `temps` типа `float[]` для хранения значений температуры.</span><span class="sxs-lookup"><span data-stu-id="cbef8-106">The class contains an array `temps` of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="cbef8-107">Реализация индексатора в этом классе позволит клиентам получать доступ к значениям температуры в экземпляре `TempRecord`, используя `float temp = tr[4]` вместо `float temp = tr.temps[4]`.</span><span class="sxs-lookup"><span data-stu-id="cbef8-107">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tr[4]` instead of as `float temp = tr.temps[4]`.</span></span> <span data-ttu-id="cbef8-108">Это позволяет не только упростить синтаксис клиентских приложений, но и облегчить понимание кода класса и его предназначения другими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="cbef8-108">The indexer notation not only simplifies the syntax for client applications; it also makes the class and its purpose more intuitive for other developers to understand.</span></span>  
  
<span data-ttu-id="cbef8-109">Чтобы объявить индексатор для класса или структуры, используйте ключевое слово [this](../../language-reference/keywords/this.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cbef8-109">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```

## <a name="remarks"></a><span data-ttu-id="cbef8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbef8-110">Remarks</span></span>

<span data-ttu-id="cbef8-111">Тип индексатора и типы его параметров должны иметь по крайней мере такой же уровень доступности, как и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="cbef8-111">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="cbef8-112">Дополнительные сведения об уровнях доступа см. в разделе [Модификаторы доступа](../../language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cbef8-112">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="cbef8-113">Дополнительные сведения об использовании индексаторов с интерфейсом см. в разделе [Индексаторы интерфейса](./indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="cbef8-113">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>  
  
 <span data-ttu-id="cbef8-114">Сигнатура индексатора определяет число и типы его формальных параметров.</span><span class="sxs-lookup"><span data-stu-id="cbef8-114">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="cbef8-115">В ней не указываются тип индексатора или имена его формальных параметров.</span><span class="sxs-lookup"><span data-stu-id="cbef8-115">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="cbef8-116">Если для одного класса объявляется несколько индексаторов, они должны иметь разные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="cbef8-116">If you declare more than one indexer in the same class, they must have different signatures.</span></span>  
  
 <span data-ttu-id="cbef8-117">Значение индексатора не классифицируется как переменная и, соответственно, не может передаваться в качестве параметра [ref](../../language-reference/keywords/ref.md) или [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="cbef8-117">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>  
  
 <span data-ttu-id="cbef8-118">Чтобы присвоить индексатору имя, которое можно использовать в других языках, используйте <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="cbef8-118">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>  

```csharp
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this[int index]   // Indexer declaration  
{
    // get and set accessors  
}  
```

<span data-ttu-id="cbef8-119">Этот индексатор будет иметь имя `TheItem`.</span><span class="sxs-lookup"><span data-stu-id="cbef8-119">This indexer will have the name `TheItem`.</span></span> <span data-ttu-id="cbef8-120">Без атрибута имени по умолчанию будет использоваться имя `Item`.</span><span class="sxs-lookup"><span data-stu-id="cbef8-120">Not providing the name attribute would make `Item` the default name.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="cbef8-121">Пример 1</span><span class="sxs-lookup"><span data-stu-id="cbef8-121">Example 1</span></span>  
  
<span data-ttu-id="cbef8-122">В следующем примере показано, как объявить частное поле массива `temps` и индексатор.</span><span class="sxs-lookup"><span data-stu-id="cbef8-122">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="cbef8-123">Индексатор обеспечивает прямой доступ к экземпляру `tempRecord[i]`.</span><span class="sxs-lookup"><span data-stu-id="cbef8-123">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="cbef8-124">Вместо использования индексатора можно объявить массив как элемент [public](../../language-reference/keywords/public.md) и осуществлять доступ к его элементам напрямую (`tempRecord.temps[i]`).</span><span class="sxs-lookup"><span data-stu-id="cbef8-124">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>  
  
 <span data-ttu-id="cbef8-125">Обратите внимание, что при определении прав доступа индексатора, например в инструкции `Console.Write`, вызывается метод доступа [get](../../language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="cbef8-125">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="cbef8-126">Таким образом, если метод доступа `get` отсутствует, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="cbef8-126">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#1)]  
  
## <a name="indexing-using-other-values"></a><span data-ttu-id="cbef8-127">Индексирование с использованием других значений</span><span class="sxs-lookup"><span data-stu-id="cbef8-127">Indexing using other values</span></span>

<span data-ttu-id="cbef8-128">В C# тип параметра индексатора не ограничивается целочисленными значениями.</span><span class="sxs-lookup"><span data-stu-id="cbef8-128">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="cbef8-129">Например, в качестве индексатора могут использоваться строки.</span><span class="sxs-lookup"><span data-stu-id="cbef8-129">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="cbef8-130">Такой индексатор можно реализовать путем поиска строки в коллекции с возвратом соответствующего значения.</span><span class="sxs-lookup"><span data-stu-id="cbef8-130">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="cbef8-131">Поскольку методы доступа можно перегружать, строковые и целочисленные версии могут сосуществовать.</span><span class="sxs-lookup"><span data-stu-id="cbef8-131">As accessors can be overloaded, the string and integer versions can co-exist.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="cbef8-132">Пример 2</span><span class="sxs-lookup"><span data-stu-id="cbef8-132">Example 2</span></span>  
  
<span data-ttu-id="cbef8-133">Этот пример объявляет класс, который хранит названия дней недели.</span><span class="sxs-lookup"><span data-stu-id="cbef8-133">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="cbef8-134">Метод доступа `get` принимает название дня в виде строкового значения и возвращает соответствующее целое число.</span><span class="sxs-lookup"><span data-stu-id="cbef8-134">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="cbef8-135">Например, для Sunday возвращается значение 0, для Monday — 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="cbef8-135">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="cbef8-136">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="cbef8-136">Robust programming</span></span>

 <span data-ttu-id="cbef8-137">Повысить безопасность и надежность индексаторов можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="cbef8-137">There are two main ways in which the security and reliability of indexers can be improved:</span></span>  
  
- <span data-ttu-id="cbef8-138">Реализуйте стратегию обработки ошибок, предусматривающую действия в ситуациях, когда из клиентского кода передается недопустимое значение индекса.</span><span class="sxs-lookup"><span data-stu-id="cbef8-138">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="cbef8-139">В первом примере из этого раздела класс TempRecord содержит свойство Length, с помощью которого клиентский код проверяет введенное значение, прежде чем передать его в индексатор.</span><span class="sxs-lookup"><span data-stu-id="cbef8-139">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="cbef8-140">Кроме того, код обработки ошибок можно поместить в сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="cbef8-140">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="cbef8-141">Не забудьте задокументировать исключения, которые будут вызываться в методе доступа индексатора, для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="cbef8-141">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>  
  
- <span data-ttu-id="cbef8-142">Настройте максимально ограничивающие уровни доступа для методов доступа [get](../../language-reference/keywords/get.md) и [set](../../language-reference/keywords/set.md).</span><span class="sxs-lookup"><span data-stu-id="cbef8-142">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="cbef8-143">Особенно важно сделать это для метода доступа `set`.</span><span class="sxs-lookup"><span data-stu-id="cbef8-143">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="cbef8-144">Дополнительные сведения см. в разделе [Доступность методов доступа](../classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="cbef8-144">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbef8-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cbef8-145">See also</span></span>

- [<span data-ttu-id="cbef8-146">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cbef8-146">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cbef8-147">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="cbef8-147">Indexers</span></span>](./index.md)
- [<span data-ttu-id="cbef8-148">Свойства</span><span class="sxs-lookup"><span data-stu-id="cbef8-148">Properties</span></span>](../classes-and-structs/properties.md)
