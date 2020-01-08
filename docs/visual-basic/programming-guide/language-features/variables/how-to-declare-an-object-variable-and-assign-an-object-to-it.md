---
title: Инструкции. Объявление объектной переменной и назначение ей объекта
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: eaaeda2a986584e6e1a2e0d2cda3890fb6187598
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344235"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="a7053-102">Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта</span><span class="sxs-lookup"><span data-stu-id="a7053-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="a7053-103">Переменная [типа данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) объявляется путем указания `As Object` в [операторе Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a7053-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="a7053-104">Вы назначаете объект такой переменной, помещая объект после знака равенства (`=`) в операторе присваивания или в предложении инициализации.</span><span class="sxs-lookup"><span data-stu-id="a7053-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="a7053-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a7053-105">Example</span></span>

<span data-ttu-id="a7053-106">В следующем примере объявляется переменная `Object` и ей присваивается текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="a7053-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="a7053-107">Объявление и присваивание можно объединить, инициализируя переменную как часть ее объявления.</span><span class="sxs-lookup"><span data-stu-id="a7053-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="a7053-108">Следующий пример эквивалентен предыдущему примеру.</span><span class="sxs-lookup"><span data-stu-id="a7053-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="a7053-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a7053-109">Compile the code</span></span>

<span data-ttu-id="a7053-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="a7053-110">This example requires:</span></span>

- <span data-ttu-id="a7053-111">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="a7053-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="a7053-112">Класс, структура или модуль, в котором будет размещена инструкция `Dim`.</span><span class="sxs-lookup"><span data-stu-id="a7053-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="a7053-113">Процедура, в которой следует разместить оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="a7053-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7053-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7053-114">See also</span></span>

- [<span data-ttu-id="a7053-115">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="a7053-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="a7053-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="a7053-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="a7053-117">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="a7053-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="a7053-118">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="a7053-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="a7053-119">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="a7053-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="a7053-120">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="a7053-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="a7053-121">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="a7053-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
