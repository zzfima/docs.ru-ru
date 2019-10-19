---
title: Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: ca50ddd86cfbba8db0148ed315645714acabc18d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582425"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="5ff73-102">Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов</span><span class="sxs-lookup"><span data-stu-id="5ff73-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>

<span data-ttu-id="5ff73-103">В запрос LINQ входит программный элемент, который принимает один или несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="5ff73-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="5ff73-104">Компилятору не удается вывести переменную диапазона из этого программного элемента.</span><span class="sxs-lookup"><span data-stu-id="5ff73-104">The compiler is unable to infer a range variable from that programming element.</span></span>

<span data-ttu-id="5ff73-105">**Идентификатор ошибки:** BC36599</span><span class="sxs-lookup"><span data-stu-id="5ff73-105">**Error ID:** BC36599</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5ff73-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5ff73-106">To correct this error</span></span>

<span data-ttu-id="5ff73-107">Укажите явное имя переменной для программного элемента, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="5ff73-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a><span data-ttu-id="5ff73-108">См. также</span><span class="sxs-lookup"><span data-stu-id="5ff73-108">See also</span></span>

- <span data-ttu-id="5ff73-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ff73-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="5ff73-110">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="5ff73-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
