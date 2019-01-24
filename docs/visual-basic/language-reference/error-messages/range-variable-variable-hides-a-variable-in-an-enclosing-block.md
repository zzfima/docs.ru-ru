---
title: Переменная диапазона &lt;переменной&gt; скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: aef52ea912a4180a6505949c8077296628592c72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748120"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="da837-102">Переменная диапазона &lt;переменной&gt; скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса</span><span class="sxs-lookup"><span data-stu-id="da837-102">Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="da837-103">Имя переменной диапазона, указанного в `Select`, `From`, `Aggregate`, или `Let` дублирует имя переменной диапазона, уже указанное ранее в запросе, или имя переменной, неявно объявленный для запроса Например, имя поля или имя агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="da837-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="da837-104">**Идентификатор ошибки:** BC36633</span><span class="sxs-lookup"><span data-stu-id="da837-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da837-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="da837-105">To correct this error</span></span>  
  
-   <span data-ttu-id="da837-106">Убедитесь, что все переменные диапазона в области действия определенного запроса имеют уникальные имена.</span><span class="sxs-lookup"><span data-stu-id="da837-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="da837-107">Запрос можно заключить в круглые скобки, чтобы обеспечить уникальную область для вложенных запросов.</span><span class="sxs-lookup"><span data-stu-id="da837-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da837-108">См. также</span><span class="sxs-lookup"><span data-stu-id="da837-108">See also</span></span>
- <span data-ttu-id="da837-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da837-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="da837-110">Предложение From</span><span class="sxs-lookup"><span data-stu-id="da837-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="da837-111">Предложение Let</span><span class="sxs-lookup"><span data-stu-id="da837-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="da837-112">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="da837-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="da837-113">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="da837-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
