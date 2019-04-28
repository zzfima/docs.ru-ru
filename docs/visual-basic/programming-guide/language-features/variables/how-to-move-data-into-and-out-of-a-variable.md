---
title: Практическое руководство. Перемещение данных в действие и из переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 30d1c0ab91724ac556e59b272782513ee8b8067b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756602"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="52b4a-102">Практическое руководство. Перемещение данных в действие и из переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52b4a-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="52b4a-103">Сохраните значение в переменной, помещая имя переменной в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="52b4a-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="52b4a-104">Размещение данных в переменной</span><span class="sxs-lookup"><span data-stu-id="52b4a-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="52b4a-105">Для хранения значений в переменной</span><span class="sxs-lookup"><span data-stu-id="52b4a-105">To store a value in a variable</span></span>  
  
- <span data-ttu-id="52b4a-106">Используйте имя переменной в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="52b4a-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="52b4a-107">В следующем примере значение переменной `alpha`.</span><span class="sxs-lookup"><span data-stu-id="52b4a-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="52b4a-108">Значение, созданное в правой части оператора присваивания хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="52b4a-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="52b4a-109">Получение данных из переменной</span><span class="sxs-lookup"><span data-stu-id="52b4a-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="52b4a-110">Получить значение переменной, включая имя переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="52b4a-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="52b4a-111">Для извлечения значения из переменной</span><span class="sxs-lookup"><span data-stu-id="52b4a-111">To retrieve a value from a variable</span></span>  
  
- <span data-ttu-id="52b4a-112">Используете имя переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="52b4a-112">Use the variable name in an expression.</span></span> <span data-ttu-id="52b4a-113">Можно использовать переменную везде, где можно использовать константой или литералом, за исключением в выражение, определяющее значение константы.</span><span class="sxs-lookup"><span data-stu-id="52b4a-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="52b4a-114">-или-</span><span class="sxs-lookup"><span data-stu-id="52b4a-114">-or-</span></span>  
  
- <span data-ttu-id="52b4a-115">Использовать имя переменной после равенства (`=`) войдите в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="52b4a-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="52b4a-116">В следующем примере считывается значение переменной `startValue` , а затем использует значение переменной `counter` в выражении.</span><span class="sxs-lookup"><span data-stu-id="52b4a-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="52b4a-117">Значение переменной участвует в выражении, так же, как константа, а затем сохраняется в переменной или свойству в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="52b4a-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b4a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="52b4a-118">See also</span></span>

- [<span data-ttu-id="52b4a-119">Переменные</span><span class="sxs-lookup"><span data-stu-id="52b4a-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="52b4a-120">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="52b4a-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="52b4a-121">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="52b4a-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
