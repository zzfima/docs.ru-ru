---
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: b3aa66416f0cad6a6fb29a20aa0bca5e3486a18e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275435"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="4b9ff-102">Метод не доступен «Main» с подходящей сигнатурой найден в "\<имя >"</span><span class="sxs-lookup"><span data-stu-id="4b9ff-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="4b9ff-103">Приложения командной строки должны иметь `Sub Main` определен.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="4b9ff-104">`Main` должен быть объявлен как `Public Shared` если оно определено в классе, или как `Public` Если определен в модуле.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="4b9ff-105">**Идентификатор ошибки:** BC30737</span><span class="sxs-lookup"><span data-stu-id="4b9ff-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b9ff-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4b9ff-106">To correct this error</span></span>  
  
-   <span data-ttu-id="4b9ff-107">Определение `Public Sub Main` процедуры для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="4b9ff-108">Он объявляется как `Shared` только в том случае, если она определяется внутри класса.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9ff-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4b9ff-109">See also</span></span>
- [<span data-ttu-id="4b9ff-110">Структура программы на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b9ff-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="4b9ff-111">Процедуры</span><span class="sxs-lookup"><span data-stu-id="4b9ff-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
