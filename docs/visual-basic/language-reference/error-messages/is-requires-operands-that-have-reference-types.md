---
title: '&#39;—&#39; Требуются операнды, имеющие ссылочные типы, но этот операнд имеет тип значения &#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 0b3f80e98087e455ec730dea8c57478528e9259c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722924"
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="063b3-102">&#39;—&#39; Требуются операнды, имеющие ссылочные типы, но этот операнд имеет тип значения &#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="063b3-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="063b3-103">`Is` Оператор сравнения определяет, ссылаются ли две объектные переменные на один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="063b3-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="063b3-104">Это сравнение не определен для типов значений.</span><span class="sxs-lookup"><span data-stu-id="063b3-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="063b3-105">**Идентификатор ошибки:** BC30020</span><span class="sxs-lookup"><span data-stu-id="063b3-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="063b3-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="063b3-106">To correct this error</span></span>  
  
-   <span data-ttu-id="063b3-107">Используйте соответствующий арифметический оператор сравнения или `Like` оператор для сравнения двух типов значений.</span><span class="sxs-lookup"><span data-stu-id="063b3-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063b3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="063b3-108">See also</span></span>
- [<span data-ttu-id="063b3-109">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="063b3-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="063b3-110">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="063b3-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="063b3-111">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="063b3-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
