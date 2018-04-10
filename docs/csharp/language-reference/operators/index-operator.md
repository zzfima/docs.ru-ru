---
title: Оператор [] (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03664f5604bb7d7dce9e8ae2ff0ec045c6a203b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="efb61-102">Оператор [] (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="efb61-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="efb61-103">Квадратные скобки (`[]`) используются для массивов, индексаторов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="efb61-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="efb61-104">Кроме того, их можно использовать с указателями.</span><span class="sxs-lookup"><span data-stu-id="efb61-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb61-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="efb61-105">Remarks</span></span>  
 <span data-ttu-id="efb61-106">Тип массива указывается перед оператором `[]`:</span><span class="sxs-lookup"><span data-stu-id="efb61-106">An array type is a type followed by `[]`:</span></span>  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 <span data-ttu-id="efb61-107">Для доступа к элементу массива его индекс необходимо заключить в скобки:</span><span class="sxs-lookup"><span data-stu-id="efb61-107">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 <span data-ttu-id="efb61-108">Если индекс массива выходит за границы диапазона, создается исключение.</span><span class="sxs-lookup"><span data-stu-id="efb61-108">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="efb61-109">Перегрузка оператора индексирования массива невозможна. Однако типы могут определять индексаторы и свойства, принимающие один или несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="efb61-109">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="efb61-110">Параметры индексатора заключаются в квадратные скобки, как и индексы массива, но, в отличие от индексов массива, которые должны быть целочисленными, эти параметры могут быть любого типа.</span><span class="sxs-lookup"><span data-stu-id="efb61-110">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="efb61-111">Например, в платформе .NET Framework определен тип `Hashtable`, связывающий ключи и значения произвольного типа.</span><span class="sxs-lookup"><span data-stu-id="efb61-111">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 <span data-ttu-id="efb61-112">Кроме того, квадратные скобки используются для определения [атрибутов](../../../csharp/programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="efb61-112">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 <span data-ttu-id="efb61-113">Квадратные скобки можно использовать для создания индекса на основе указателя:</span><span class="sxs-lookup"><span data-stu-id="efb61-113">You can use square brackets to index off a pointer:</span></span>  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 <span data-ttu-id="efb61-114">Проверка границ не выполняется.</span><span class="sxs-lookup"><span data-stu-id="efb61-114">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="efb61-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="efb61-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efb61-116">См. также</span><span class="sxs-lookup"><span data-stu-id="efb61-116">See Also</span></span>  
 [<span data-ttu-id="efb61-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="efb61-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="efb61-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="efb61-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="efb61-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="efb61-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="efb61-120">Массивы</span><span class="sxs-lookup"><span data-stu-id="efb61-120">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="efb61-121">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="efb61-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="efb61-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="efb61-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="efb61-123">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="efb61-123">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
