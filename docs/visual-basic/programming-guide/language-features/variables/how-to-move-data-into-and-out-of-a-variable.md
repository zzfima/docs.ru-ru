---
title: Практическое руководство. Запись данных в переменную и их извлечение из переменной
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bc5a7377a5e2e4c7ebe7291fd5f0093c4d6e996d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346893"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="5b9c3-102">Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b9c3-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="5b9c3-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="5b9c3-104">Putting Data in a Variable</span><span class="sxs-lookup"><span data-stu-id="5b9c3-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="5b9c3-105">To store a value in a variable</span><span class="sxs-lookup"><span data-stu-id="5b9c3-105">To store a value in a variable</span></span>

- <span data-ttu-id="5b9c3-106">Use the variable name on the left side of an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="5b9c3-107">The following example sets the value of the variable `alpha`.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="5b9c3-108">The value generated on the right side of the assignment statement is stored in the variable.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="5b9c3-109">Getting Data from a Variable</span><span class="sxs-lookup"><span data-stu-id="5b9c3-109">Getting Data from a Variable</span></span>

<span data-ttu-id="5b9c3-110">You retrieve a variable's value by including the variable name in an expression.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="5b9c3-111">To retrieve a value from a variable</span><span class="sxs-lookup"><span data-stu-id="5b9c3-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="5b9c3-112">Use the variable name in an expression.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-112">Use the variable name in an expression.</span></span> <span data-ttu-id="5b9c3-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="5b9c3-114">\-или-</span><span class="sxs-lookup"><span data-stu-id="5b9c3-114">\-or-</span></span>

- <span data-ttu-id="5b9c3-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="5b9c3-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="5b9c3-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span><span class="sxs-lookup"><span data-stu-id="5b9c3-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b9c3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5b9c3-118">See also</span></span>

- [<span data-ttu-id="5b9c3-119">Переменные</span><span class="sxs-lookup"><span data-stu-id="5b9c3-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="5b9c3-120">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="5b9c3-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="5b9c3-121">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="5b9c3-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
