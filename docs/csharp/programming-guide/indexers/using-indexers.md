---
title: "Использование индексаторов (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
caps.latest.revision: 30
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
ms.openlocfilehash: ac8990fa2efb1a2ea24497a3a5de3649795c7b23
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="cd3c9-102">Использование индексаторов (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="cd3c9-102">Using Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="cd3c9-103">Применение индексаторов упрощает работу с синтаксисом, позволяя создавать [классы](../../../csharp/language-reference/keywords/class.md), [структуры](../../../csharp/language-reference/keywords/struct.md) и [интерфейсы](../../../csharp/language-reference/keywords/interface.md), к которым клиентские приложения могут обращаться так же, как к массиву.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-103">Indexers are a syntactic convenience that enable you to create a [class](../../../csharp/language-reference/keywords/class.md), [struct](../../../csharp/language-reference/keywords/struct.md), or [interface](../../../csharp/language-reference/keywords/interface.md) that client applications can access just as an array.</span></span> <span data-ttu-id="cd3c9-104">Индексаторы чаще всего реализуются в типах, предназначенных преимущественно для инкапсуляции внутренней коллекции или массива.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-104">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="cd3c9-105">Допустим, у вас есть класс TempRecord, представляющий журнал с 10 измерениями температуры по шкале Фаренгейта за 24 часа.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-105">For example, suppose you have a class named TempRecord that represents the temperature in Farenheit as recorded at 10 different times during a 24 hour period.</span></span> <span data-ttu-id="cd3c9-106">В этом классе содержится массив temps типа float, представляющий значения температуры, а также <xref:System.DateTime>, содержащий даты соответствующих измерений.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-106">The class contains an array named "temps" of type float to represent the temperatures, and a <xref:System.DateTime> that represents the date the temperatures were recorded.</span></span> <span data-ttu-id="cd3c9-107">Реализация индексатора в этом классе позволит клиентам получать доступ к значениям температуры в экземпляре TempRecord, используя синтаксис `float temp = tr[4]` вместо `float temp = tr.temps[4]`.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-107">By implementing an indexer in this class, clients can access the temperatures in a TempRecord instance as `float temp = tr[4]` instead of as `float temp = tr.temps[4]`.</span></span> <span data-ttu-id="cd3c9-108">Это позволяет не только упростить синтаксис клиентских приложений, но и облегчить понимание кода класса и его предназначения другими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-108">The indexer notation not only simplifies the syntax for client applications; it also makes the class and its purpose more intuitive for other developers to understand.</span></span>  
  
 <span data-ttu-id="cd3c9-109">Чтобы объявить индексатор для класса или структуры, используйте ключевое слово [this](../../../csharp/language-reference/keywords/this.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cd3c9-109">To declare an indexer on a class or struct, use the [this](../../../csharp/language-reference/keywords/this.md) keyword, as in this example:</span></span>  
  
```  
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="cd3c9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd3c9-110">Remarks</span></span>  
 <span data-ttu-id="cd3c9-111">Тип индексатора и типы его параметров должны иметь по крайней мере такой же уровень доступности, как и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-111">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="cd3c9-112">Дополнительные сведения об уровнях доступа см. в разделе [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cd3c9-112">For more information about accessibility levels, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="cd3c9-113">Дополнительные сведения об использовании индексаторов с интерфейсом см. в разделе [Индексаторы интерфейса](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="cd3c9-113">For more information about how to use indexers with an interface, see [Interface Indexers](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).</span></span>  
  
 <span data-ttu-id="cd3c9-114">Сигнатура индексатора определяет число и типы его формальных параметров.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-114">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="cd3c9-115">В ней не указываются тип индексатора или имена его формальных параметров.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-115">It does not include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="cd3c9-116">Если для одного класса объявляется несколько индексаторов, они должны иметь разные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-116">If you declare more than one indexer in the same class, they must have different signatures.</span></span>  
  
 <span data-ttu-id="cd3c9-117">Значение индексатора не классифицируется как переменная и, соответственно, не может передаваться в качестве параметра [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="cd3c9-117">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameter.</span></span>  
  
 <span data-ttu-id="cd3c9-118">Чтобы присвоить индексатору имя, которое можно использовать на других языках, используйте в объявлении атрибут `name`.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-118">To provide the indexer with a name that other languages can use, use a `name` attribute in the declaration.</span></span> <span data-ttu-id="cd3c9-119">Например:</span><span class="sxs-lookup"><span data-stu-id="cd3c9-119">For example:</span></span>  
  
```  
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this [int index]   // Indexer declaration  
{  
}  
```  
  
 <span data-ttu-id="cd3c9-120">Этот индексатор будет иметь имя `TheItem`.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-120">This indexer will have the name `TheItem`.</span></span> <span data-ttu-id="cd3c9-121">Без атрибута имени по умолчанию будет использоваться имя `Item`.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-121">Not providing the name attribute would make `Item` the default name.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="cd3c9-122">Пример 1</span><span class="sxs-lookup"><span data-stu-id="cd3c9-122">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="cd3c9-123">Описание</span><span class="sxs-lookup"><span data-stu-id="cd3c9-123">Description</span></span>  
 <span data-ttu-id="cd3c9-124">В следующем примере показано, как объявить частное поле массива `temps` и индексатор.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-124">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="cd3c9-125">Индексатор обеспечивает прямой доступ к экземпляру `tempRecord[i]`.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-125">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="cd3c9-126">Вместо использования индексатора можно объявить массив как элемент [public](../../../csharp/language-reference/keywords/public.md) и осуществлять доступ к его элементам напрямую (`tempRecord.temps[i]`).</span><span class="sxs-lookup"><span data-stu-id="cd3c9-126">The alternative to using the indexer is to declare the array as a [public](../../../csharp/language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>  
  
 <span data-ttu-id="cd3c9-127">Обратите внимание, что при определении прав доступа индексатора, например в инструкции `Console.Write`, вызывается метод доступа [get](../../../csharp/language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="cd3c9-127">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../../csharp/language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="cd3c9-128">Таким образом, если метод доступа `get` отсутствует, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-128">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cd3c9-129">Код</span><span class="sxs-lookup"><span data-stu-id="cd3c9-129">Code</span></span>  
 <span data-ttu-id="cd3c9-130">[!code-cs[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd3c9-130">[!code-cs[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]</span></span>  
  
## <a name="indexing-using-other-values"></a><span data-ttu-id="cd3c9-131">Индексирование с использованием других значений</span><span class="sxs-lookup"><span data-stu-id="cd3c9-131">Indexing Using Other Values</span></span>  
 <span data-ttu-id="cd3c9-132">В C# тип индекса не ограничивается целочисленными значениями.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-132">C# does not limit the index type to integer.</span></span> <span data-ttu-id="cd3c9-133">Например, в качестве индексатора могут использоваться строки.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-133">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="cd3c9-134">Такой индексатор можно реализовать путем поиска строки в коллекции с возвратом соответствующего значения.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-134">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="cd3c9-135">Поскольку методы доступа можно перегружать, строковые и целочисленные версии могут сосуществовать.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-135">As accessors can be overloaded, the string and integer versions can co-exist.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="cd3c9-136">Пример 2</span><span class="sxs-lookup"><span data-stu-id="cd3c9-136">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="cd3c9-137">Описание</span><span class="sxs-lookup"><span data-stu-id="cd3c9-137">Description</span></span>  
 <span data-ttu-id="cd3c9-138">В этом примере объявляется класс, в котором хранятся дни недели.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-138">In this example, a class is declared that stores the days of the week.</span></span> <span data-ttu-id="cd3c9-139">Также объявляется метод доступа `get`, который принимает название дня и возвращает соответствующее ему целое число.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-139">A `get` accessor is declared that takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="cd3c9-140">Например, для воскресенья будет возвращаться значение 0, для понедельника 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-140">For example, Sunday will return 0, Monday will return 1, and so on.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cd3c9-141">Код</span><span class="sxs-lookup"><span data-stu-id="cd3c9-141">Code</span></span>  
 <span data-ttu-id="cd3c9-142">[!code-cs[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd3c9-142">[!code-cs[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cd3c9-143">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="cd3c9-143">Robust Programming</span></span>  
 <span data-ttu-id="cd3c9-144">Повысить безопасность и надежность индексаторов можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="cd3c9-144">There are two main ways in which the security and reliability of indexers can be improved:</span></span>  
  
-   <span data-ttu-id="cd3c9-145">Реализуйте стратегию обработки ошибок, предусматривающую действия в ситуациях, когда из клиентского кода передается недопустимое значение индекса.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-145">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="cd3c9-146">В первом примере из этого раздела класс TempRecord содержит свойство Length, с помощью которого клиентский код проверяет введенное значение, прежде чем передать его в индексатор.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-146">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="cd3c9-147">Кроме того, код обработки ошибок можно поместить в сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-147">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="cd3c9-148">Не забудьте задокументировать исключения, которые будут вызываться в методе доступа индексатора, для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-148">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>  
  
-   <span data-ttu-id="cd3c9-149">Настройте максимально ограничивающие уровни доступа для методов `get` и [set](../../../csharp/language-reference/keywords/set.md).</span><span class="sxs-lookup"><span data-stu-id="cd3c9-149">Set the accessibility of the `get` and [set](../../../csharp/language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="cd3c9-150">Особенно важно сделать это для метода доступа `set`.</span><span class="sxs-lookup"><span data-stu-id="cd3c9-150">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="cd3c9-151">Дополнительные сведения см. в разделе [Доступность методов доступа](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="cd3c9-151">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd3c9-152">См. также</span><span class="sxs-lookup"><span data-stu-id="cd3c9-152">See Also</span></span>  
 <span data-ttu-id="cd3c9-153">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cd3c9-153">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cd3c9-154">[Индексаторы](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="cd3c9-154">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="cd3c9-155">Свойства</span><span class="sxs-lookup"><span data-stu-id="cd3c9-155">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

