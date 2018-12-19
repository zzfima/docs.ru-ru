---
title: Руководство по программированию на C#. Сравнение указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 72d9017064959c801bd2702ff585ee16b1592da6
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236795"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="81a40-102">Сравнение указателей (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="81a40-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="81a40-103">Для сравнения указателей любого типа можно применять следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="81a40-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="81a40-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="81a40-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="81a40-105">Операторы сравнения сравнивают адреса двух операндов, принимая их как целые числа без знака.</span><span class="sxs-lookup"><span data-stu-id="81a40-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81a40-106">Пример</span><span class="sxs-lookup"><span data-stu-id="81a40-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="81a40-107">Пример результатов выполнения</span><span class="sxs-lookup"><span data-stu-id="81a40-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="81a40-108">См. также</span><span class="sxs-lookup"><span data-stu-id="81a40-108">See Also</span></span>

- [<span data-ttu-id="81a40-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="81a40-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="81a40-110">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="81a40-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="81a40-111">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="81a40-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="81a40-112">Обработка указателей</span><span class="sxs-lookup"><span data-stu-id="81a40-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="81a40-113">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="81a40-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="81a40-114">Типы</span><span class="sxs-lookup"><span data-stu-id="81a40-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="81a40-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="81a40-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="81a40-116">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="81a40-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="81a40-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="81a40-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
