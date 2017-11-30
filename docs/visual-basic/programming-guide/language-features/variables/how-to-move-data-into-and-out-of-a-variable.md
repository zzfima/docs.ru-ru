---
title: "Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="08120-102">Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08120-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="08120-103">Сохраните значение в переменной, помещая имя переменной слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="08120-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="08120-104">Размещение данных в переменной</span><span class="sxs-lookup"><span data-stu-id="08120-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="08120-105">Для хранения значений в переменной</span><span class="sxs-lookup"><span data-stu-id="08120-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="08120-106">Используйте имя переменной в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="08120-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="08120-107">В следующем примере задается значение переменной `alpha`.</span><span class="sxs-lookup"><span data-stu-id="08120-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="08120-108">Значение, созданное в правой части оператора присваивания, хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="08120-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="08120-109">Получение данных из переменной</span><span class="sxs-lookup"><span data-stu-id="08120-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="08120-110">Получить значение переменной, включая имя переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="08120-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="08120-111">Для извлечения значения из переменной</span><span class="sxs-lookup"><span data-stu-id="08120-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="08120-112">Используйте имя переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="08120-112">Use the variable name in an expression.</span></span> <span data-ttu-id="08120-113">Можно использовать переменную везде, где можно использовать константу или литерал, за исключением в выражение, определяющее значение константы.</span><span class="sxs-lookup"><span data-stu-id="08120-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="08120-114">-или-</span><span class="sxs-lookup"><span data-stu-id="08120-114">-or-</span></span>  
  
-   <span data-ttu-id="08120-115">Используйте имя переменной после равенства (`=`) войти в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="08120-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="08120-116">В следующем примере считывается значение переменной `startValue` , а затем использует значение переменной `counter` в выражении.</span><span class="sxs-lookup"><span data-stu-id="08120-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="08120-117">Значение переменной участвует в выражении так же, как константа, и затем сохраняются в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="08120-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08120-118">См. также</span><span class="sxs-lookup"><span data-stu-id="08120-118">See Also</span></span>  
 [<span data-ttu-id="08120-119">Переменные</span><span class="sxs-lookup"><span data-stu-id="08120-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="08120-120">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="08120-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="08120-121">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="08120-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
