---
title: Практическое руководство. Объявите объектную переменную и присвойте ей объект в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 71949d50b01d7f252a988e86ca259261086d3b3b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630870"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="d5fef-102">Практическое руководство. Объявите объектную переменную и присвойте ей объект в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5fef-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="d5fef-103">Переменная [типа данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) объявляется путем указания `As Object` в [операторе Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d5fef-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="d5fef-104">Вы назначаете объект такой переменной, помещая объект после знака равенства (`=`) в операторе присваивания или предложении инициализации.</span><span class="sxs-lookup"><span data-stu-id="d5fef-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="d5fef-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d5fef-105">Example</span></span>

<span data-ttu-id="d5fef-106">В следующем примере объявляется `Object` переменная и назначается ей текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d5fef-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="d5fef-107">Объявление и присваивание можно объединить, инициализируя переменную как часть ее объявления.</span><span class="sxs-lookup"><span data-stu-id="d5fef-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="d5fef-108">Следующий пример эквивалентен предыдущему примеру.</span><span class="sxs-lookup"><span data-stu-id="d5fef-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a><span data-ttu-id="d5fef-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d5fef-109">Compiling the Code</span></span>

<span data-ttu-id="d5fef-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d5fef-110">This example requires:</span></span>

- <span data-ttu-id="d5fef-111">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="d5fef-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="d5fef-112">Класс, структура или модуль, в котором будет размещена `Dim` инструкция.</span><span class="sxs-lookup"><span data-stu-id="d5fef-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="d5fef-113">Процедура, в которой следует разместить оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="d5fef-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5fef-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d5fef-114">See also</span></span>

- [<span data-ttu-id="d5fef-115">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="d5fef-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="d5fef-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="d5fef-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="d5fef-117">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="d5fef-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="d5fef-118">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="d5fef-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d5fef-119">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="d5fef-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="d5fef-120">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="d5fef-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="d5fef-121">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="d5fef-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
