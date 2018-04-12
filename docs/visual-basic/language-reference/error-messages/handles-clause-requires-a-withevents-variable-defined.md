---
title: Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e007b371886ab721df6f099e289ea860474c915b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="7e802-102">Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов</span><span class="sxs-lookup"><span data-stu-id="7e802-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>
<span data-ttu-id="7e802-103">Не была предоставлена `WithEvents` переменных в вашей `Handles` предложения.</span><span class="sxs-lookup"><span data-stu-id="7e802-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="7e802-104">`Handles` Вызывает обработки событий, вызванных объектной переменной, объявленной с помощью ключевого слова в конце объявления процедуры `WithEvents` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7e802-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>  
  
 <span data-ttu-id="7e802-105">**Идентификатор ошибки:** BC30506</span><span class="sxs-lookup"><span data-stu-id="7e802-105">**Error ID:** BC30506</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e802-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7e802-106">To correct this error</span></span>  
  
-   <span data-ttu-id="7e802-107">Укажите необходимую `WithEvents` переменной.</span><span class="sxs-lookup"><span data-stu-id="7e802-107">Supply the necessary `WithEvents` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e802-108">См. также</span><span class="sxs-lookup"><span data-stu-id="7e802-108">See Also</span></span>  
 [<span data-ttu-id="7e802-109">Handles</span><span class="sxs-lookup"><span data-stu-id="7e802-109">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
