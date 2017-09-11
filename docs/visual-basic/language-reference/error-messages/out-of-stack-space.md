---
title: "Место (Visual Basic) в стеке | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 256ef0c7fcb3632e0c13d12737d438225343884f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="0c650-102">Отсутствует место в стеке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c650-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="0c650-103">Стек — это рабочая область памяти, увеличивается и уменьшается динамически с требованиями выполняемой программы.</span><span class="sxs-lookup"><span data-stu-id="0c650-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="0c650-104">Предел был превышен.</span><span class="sxs-lookup"><span data-stu-id="0c650-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0c650-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0c650-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="0c650-106">Проверьте, что процедуры не вложены слишком глубоко.</span><span class="sxs-lookup"><span data-stu-id="0c650-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="0c650-107">Убедитесь, что рекурсивные процедуры завершаются должным образом.</span><span class="sxs-lookup"><span data-stu-id="0c650-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="0c650-108">Если для локальных переменных недостаточно места, чем доступно, объявите некоторые переменные на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="0c650-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="0c650-109">Можно также объявить все переменные в процедуре статических перед `Property`, `Sub`, или `Function` ключевого слова with `Static`.</span><span class="sxs-lookup"><span data-stu-id="0c650-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="0c650-110">Или можно использовать `Static` инструкции для объявления в процедурах отдельных статических переменных.</span><span class="sxs-lookup"><span data-stu-id="0c650-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="0c650-111">Переопределите некоторые строки фиксированной длины как строки переменной длины, как строки фиксированной длины используют большее пространство стека, чем строки с переменной длиной.</span><span class="sxs-lookup"><span data-stu-id="0c650-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="0c650-112">Можно также определить строку на уровне модуля, где требуется пространство стека.</span><span class="sxs-lookup"><span data-stu-id="0c650-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="0c650-113">Проверьте число вложенных `DoEvents` вызовы функций, с помощью `Calls` диалоговое окно просмотра процедур, действующих в стеке.</span><span class="sxs-lookup"><span data-stu-id="0c650-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="0c650-114">Убедитесь, что не был запущен «Каскад событий» путем активации события, вызывающего процедуру события уже в стеке.</span><span class="sxs-lookup"><span data-stu-id="0c650-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="0c650-115">Каскад событий похож на вызов незаконченной рекурсивной процедуры, но это заметен, поскольку вызов выполняется системой [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вместо явного вызова в коде.</span><span class="sxs-lookup"><span data-stu-id="0c650-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="0c650-116">Используйте `Calls`диалоговое окно просмотра процедур, действующих в стеке.</span><span class="sxs-lookup"><span data-stu-id="0c650-116">Use the `Calls`dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c650-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0c650-117">See Also</span></span>  
 [<span data-ttu-id="0c650-118">Окно памяти</span><span class="sxs-lookup"><span data-stu-id="0c650-118">Memory Windows</span></span>](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
