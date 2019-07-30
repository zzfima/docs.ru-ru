---
title: Практическое руководство. Перемещение данных в переменную или из нее (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: df55f122c4ea029a383196f8d9684295ac8926aa
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631125"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="d087d-102">Практическое руководство. Перемещение данных в переменную или из нее (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d087d-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="d087d-103">Значение сохраняется в переменной путем размещения имени переменной в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="d087d-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="d087d-104">Помещение данных в переменную</span><span class="sxs-lookup"><span data-stu-id="d087d-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="d087d-105">Сохранение значения в переменной</span><span class="sxs-lookup"><span data-stu-id="d087d-105">To store a value in a variable</span></span>

- <span data-ttu-id="d087d-106">Используйте имя переменной в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="d087d-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="d087d-107">В следующем примере задается значение переменной `alpha`.</span><span class="sxs-lookup"><span data-stu-id="d087d-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="d087d-108">Значение, созданное в правой части оператора присваивания, хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="d087d-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="d087d-109">Получение данных из переменной</span><span class="sxs-lookup"><span data-stu-id="d087d-109">Getting Data from a Variable</span></span>

<span data-ttu-id="d087d-110">Значение переменной извлекается путем включения имени переменной в выражение.</span><span class="sxs-lookup"><span data-stu-id="d087d-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="d087d-111">Получение значения из переменной</span><span class="sxs-lookup"><span data-stu-id="d087d-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="d087d-112">Используйте имя переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="d087d-112">Use the variable name in an expression.</span></span> <span data-ttu-id="d087d-113">Можно использовать переменную в любом месте, где можно использовать константу или литерал, за исключением выражения, определяющего значение константы.</span><span class="sxs-lookup"><span data-stu-id="d087d-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="d087d-114">\-или-</span><span class="sxs-lookup"><span data-stu-id="d087d-114">\-or-</span></span>

- <span data-ttu-id="d087d-115">Используйте имя переменной после знака равенства (`=`) в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="d087d-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="d087d-116">В следующем примере считывается значение переменной `startValue` , а затем используется значение переменной `counter` в выражении.</span><span class="sxs-lookup"><span data-stu-id="d087d-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="d087d-117">Значение переменной участвует в выражении точно так же, как константа, а затем хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="d087d-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="d087d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d087d-118">See also</span></span>

- [<span data-ttu-id="d087d-119">Переменные</span><span class="sxs-lookup"><span data-stu-id="d087d-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="d087d-120">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="d087d-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="d087d-121">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="d087d-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
