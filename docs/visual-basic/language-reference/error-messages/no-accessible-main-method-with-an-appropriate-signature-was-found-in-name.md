---
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 559c905d1e2e2de4500771a93d6116f9630011ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591981"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="70309-102">Метод не доступен «Main» с подходящей сигнатурой найден в "\<имя >"</span><span class="sxs-lookup"><span data-stu-id="70309-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="70309-103">Приложения командной строки должны иметь `Sub Main` определен.</span><span class="sxs-lookup"><span data-stu-id="70309-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="70309-104">`Main` должен быть объявлен как `Public Shared` если оно определено в классе, или как `Public` Если определен в модуле.</span><span class="sxs-lookup"><span data-stu-id="70309-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="70309-105">**Идентификатор ошибки:** BC30737</span><span class="sxs-lookup"><span data-stu-id="70309-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="70309-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="70309-106">To correct this error</span></span>  
  
- <span data-ttu-id="70309-107">Определение `Public Sub Main` процедуры для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="70309-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="70309-108">Он объявляется как `Shared` только в том случае, если она определяется внутри класса.</span><span class="sxs-lookup"><span data-stu-id="70309-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70309-109">См. также</span><span class="sxs-lookup"><span data-stu-id="70309-109">See also</span></span>

- [<span data-ttu-id="70309-110">Структура программы на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70309-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="70309-111">Процедуры</span><span class="sxs-lookup"><span data-stu-id="70309-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
