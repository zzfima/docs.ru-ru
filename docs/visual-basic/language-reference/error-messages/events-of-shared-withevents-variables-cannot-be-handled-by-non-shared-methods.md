---
title: "События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords: BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="a786b-102">События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами</span><span class="sxs-lookup"><span data-stu-id="a786b-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="a786b-103">Переменная, объявленная с `Shared` модификатор — общей переменной.</span><span class="sxs-lookup"><span data-stu-id="a786b-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="a786b-104">Общей переменной определяет только одно место хранения.</span><span class="sxs-lookup"><span data-stu-id="a786b-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="a786b-105">Переменная, объявленная с `WithEvents` модификатор подтверждает, что тип, к которому принадлежит переменная обрабатывает набор событий, вызываемых переменной.</span><span class="sxs-lookup"><span data-stu-id="a786b-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="a786b-106">Когда значение присваивается переменной, свойства, созданные `WithEvents` объявление отсоединяется от любого существующего обработчика событий и подключает обработчик событий через `Add` метод.</span><span class="sxs-lookup"><span data-stu-id="a786b-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="a786b-107">**Идентификатор ошибки:** BC30594</span><span class="sxs-lookup"><span data-stu-id="a786b-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a786b-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a786b-108">To correct this error</span></span>  
  
-   <span data-ttu-id="a786b-109">Объявите обработчик событий `Shared`.</span><span class="sxs-lookup"><span data-stu-id="a786b-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a786b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a786b-110">See Also</span></span>  
 [<span data-ttu-id="a786b-111">Общие</span><span class="sxs-lookup"><span data-stu-id="a786b-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="a786b-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="a786b-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
