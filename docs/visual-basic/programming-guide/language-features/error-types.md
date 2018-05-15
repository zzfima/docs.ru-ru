---
title: Типы ошибок (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: c11b7f41dee57fc52ca1dff75734ad0b27b6a43a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="59960-102">Типы ошибок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59960-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="59960-103">В Visual Basic, ошибок (также называемый *исключения*) делятся на три категории: синтаксические ошибки, ошибки времени выполнения и логические ошибки.</span><span class="sxs-lookup"><span data-stu-id="59960-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="59960-104">Синтаксические ошибки</span><span class="sxs-lookup"><span data-stu-id="59960-104">Syntax Errors</span></span>  
 <span data-ttu-id="59960-105">*Синтаксические ошибки* являются те, которые отображаются во время написания кода.</span><span class="sxs-lookup"><span data-stu-id="59960-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="59960-106">Visual Basic проверяет код при вводе в **редактор кода** окна и оповещает пользователя в случае ошибки, например неправильное написание слова или неправильное использование элемента языка.</span><span class="sxs-lookup"><span data-stu-id="59960-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="59960-107">Синтаксические ошибки являются наиболее распространенным типом ошибки.</span><span class="sxs-lookup"><span data-stu-id="59960-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="59960-108">Их легко исправить в среде кодирования по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="59960-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59960-109">`Option Explicit` Инструкция является одним из средств предотвращения синтаксических ошибок.</span><span class="sxs-lookup"><span data-stu-id="59960-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="59960-110">Он заставляет можно объявить, заранее, все переменные для использования в приложении.</span><span class="sxs-lookup"><span data-stu-id="59960-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="59960-111">Таким образом Если эти переменные используются в коде, опечатки немедленно обнаруживаются и могут быть исправлены.</span><span class="sxs-lookup"><span data-stu-id="59960-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="59960-112">Ошибки во время выполнения</span><span class="sxs-lookup"><span data-stu-id="59960-112">Run-Time Errors</span></span>  
 <span data-ttu-id="59960-113">*Ошибки во время выполнения* являются те, которые отображаются только после компиляции и выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="59960-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="59960-114">Они включают код, который может указаны правильно, он не содержат синтаксических ошибок, но не выполняются.</span><span class="sxs-lookup"><span data-stu-id="59960-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="59960-115">Например может правильно написать строку кода для открытия файла.</span><span class="sxs-lookup"><span data-stu-id="59960-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="59960-116">Но если файл поврежден, приложение не может выполнить `Open` функции и будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="59960-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="59960-117">Вы можете исправить большинство ошибок времени выполнения, переписав ошибочный код и перекомпилировать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="59960-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="59960-118">Логические ошибки</span><span class="sxs-lookup"><span data-stu-id="59960-118">Logic Errors</span></span>  
 <span data-ttu-id="59960-119">*Логические ошибки* — это те, которые выявляются приложения уже используется.</span><span class="sxs-lookup"><span data-stu-id="59960-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="59960-120">Они являются большинства часто нежелательных или непредвиденных результатов в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="59960-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="59960-121">Например, ошибочное нажатие клавиши или другое внешнее воздействие может вызвать прекращение работы в ожидаемом приложения или вообще.</span><span class="sxs-lookup"><span data-stu-id="59960-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="59960-122">Логические ошибки обычно являются наиболее сложно исправить, так как не всегда ясно их происхождение.</span><span class="sxs-lookup"><span data-stu-id="59960-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59960-123">См. также</span><span class="sxs-lookup"><span data-stu-id="59960-123">See Also</span></span>  
 [<span data-ttu-id="59960-124">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="59960-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="59960-125">Основы отладки</span><span class="sxs-lookup"><span data-stu-id="59960-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
