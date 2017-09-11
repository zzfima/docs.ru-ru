---
title: "Оператор [] (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: b49d41af0dd4dc34b1b74c62ce8779aa31d69f77
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="7132b-102">Оператор [] (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7132b-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="7132b-103">Квадратные скобки (`[]`) используются для массивов, индексаторов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="7132b-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="7132b-104">Кроме того, их можно использовать с указателями.</span><span class="sxs-lookup"><span data-stu-id="7132b-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7132b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="7132b-105">Remarks</span></span>  
 <span data-ttu-id="7132b-106">Тип массива указывается перед оператором `[]`:</span><span class="sxs-lookup"><span data-stu-id="7132b-106">An array type is a type followed by `[]`:</span></span>  
  
 <span data-ttu-id="7132b-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7132b-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="7132b-108">Для доступа к элементу массива его индекс необходимо заключить в скобки:</span><span class="sxs-lookup"><span data-stu-id="7132b-108">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 <span data-ttu-id="7132b-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7132b-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="7132b-110">Если индекс массива выходит за границы диапазона, создается исключение.</span><span class="sxs-lookup"><span data-stu-id="7132b-110">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="7132b-111">Перегрузка оператора индексирования массива невозможна. Однако типы могут определять индексаторы и свойства, принимающие один или несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="7132b-111">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="7132b-112">Параметры индексатора заключаются в квадратные скобки, как и индексы массива, но, в отличие от индексов массива, которые должны быть целочисленными, эти параметры могут быть любого типа.</span><span class="sxs-lookup"><span data-stu-id="7132b-112">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="7132b-113">Например, в платформе .NET Framework определен тип `Hashtable`, связывающий ключи и значения произвольного типа.</span><span class="sxs-lookup"><span data-stu-id="7132b-113">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 <span data-ttu-id="7132b-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="7132b-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="7132b-115">Кроме того, квадратные скобки используются для определения [атрибутов](../../../csharp/programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="7132b-115">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 <span data-ttu-id="7132b-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="7132b-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="7132b-117">Квадратные скобки можно использовать для создания индекса на основе указателя:</span><span class="sxs-lookup"><span data-stu-id="7132b-117">You can use square brackets to index off a pointer:</span></span>  
  
 <span data-ttu-id="7132b-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="7132b-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="7132b-119">Проверка границ не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7132b-119">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7132b-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7132b-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7132b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7132b-121">See Also</span></span>  
 <span data-ttu-id="7132b-122">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7132b-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7132b-123">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7132b-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7132b-124">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="7132b-124">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="7132b-125">[Массивы](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="7132b-125">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="7132b-126">[Индексаторы](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="7132b-126">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="7132b-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="7132b-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="7132b-128">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="7132b-128">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)

