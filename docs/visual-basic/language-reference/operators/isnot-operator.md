---
title: Оператор IsNot
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336063"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="6be78-102">Оператор IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6be78-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="6be78-103">Сравнивает две переменные ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="6be78-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="6be78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6be78-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="6be78-105">Части</span><span class="sxs-lookup"><span data-stu-id="6be78-105">Parts</span></span>
 <span data-ttu-id="6be78-106">`result` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6be78-106">`result` Required.</span></span> <span data-ttu-id="6be78-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="6be78-107">A `Boolean` value.</span></span>

 <span data-ttu-id="6be78-108">`object1` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6be78-108">`object1` Required.</span></span> <span data-ttu-id="6be78-109">Любая `Object` переменная или выражение.</span><span class="sxs-lookup"><span data-stu-id="6be78-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="6be78-110">`object2` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6be78-110">`object2` Required.</span></span> <span data-ttu-id="6be78-111">Любая `Object` переменная или выражение.</span><span class="sxs-lookup"><span data-stu-id="6be78-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="6be78-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="6be78-112">Remarks</span></span>
 <span data-ttu-id="6be78-113">Оператор `IsNot` определяет, ссылаются ли две объектные ссылки на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="6be78-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="6be78-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6be78-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="6be78-115">Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` `False`. в противном случае `result` `True`.</span><span class="sxs-lookup"><span data-stu-id="6be78-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="6be78-116">`IsNot` является противоположностью оператора `Is`.</span><span class="sxs-lookup"><span data-stu-id="6be78-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="6be78-117">Преимущество `IsNot` состоит в том, что можно избежать неудобного синтаксиса с `Not` и `Is`, который трудно читать.</span><span class="sxs-lookup"><span data-stu-id="6be78-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="6be78-118">Операторы `Is` и `IsNot` можно использовать для тестирования объектов с ранней и поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="6be78-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="6be78-119">Пример</span><span class="sxs-lookup"><span data-stu-id="6be78-119">Example</span></span>
 <span data-ttu-id="6be78-120">В следующем примере кода используются как оператор `Is`, так и оператор `IsNot` для выполнения одинакового сравнения.</span><span class="sxs-lookup"><span data-stu-id="6be78-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="6be78-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6be78-121">See also</span></span>

- [<span data-ttu-id="6be78-122">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="6be78-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="6be78-123">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="6be78-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="6be78-124">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6be78-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="6be78-125">Практическое руководство. Проверка совпадения двух объектов</span><span class="sxs-lookup"><span data-stu-id="6be78-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
