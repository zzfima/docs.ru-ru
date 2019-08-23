---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966926"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="7361c-102">Оператор IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7361c-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="7361c-103">Сравнивает две переменные ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="7361c-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7361c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7361c-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="7361c-105">Части</span><span class="sxs-lookup"><span data-stu-id="7361c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7361c-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7361c-106">Required.</span></span> <span data-ttu-id="7361c-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7361c-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="7361c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7361c-108">Required.</span></span> <span data-ttu-id="7361c-109">Любая `Object` переменная или выражение.</span><span class="sxs-lookup"><span data-stu-id="7361c-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="7361c-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7361c-110">Required.</span></span> <span data-ttu-id="7361c-111">Любая `Object` переменная или выражение.</span><span class="sxs-lookup"><span data-stu-id="7361c-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7361c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="7361c-112">Remarks</span></span>  
 <span data-ttu-id="7361c-113">Оператор `IsNot` определяет, ссылаются ли две объектные ссылки на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="7361c-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="7361c-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7361c-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="7361c-115">Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта `result` , `False`имеет значение; если нет, `result` то `True`имеет значение.</span><span class="sxs-lookup"><span data-stu-id="7361c-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="7361c-116">`IsNot`является противоположностью `Is` оператора.</span><span class="sxs-lookup"><span data-stu-id="7361c-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="7361c-117">Преимущество `IsNot` заключается в том, что можно избежать неудобного `Not` синтаксиса с и `Is`, что может быть трудно читать.</span><span class="sxs-lookup"><span data-stu-id="7361c-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="7361c-118">Операторы `Is` и`IsNot` можно использовать для тестирования объектов с ранней и поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="7361c-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7361c-119">Оператор не может использоваться для сравнения выражений, `TypeOf` возвращаемых оператором. `IsNot`</span><span class="sxs-lookup"><span data-stu-id="7361c-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="7361c-120">Вместо этого необходимо использовать `Not` операторы и. `Is`</span><span class="sxs-lookup"><span data-stu-id="7361c-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7361c-121">Пример</span><span class="sxs-lookup"><span data-stu-id="7361c-121">Example</span></span>  
 <span data-ttu-id="7361c-122">В следующем примере кода используются `Is` оператор `IsNot` и оператор для выполнения одинакового сравнения.</span><span class="sxs-lookup"><span data-stu-id="7361c-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="7361c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="7361c-123">See also</span></span>

- [<span data-ttu-id="7361c-124">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="7361c-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="7361c-125">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="7361c-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="7361c-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7361c-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7361c-127">Практическое руководство. Проверка того, совпадают ли два объекта</span><span class="sxs-lookup"><span data-stu-id="7361c-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
