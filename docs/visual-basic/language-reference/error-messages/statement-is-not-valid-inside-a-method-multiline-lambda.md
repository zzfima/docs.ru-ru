---
title: Недопустимая инструкция внутри метода многострочного лямбда-выражения
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef5beea16c8589a884b7d3533e0543454783999
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="60ba0-102">Оператор недопустим в теле метода/многострочного лямбда-оператора</span><span class="sxs-lookup"><span data-stu-id="60ba0-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="60ba0-103">Инструкция не является допустимым в `Sub`, `Function`, свойство `Get`, или свойство `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="60ba0-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="60ba0-104">Некоторые операторы могут размещаться на уровне модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="60ba0-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="60ba0-105">Другие, такие как `Option Strict`, должны быть на уровне пространства имен и перед всеми объявлениями.</span><span class="sxs-lookup"><span data-stu-id="60ba0-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="60ba0-106">**Идентификатор ошибки:** BC30024</span><span class="sxs-lookup"><span data-stu-id="60ba0-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60ba0-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="60ba0-107">To correct this error</span></span>  
  
-   <span data-ttu-id="60ba0-108">Удалите оператор из процедуры.</span><span class="sxs-lookup"><span data-stu-id="60ba0-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ba0-109">См. также</span><span class="sxs-lookup"><span data-stu-id="60ba0-109">See Also</span></span>  
 [<span data-ttu-id="60ba0-110">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="60ba0-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="60ba0-111">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="60ba0-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="60ba0-112">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="60ba0-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="60ba0-113">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="60ba0-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
