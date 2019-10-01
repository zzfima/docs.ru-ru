---
title: Оператор Is (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 0351d224d9bf08a8f3ca74090de7b9c51c2c61bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701365"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="55c9b-102">Оператор Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55c9b-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="55c9b-103">Сравнивает две переменные ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="55c9b-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55c9b-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="55c9b-105">Части</span><span class="sxs-lookup"><span data-stu-id="55c9b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="55c9b-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="55c9b-106">Required.</span></span> <span data-ttu-id="55c9b-107">Любое значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="55c9b-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="55c9b-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="55c9b-108">Required.</span></span> <span data-ttu-id="55c9b-109">Любое имя `Object`.</span><span class="sxs-lookup"><span data-stu-id="55c9b-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="55c9b-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="55c9b-110">Required.</span></span> <span data-ttu-id="55c9b-111">Любое имя `Object`.</span><span class="sxs-lookup"><span data-stu-id="55c9b-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55c9b-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="55c9b-112">Remarks</span></span>  
 <span data-ttu-id="55c9b-113">Оператор `Is` определяет, ссылаются ли две объектные ссылки на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="55c9b-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="55c9b-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="55c9b-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="55c9b-115">Если `object1` и `object2` ссылаются на один и тот же экземпляр объекта, `result` — `True`; в противном случае `result` — `False`.</span><span class="sxs-lookup"><span data-stu-id="55c9b-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="55c9b-116">`Is` можно также использовать с ключевым словом `TypeOf` для создания выражения `TypeOf`... `Is`, которое проверяет, совместима ли объектная переменная с типом данных.</span><span class="sxs-lookup"><span data-stu-id="55c9b-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55c9b-117">Ключевое слово `Is` также используется в [SELECT... Case, инструкция](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="55c9b-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55c9b-118">Пример</span><span class="sxs-lookup"><span data-stu-id="55c9b-118">Example</span></span>  
 <span data-ttu-id="55c9b-119">В следующем примере оператор `Is` используется для сравнения пар ссылок на объекты.</span><span class="sxs-lookup"><span data-stu-id="55c9b-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="55c9b-120">Результаты присваиваются значению `Boolean`, показывающему, идентичны ли два объекта.</span><span class="sxs-lookup"><span data-stu-id="55c9b-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="55c9b-121">Как показано в предыдущем примере, оператор `Is` можно использовать для тестирования объектов с ранней и поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="55c9b-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c9b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="55c9b-122">See also</span></span>

- [<span data-ttu-id="55c9b-123">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="55c9b-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="55c9b-124">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="55c9b-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="55c9b-125">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55c9b-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="55c9b-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55c9b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="55c9b-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="55c9b-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="55c9b-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="55c9b-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
