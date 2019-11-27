---
title: Недостаточно места для стека
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 9ae604a9727413f2705d42a4b68f5a50b7dd3feb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349181"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="50b7a-102">Отсутствует место в стеке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50b7a-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="50b7a-103">Стек — это Рабочая область памяти, которая динамически растет и сжимается с учетом требований к выполненной программе.</span><span class="sxs-lookup"><span data-stu-id="50b7a-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="50b7a-104">Превышены его ограничения.</span><span class="sxs-lookup"><span data-stu-id="50b7a-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="50b7a-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="50b7a-105">To correct this error</span></span>  
  
1. <span data-ttu-id="50b7a-106">Убедитесь, что процедуры не вложены слишком глубоко.</span><span class="sxs-lookup"><span data-stu-id="50b7a-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="50b7a-107">Убедитесь, что рекурсивные процедуры завершаются должным образом.</span><span class="sxs-lookup"><span data-stu-id="50b7a-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="50b7a-108">Если локальным переменным требуется больше пространства локальных переменных, чем доступно, попробуйте объявить некоторые переменные на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="50b7a-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="50b7a-109">Кроме того, можно объявить все переменные в процедуре статически, выполнив ключевое слово `Property`, `Sub`или `Function` с `Static`.</span><span class="sxs-lookup"><span data-stu-id="50b7a-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="50b7a-110">Или можно использовать инструкцию `Static` для объявления отдельных статических переменных в процедурах.</span><span class="sxs-lookup"><span data-stu-id="50b7a-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="50b7a-111">Переопределите некоторые строки фиксированной длины как строки переменной длины, так как строки фиксированной длины используют больше пространства стека, чем строки переменной длины.</span><span class="sxs-lookup"><span data-stu-id="50b7a-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="50b7a-112">Можно также определить строку на уровне модуля, где не требуется пространство стека.</span><span class="sxs-lookup"><span data-stu-id="50b7a-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="50b7a-113">Проверьте число вложенных вызовов функций `DoEvents`, используя диалоговое окно `Calls` для просмотра активных процедур в стеке.</span><span class="sxs-lookup"><span data-stu-id="50b7a-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="50b7a-114">Убедитесь, что вы не вызвали "каскадное событие", активируя событие, которое вызывает процедуру события, уже называемую в стеке.</span><span class="sxs-lookup"><span data-stu-id="50b7a-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="50b7a-115">Каскад событий аналогичен вызову незавершенной рекурсивной процедуры, но он менее очевидн, так как вызов выполняется Visual Basic а не явным вызовом в коде.</span><span class="sxs-lookup"><span data-stu-id="50b7a-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="50b7a-116">Используйте диалоговое окно `Calls` для просмотра активных процедур в стеке.</span><span class="sxs-lookup"><span data-stu-id="50b7a-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b7a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="50b7a-117">See also</span></span>

- [<span data-ttu-id="50b7a-118">Окно памяти</span><span class="sxs-lookup"><span data-stu-id="50b7a-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
