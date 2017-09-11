---
title: "Практическое руководство. Доступ к классу коллекции с помощью оператора foreach (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
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
ms.openlocfilehash: 2ad81ab699b079f4aabb04a886211e94a937335d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a><span data-ttu-id="1afbe-102">Практическое руководство. Доступ к классу коллекции с помощью оператора foreach (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="1afbe-102">How to: Access a Collection Class with foreach (C# Programming Guide)</span></span>
<span data-ttu-id="1afbe-103">В следующем примере кода показано, как записать неуниверсальный класс коллекции, который можно использовать с оператором [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="1afbe-103">The following code example illustrates how to write a non-generic collection class that can be used with [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span></span> <span data-ttu-id="1afbe-104">В этом примере определяется класс строкового лексического анализатора.</span><span class="sxs-lookup"><span data-stu-id="1afbe-104">The example defines a string tokenizer class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1afbe-105">Этот пример представляет рекомендованный способ, только если использование универсального класса коллекции невозможно.</span><span class="sxs-lookup"><span data-stu-id="1afbe-105">This example represents recommended practice only when you cannot use a generic collection class.</span></span> <span data-ttu-id="1afbe-106">Пример реализации типобезопасного универсального класса коллекции, поддерживающего <xref:System.Collections.Generic.IEnumerable%601>, см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="1afbe-106">For an example of how to implement a type-safe generic collection class that supports <xref:System.Collections.Generic.IEnumerable%601>, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="1afbe-107">В этом примере следующий сегмент кода использует класс `Tokens` для разделения предложения "Это предложение-образец"</span><span class="sxs-lookup"><span data-stu-id="1afbe-107">In the example, the following code segment uses the `Tokens` class to break the sentence "This is a sample sentence."</span></span> <span data-ttu-id="1afbe-108">на токены с помощью разделителей " " и "-".</span><span class="sxs-lookup"><span data-stu-id="1afbe-108">into tokens by using ' ' and '-' as separators.</span></span> <span data-ttu-id="1afbe-109">Затем код отображает эти токены с помощью оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="1afbe-109">The code then displays those tokens by using a `foreach` statement.</span></span>  
  
 <span data-ttu-id="1afbe-110">[!code-cs[csProgGuideCollections #3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1afbe-110">[!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1afbe-111">Пример</span><span class="sxs-lookup"><span data-stu-id="1afbe-111">Example</span></span>  
 <span data-ttu-id="1afbe-112">По сути, класс `Tokens` использует массив для хранения токенов.</span><span class="sxs-lookup"><span data-stu-id="1afbe-112">Internally, the `Tokens` class uses an array to store the tokens.</span></span> <span data-ttu-id="1afbe-113">Поскольку массивы реализуют <xref:System.Collections.IEnumerator> и <xref:System.Collections.IEnumerable>, в этом примере кода можно использовать методы перечисления массива (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.Current%2A>) вместо того, чтобы определять их в классе `Tokens`.</span><span class="sxs-lookup"><span data-stu-id="1afbe-113">Because arrays implement <xref:System.Collections.IEnumerator> and <xref:System.Collections.IEnumerable>, the code example could have used the array's enumeration methods (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A>) instead of defining them in the `Tokens` class.</span></span> <span data-ttu-id="1afbe-114">Определения методов содержатся в примере для уточнения способа их определения и предназначения каждого из них.</span><span class="sxs-lookup"><span data-stu-id="1afbe-114">The method definitions are included in the example to clarify how they are defined and what each does.</span></span>  
  
 <span data-ttu-id="1afbe-115">[!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1afbe-115">[!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]</span></span>  
  
 <span data-ttu-id="1afbe-116">В C# для класса коллекции необязательно реализовывать <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> в совместимой с `foreach` форме.</span><span class="sxs-lookup"><span data-stu-id="1afbe-116">In C#, it is not necessary for a collection class to implement <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> to be compatible with `foreach`.</span></span> <span data-ttu-id="1afbe-117">Если класс содержит необходимые члены <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.Current%2A>, он может работать с циклом `foreach`.</span><span class="sxs-lookup"><span data-stu-id="1afbe-117">If the class has the required <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A> members, it will work with `foreach`.</span></span> <span data-ttu-id="1afbe-118">Пропуск интерфейсов имеет преимущество, поскольку позволяет определить тип возврата для `Current`, который более специфичен, чем тип <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="1afbe-118">Omitting the interfaces has the advantage of enabling you to define a return type for `Current` that is more specific than <xref:System.Object>.</span></span> <span data-ttu-id="1afbe-119">Это повышает типобезопасность.</span><span class="sxs-lookup"><span data-stu-id="1afbe-119">This provides type safety.</span></span>  
  
 <span data-ttu-id="1afbe-120">Например, измените следующие строки в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="1afbe-120">For example, change the following lines in the previous example.</span></span>  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 <span data-ttu-id="1afbe-121">Поскольку `Current` возвращает строку, компилятор может определить, когда используется несовместимый тип в операторе `foreach`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="1afbe-121">Because `Current` returns a string, the compiler can detect when an incompatible type is used in a `foreach` statement, as shown in the following code.</span></span>  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 <span data-ttu-id="1afbe-122">Недостатком пропуска типов <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> является то, что класс коллекции больше не может взаимодействовать с операторами `foreach` или эквивалентными операторами из других языков среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1afbe-122">The disadvantage of omitting <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> is that the collection class is no longer interoperable with the `foreach` statements, or equivalent statements, of other common language runtime languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1afbe-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1afbe-123">See Also</span></span>  
 <span data-ttu-id="1afbe-124"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="1afbe-124"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="1afbe-125">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1afbe-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1afbe-126">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1afbe-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1afbe-127">[Массивы](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="1afbe-127">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="1afbe-128">Коллекции</span><span class="sxs-lookup"><span data-stu-id="1afbe-128">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)

