---
title: Операнд IsNot типа  можно сравнить только с Nothing, так как  является типом, допускающим значение NULL
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 1660971e2a1a11d7a2d14f222cd149edf4aa4c7b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249517"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="9608b-102">Операнд IsNot типа  можно сравнить только с Nothing, так как  является типом, допускающим значение NULL</span><span class="sxs-lookup"><span data-stu-id="9608b-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="9608b-103">Переменная, объявленная как недействительный тип значения, `Nothing` сравнивалась с выражением, не использующим `IsNot` оператора.</span><span class="sxs-lookup"><span data-stu-id="9608b-103">A variable declared as a nullable value type has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="9608b-104">**Идентификатор ошибки:** BC32128</span><span class="sxs-lookup"><span data-stu-id="9608b-104">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9608b-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9608b-105">To correct this error</span></span>

<span data-ttu-id="9608b-106">Чтобы сравнить тип, допускающий значение null, с выражением, отличным от `Nothing` , с помощью оператора `IsNot` , вызовите метод `GetType` для типа, допускающего значение null, и сравните результат с выражением, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9608b-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="9608b-107">См. также</span><span class="sxs-lookup"><span data-stu-id="9608b-107">See also</span></span>

- [<span data-ttu-id="9608b-108">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="9608b-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="9608b-109">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="9608b-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
