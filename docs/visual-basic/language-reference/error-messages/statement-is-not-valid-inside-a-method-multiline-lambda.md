---
title: Недопустимая инструкция в методе / многострочной лямбде
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 994cafc44a37d16d0f70caec560f530c6a836ec0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841567"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="96eb7-102">Оператор недопустим в теле метода/многострочного лямбда-оператора</span><span class="sxs-lookup"><span data-stu-id="96eb7-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="96eb7-103">Инструкция не является допустимым в `Sub`, `Function`, свойство `Get`, или свойство `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="96eb7-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="96eb7-104">Некоторые инструкции можно поместить на уровне модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="96eb7-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="96eb7-105">Другие, такие как `Option Strict`должны быть на уровне пространства имен и должны предшествовать всем объявлениям.</span><span class="sxs-lookup"><span data-stu-id="96eb7-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="96eb7-106">**Идентификатор ошибки:** BC30024</span><span class="sxs-lookup"><span data-stu-id="96eb7-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96eb7-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="96eb7-107">To correct this error</span></span>  
  
-   <span data-ttu-id="96eb7-108">Удалите оператор из процедуры.</span><span class="sxs-lookup"><span data-stu-id="96eb7-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96eb7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="96eb7-109">See also</span></span>

- [<span data-ttu-id="96eb7-110">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="96eb7-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="96eb7-111">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="96eb7-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="96eb7-112">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="96eb7-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="96eb7-113">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="96eb7-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
