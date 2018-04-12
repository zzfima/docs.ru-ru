---
title: '&#39; — &#39; требуются операнды, имеющие ссылочные типы, но этот операнд имеет тип значения &#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28d017a566fdc1e55cb53ce907641d6bccfb354c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="8cc91-102">&#39; — &#39; требуются операнды, имеющие ссылочные типы, но этот операнд имеет тип значения &#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="8cc91-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="8cc91-103">`Is` Оператор сравнения определяет, ссылаются ли две объектные переменные с тем же экземпляром.</span><span class="sxs-lookup"><span data-stu-id="8cc91-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="8cc91-104">Это сравнение не определен для типов значений.</span><span class="sxs-lookup"><span data-stu-id="8cc91-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="8cc91-105">**Идентификатор ошибки:** BC30020</span><span class="sxs-lookup"><span data-stu-id="8cc91-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8cc91-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8cc91-106">To correct this error</span></span>  
  
-   <span data-ttu-id="8cc91-107">Используйте соответствующий арифметический оператор сравнения или `Like` оператор для сравнения двух типов значений.</span><span class="sxs-lookup"><span data-stu-id="8cc91-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc91-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8cc91-108">See Also</span></span>  
 [<span data-ttu-id="8cc91-109">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="8cc91-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="8cc91-110">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="8cc91-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="8cc91-111">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="8cc91-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
