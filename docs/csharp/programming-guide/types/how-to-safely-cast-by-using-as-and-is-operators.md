---
title: "Практическое руководство. Безопасное приведение с помощью операторов as и is (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
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
ms.openlocfilehash: c5daa8525f45c123dabb0f59dfd29385b9e50354
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a><span data-ttu-id="d72e7-102">Практическое руководство. Безопасное приведение с помощью операторов as и is (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d72e7-102">How to: Safely Cast by Using as and is Operators (C# Programming Guide)</span></span>
<span data-ttu-id="d72e7-103">В связи с полиморфизмом объектов переменная типа базового класса может содержать производный тип.</span><span class="sxs-lookup"><span data-stu-id="d72e7-103">Because objects are polymorphic, it is possible for a variable of a base class type to hold a derived type.</span></span> <span data-ttu-id="d72e7-104">Для доступа к методу производного типа необходимо привести значение обратно к производному типу.</span><span class="sxs-lookup"><span data-stu-id="d72e7-104">To access the derived type's method, it is necessary to cast the value back to the derived type.</span></span> <span data-ttu-id="d72e7-105">Тем не менее при попытке простого приведения в этих случаях существует риск возникновения исключения <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="d72e7-105">However, to attempt a simple cast in these cases creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="d72e7-106">Именно поэтому в языке C# реализованы операторы [is](../../../csharp/language-reference/keywords/is.md) и [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="d72e7-106">That is why C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators.</span></span> <span data-ttu-id="d72e7-107">С помощью этих операторов можно проверить возможность успешного выполнения приведения без возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="d72e7-107">You can use these operators to test whether a cast will succeed without causing an exception to be thrown.</span></span> <span data-ttu-id="d72e7-108">В общем случае оператор `as` является более эффективным, поскольку для приведения, которое может быть выполнено успешно, он возвращает фактическое значение приведения.</span><span class="sxs-lookup"><span data-stu-id="d72e7-108">In general, the `as` operator is more efficient because it actually returns the cast value if the cast can be made successfully.</span></span> <span data-ttu-id="d72e7-109">Оператор `is` возвращает только логическое значение.</span><span class="sxs-lookup"><span data-stu-id="d72e7-109">The `is` operator returns only a Boolean value.</span></span> <span data-ttu-id="d72e7-110">Таким образом, он может использоваться в тех случаях, когда нужно определить тип объекта и не требуется выполнять его фактическое приведение.</span><span class="sxs-lookup"><span data-stu-id="d72e7-110">It can therefore be used when you just want to determine an object's type but do not have to actually cast it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d72e7-111">Пример</span><span class="sxs-lookup"><span data-stu-id="d72e7-111">Example</span></span>  
 <span data-ttu-id="d72e7-112">В следующих примерах показано, как использовать операторы `is` и `as` для приведения из одного ссылочного типа к другому без риска возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="d72e7-112">The following examples show how to use the `is` and `as` operators to cast from one reference type to another without the risk of throwing an exception.</span></span> <span data-ttu-id="d72e7-113">В этом примере также демонстрируется использование оператора `as` с типами значений, допускающими значения NULL.</span><span class="sxs-lookup"><span data-stu-id="d72e7-113">The example also shows how to use the `as` operator with nullable value types.</span></span>  
  
 <span data-ttu-id="d72e7-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d72e7-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72e7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d72e7-115">See Also</span></span>  
 <span data-ttu-id="d72e7-116">[Типы](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="d72e7-116">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="d72e7-117">[Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="d72e7-117">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="d72e7-118">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="d72e7-118">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)

