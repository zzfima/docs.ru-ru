---
title: Ни один из доступных &#39;Main&#39; в найден метод с подходящей сигнатурой &#39; &lt;имя&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501494"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="7f420-102">Ни один из доступных &#39;Main&#39; в найден метод с подходящей сигнатурой &#39; &lt;имя&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="7f420-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="7f420-103">Приложения командной строки должны иметь `Sub Main` определен.</span><span class="sxs-lookup"><span data-stu-id="7f420-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="7f420-104">`Main` должен быть объявлен как `Public Shared` если оно определено в классе, или как `Public` Если определен в модуле.</span><span class="sxs-lookup"><span data-stu-id="7f420-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="7f420-105">**Идентификатор ошибки:** BC30737</span><span class="sxs-lookup"><span data-stu-id="7f420-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7f420-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7f420-106">To correct this error</span></span>  
  
-   <span data-ttu-id="7f420-107">Определение `Public Sub Main` процедуры для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="7f420-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="7f420-108">Он объявляется как `Shared` только в том случае, если она определяется внутри класса.</span><span class="sxs-lookup"><span data-stu-id="7f420-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f420-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7f420-109">See also</span></span>
- [<span data-ttu-id="7f420-110">Структура программы на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f420-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="7f420-111">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7f420-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
