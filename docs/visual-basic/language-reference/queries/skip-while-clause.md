---
title: Предложение Skip While
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333145"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="a1553-102">Предложение Skip While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1553-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="a1553-103">Пропускает элементы в коллекции, если заданное условие имеет значение `true`, и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="a1553-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1553-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1553-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a1553-105">Части</span><span class="sxs-lookup"><span data-stu-id="a1553-105">Parts</span></span>  
  
|<span data-ttu-id="a1553-106">Термин</span><span class="sxs-lookup"><span data-stu-id="a1553-106">Term</span></span>|<span data-ttu-id="a1553-107">Определение</span><span class="sxs-lookup"><span data-stu-id="a1553-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="a1553-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a1553-108">Required.</span></span> <span data-ttu-id="a1553-109">An expression that represents a condition to test elements for.</span><span class="sxs-lookup"><span data-stu-id="a1553-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="a1553-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a1553-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1553-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="a1553-111">Remarks</span></span>  
 <span data-ttu-id="a1553-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span><span class="sxs-lookup"><span data-stu-id="a1553-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="a1553-113">After `expression` returns `false`, the query returns all the remaining elements.</span><span class="sxs-lookup"><span data-stu-id="a1553-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="a1553-114">The `expression` is ignored for the remaining results.</span><span class="sxs-lookup"><span data-stu-id="a1553-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="a1553-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span><span class="sxs-lookup"><span data-stu-id="a1553-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="a1553-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span><span class="sxs-lookup"><span data-stu-id="a1553-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="a1553-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span><span class="sxs-lookup"><span data-stu-id="a1553-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="a1553-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span><span class="sxs-lookup"><span data-stu-id="a1553-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1553-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a1553-119">Example</span></span>  
 <span data-ttu-id="a1553-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span><span class="sxs-lookup"><span data-stu-id="a1553-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a1553-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a1553-121">See also</span></span>

- <span data-ttu-id="a1553-122">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1553-122">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="a1553-123">Запросы</span><span class="sxs-lookup"><span data-stu-id="a1553-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a1553-124">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="a1553-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="a1553-125">Предложение From</span><span class="sxs-lookup"><span data-stu-id="a1553-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="a1553-126">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="a1553-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="a1553-127">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="a1553-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="a1553-128">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="a1553-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
