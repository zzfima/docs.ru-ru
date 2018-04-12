---
title: Недопустимая инструкция внутри метода многострочного лямбда-выражения
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80673fc7a1497b4148a6505d29581c6403115558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="098b9-102">Оператор недопустим в теле метода/многострочного лямбда-оператора</span><span class="sxs-lookup"><span data-stu-id="098b9-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="098b9-103">Инструкция не является допустимым в `Sub`, `Function`, свойство `Get`, или свойство `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="098b9-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="098b9-104">Некоторые операторы могут размещаться на уровне модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="098b9-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="098b9-105">Другие, такие как `Option Strict`, должны быть на уровне пространства имен и перед всеми объявлениями.</span><span class="sxs-lookup"><span data-stu-id="098b9-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="098b9-106">**Идентификатор ошибки:** BC30024</span><span class="sxs-lookup"><span data-stu-id="098b9-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="098b9-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="098b9-107">To correct this error</span></span>  
  
-   <span data-ttu-id="098b9-108">Удалите оператор из процедуры.</span><span class="sxs-lookup"><span data-stu-id="098b9-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098b9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="098b9-109">See Also</span></span>  
 [<span data-ttu-id="098b9-110">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="098b9-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="098b9-111">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="098b9-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="098b9-112">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="098b9-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="098b9-113">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="098b9-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
