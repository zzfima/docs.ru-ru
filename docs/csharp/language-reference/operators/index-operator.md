---
title: Оператор [] (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 65908bb3bcd8912ef81fc094e5958ae8dc4ae1f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286033"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="86b9d-102">Оператор [] (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="86b9d-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="86b9d-103">Квадратные скобки (`[]`) используются для массивов, индексаторов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="86b9d-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="86b9d-104">Кроме того, их можно использовать с указателями.</span><span class="sxs-lookup"><span data-stu-id="86b9d-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86b9d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="86b9d-105">Remarks</span></span>  
 <span data-ttu-id="86b9d-106">Тип массива указывается перед оператором `[]`:</span><span class="sxs-lookup"><span data-stu-id="86b9d-106">An array type is a type followed by `[]`:</span></span>  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 <span data-ttu-id="86b9d-107">Для доступа к элементу массива его индекс необходимо заключить в скобки:</span><span class="sxs-lookup"><span data-stu-id="86b9d-107">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 <span data-ttu-id="86b9d-108">Если индекс массива выходит за границы диапазона, создается исключение.</span><span class="sxs-lookup"><span data-stu-id="86b9d-108">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="86b9d-109">Перегрузка оператора индексирования массива невозможна. Однако типы могут определять индексаторы и свойства, принимающие один или несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="86b9d-109">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="86b9d-110">Параметры индексатора заключаются в квадратные скобки, как и индексы массива, но, в отличие от индексов массива, которые должны быть целочисленными, эти параметры могут быть любого типа.</span><span class="sxs-lookup"><span data-stu-id="86b9d-110">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="86b9d-111">Например, в платформе .NET Framework определен тип `Hashtable`, связывающий ключи и значения произвольного типа.</span><span class="sxs-lookup"><span data-stu-id="86b9d-111">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 <span data-ttu-id="86b9d-112">Кроме того, квадратные скобки используются для определения [атрибутов](../../../csharp/programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="86b9d-112">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 <span data-ttu-id="86b9d-113">Квадратные скобки можно использовать для создания индекса на основе указателя:</span><span class="sxs-lookup"><span data-stu-id="86b9d-113">You can use square brackets to index off a pointer:</span></span>  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 <span data-ttu-id="86b9d-114">Проверка границ не выполняется.</span><span class="sxs-lookup"><span data-stu-id="86b9d-114">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="86b9d-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="86b9d-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86b9d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="86b9d-116">See Also</span></span>  
 [<span data-ttu-id="86b9d-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="86b9d-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="86b9d-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="86b9d-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="86b9d-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="86b9d-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="86b9d-120">Массивы</span><span class="sxs-lookup"><span data-stu-id="86b9d-120">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="86b9d-121">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="86b9d-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="86b9d-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="86b9d-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="86b9d-123">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="86b9d-123">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
