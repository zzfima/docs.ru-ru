---
title: Ни один из доступных &#39;Main&#39; найден метод с соответствующей сигнатурой в &#39; &lt;имя&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593224"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="a747f-102">Ни один из доступных &#39;Main&#39; найден метод с соответствующей сигнатурой в &#39; &lt;имя&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="a747f-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="a747f-103">Приложения командной строки должны иметь `Sub Main` определен.</span><span class="sxs-lookup"><span data-stu-id="a747f-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="a747f-104">`Main` должен быть объявлен как `Public Shared` , если оно определено в классе или как `Public` , если определено в модуле.</span><span class="sxs-lookup"><span data-stu-id="a747f-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="a747f-105">**Идентификатор ошибки:** BC30737</span><span class="sxs-lookup"><span data-stu-id="a747f-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a747f-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a747f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="a747f-107">Определение `Public Sub Main` процедуры для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="a747f-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="a747f-108">Он объявляется как `Shared` только в том случае, если она определяется внутри класса.</span><span class="sxs-lookup"><span data-stu-id="a747f-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a747f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a747f-109">See Also</span></span>  
 [<span data-ttu-id="a747f-110">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a747f-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="a747f-111">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a747f-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
