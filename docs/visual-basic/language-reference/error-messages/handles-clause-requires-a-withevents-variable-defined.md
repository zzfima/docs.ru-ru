---
title: Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 291240bade84bcdd3d64dac24c8c91da5ff72d4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649833"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="6550c-102">Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов</span><span class="sxs-lookup"><span data-stu-id="6550c-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>
<span data-ttu-id="6550c-103">Не предоставлен `WithEvents` переменных в вашей `Handles` предложение.</span><span class="sxs-lookup"><span data-stu-id="6550c-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="6550c-104">`Handles` Ключевое слово в конце объявления процедуры приводит к его для обработки событий, вызванных объектной переменной, объявленной с помощью `WithEvents` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6550c-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>  
  
 <span data-ttu-id="6550c-105">**Идентификатор ошибки:** BC30506</span><span class="sxs-lookup"><span data-stu-id="6550c-105">**Error ID:** BC30506</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6550c-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6550c-106">To correct this error</span></span>  
  
- <span data-ttu-id="6550c-107">Укажите необходимую `WithEvents` переменной.</span><span class="sxs-lookup"><span data-stu-id="6550c-107">Supply the necessary `WithEvents` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6550c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6550c-108">See also</span></span>

- [<span data-ttu-id="6550c-109">Handles</span><span class="sxs-lookup"><span data-stu-id="6550c-109">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
