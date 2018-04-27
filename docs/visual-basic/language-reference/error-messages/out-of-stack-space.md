---
title: Отсутствует место в стеке (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec839d1f0ad1931ed4229e898a900c3210d813ed
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="38e15-102">Отсутствует место в стеке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38e15-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="38e15-103">Стек — это рабочая область памяти, который увеличивается и уменьшается динамически с запросами большого количества выполняемой программы.</span><span class="sxs-lookup"><span data-stu-id="38e15-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="38e15-104">Предел был превышен.</span><span class="sxs-lookup"><span data-stu-id="38e15-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="38e15-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="38e15-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="38e15-106">Проверьте, что процедуры не вложены слишком глубоко.</span><span class="sxs-lookup"><span data-stu-id="38e15-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="38e15-107">Убедитесь, что рекурсивные процедуры завершаются должным образом.</span><span class="sxs-lookup"><span data-stu-id="38e15-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="38e15-108">Если для локальных переменных недостаточно места, чем доступно, объявите некоторые переменные на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="38e15-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="38e15-109">Можно также объявить все переменные в процедуре статические, поставив в начале `Property`, `Sub`, или `Function` ключевого слова with `Static`.</span><span class="sxs-lookup"><span data-stu-id="38e15-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="38e15-110">Или можно использовать `Static` инструкции для объявления в процедурах отдельных статических переменных.</span><span class="sxs-lookup"><span data-stu-id="38e15-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="38e15-111">Переопределите некоторые строки фиксированной длины как строки переменной длины, как строки фиксированной длины используют большее пространство стека, чем строки переменной длины.</span><span class="sxs-lookup"><span data-stu-id="38e15-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="38e15-112">Можно также определить строку на уровне модуля, где требуется пространство стека.</span><span class="sxs-lookup"><span data-stu-id="38e15-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="38e15-113">Проверьте число вложенных `DoEvents` вызовы функций, с помощью `Calls` диалоговым окном просмотра процедур, активных в стеке.</span><span class="sxs-lookup"><span data-stu-id="38e15-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="38e15-114">Убедитесь, что не был запущен «Каскад событий» путем активации события, вызывающего процедуру уже в стеке.</span><span class="sxs-lookup"><span data-stu-id="38e15-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="38e15-115">Каскад событий аналогичен незавершенный рекурсивный вызов процедуры, но он не заметен, поскольку вызов Visual Basic, а не явным вызовом в коде.</span><span class="sxs-lookup"><span data-stu-id="38e15-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="38e15-116">Используйте `Calls` диалоговым окном просмотра процедур, активных в стеке.</span><span class="sxs-lookup"><span data-stu-id="38e15-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e15-117">См. также</span><span class="sxs-lookup"><span data-stu-id="38e15-117">See Also</span></span>  
 [<span data-ttu-id="38e15-118">Окно памяти</span><span class="sxs-lookup"><span data-stu-id="38e15-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
