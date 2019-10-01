---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 32e8f9532244679d2994b0e3d98279d75f7e77b4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701036"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="b1e25-102">Оператор IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1e25-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="b1e25-103">Сравнивает две переменные ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="b1e25-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1e25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1e25-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="b1e25-105">Части</span><span class="sxs-lookup"><span data-stu-id="b1e25-105">Parts</span></span>
 <span data-ttu-id="b1e25-106">`result` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b1e25-106">`result` Required.</span></span> <span data-ttu-id="b1e25-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b1e25-107">A `Boolean` value.</span></span>

 <span data-ttu-id="b1e25-108">`object1` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b1e25-108">`object1` Required.</span></span> <span data-ttu-id="b1e25-109">Любая переменная или выражение `Object`.</span><span class="sxs-lookup"><span data-stu-id="b1e25-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="b1e25-110">`object2` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b1e25-110">`object2` Required.</span></span> <span data-ttu-id="b1e25-111">Любая переменная или выражение `Object`.</span><span class="sxs-lookup"><span data-stu-id="b1e25-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1e25-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1e25-112">Remarks</span></span>
 <span data-ttu-id="b1e25-113">Оператор `IsNot` определяет, ссылаются ли две объектные ссылки на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="b1e25-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="b1e25-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b1e25-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="b1e25-115">Если `object1` и `object2` ссылаются на один и тот же экземпляр объекта, `result` — `False`; в противном случае `result` — `True`.</span><span class="sxs-lookup"><span data-stu-id="b1e25-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="b1e25-116">`IsNot` является противоположностью оператора `Is`.</span><span class="sxs-lookup"><span data-stu-id="b1e25-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="b1e25-117">Преимущество `IsNot` состоит в том, что вы можете избежать неудобного синтаксиса с `Not` и `Is`, что может быть трудно читать.</span><span class="sxs-lookup"><span data-stu-id="b1e25-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="b1e25-118">Для тестирования объектов с ранней и поздней привязкой можно использовать операторы `Is` и `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="b1e25-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="b1e25-119">Пример</span><span class="sxs-lookup"><span data-stu-id="b1e25-119">Example</span></span>
 <span data-ttu-id="b1e25-120">В следующем примере кода используются как оператор `Is`, так и оператор `IsNot` для выполнения одинакового сравнения.</span><span class="sxs-lookup"><span data-stu-id="b1e25-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="b1e25-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b1e25-121">See also</span></span>

- [<span data-ttu-id="b1e25-122">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="b1e25-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="b1e25-123">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="b1e25-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="b1e25-124">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1e25-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- <span data-ttu-id="b1e25-125">[Практическое руководство. Проверка того, что два объекта одинаковы, @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="b1e25-125">[How to: Test Whether Two Objects Are the Same](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)</span></span>
