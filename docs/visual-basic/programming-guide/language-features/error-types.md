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
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831570"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="8995b-102">Типы ошибок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8995b-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="8995b-103">В Visual Basic, ошибок (также называется *исключения*) делятся на три категории: синтаксические ошибки, ошибки времени выполнения и логических ошибок.</span><span class="sxs-lookup"><span data-stu-id="8995b-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="8995b-104">Синтаксические ошибки</span><span class="sxs-lookup"><span data-stu-id="8995b-104">Syntax Errors</span></span>  
 <span data-ttu-id="8995b-105">*Синтаксические ошибки* являются те, которые при написании кода.</span><span class="sxs-lookup"><span data-stu-id="8995b-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="8995b-106">Visual Basic проверяет код, при вводе в **редактор кода** окна и оповещает вас, если вы сделаете ошибку, такие как неправильное написание слова или неправильное использование элементом языка.</span><span class="sxs-lookup"><span data-stu-id="8995b-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="8995b-107">Синтаксические ошибки являются наиболее распространенным типом ошибок.</span><span class="sxs-lookup"><span data-stu-id="8995b-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="8995b-108">Их легко исправить в среду программирования по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="8995b-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8995b-109">`Option Explicit` Инструкция является одним из средств предотвращения синтаксических ошибок.</span><span class="sxs-lookup"><span data-stu-id="8995b-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="8995b-110">Принудительно объявлять, заранее, все переменные, используемые в приложении.</span><span class="sxs-lookup"><span data-stu-id="8995b-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="8995b-111">Таким образом Если эти переменные используются в коде, опечатки немедленно обнаруживаются и могут быть исправлены.</span><span class="sxs-lookup"><span data-stu-id="8995b-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="8995b-112">Ошибки времени выполнения</span><span class="sxs-lookup"><span data-stu-id="8995b-112">Run-Time Errors</span></span>  
 <span data-ttu-id="8995b-113">*Ошибки времени выполнения* являются те, которые отображаются только в том случае, после компиляции и выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="8995b-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="8995b-114">Они могут вызывать код, который может указаны правильно, он имеет нет синтаксических ошибок, но не выполняются.</span><span class="sxs-lookup"><span data-stu-id="8995b-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="8995b-115">Например можно правильно написать строку кода для открытия файла.</span><span class="sxs-lookup"><span data-stu-id="8995b-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="8995b-116">Но если файл поврежден, приложение не может выполнить `Open` функции и будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="8995b-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="8995b-117">Вы можете исправить большинство ошибок времени выполнения, переписав ошибочный код и повторной компиляции и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="8995b-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="8995b-118">Логические ошибки</span><span class="sxs-lookup"><span data-stu-id="8995b-118">Logic Errors</span></span>  
 <span data-ttu-id="8995b-119">*Логические ошибки* являются те, которые проявляются, когда приложение уже используется.</span><span class="sxs-lookup"><span data-stu-id="8995b-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="8995b-120">Они являются большинства часто нежелательные или непредвиденные результаты, в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="8995b-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="8995b-121">Например, ошибочное нажатие клавиши или другое внешнее воздействие может вызвать приложения работают в пределах ожидаемых параметров или полностью.</span><span class="sxs-lookup"><span data-stu-id="8995b-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="8995b-122">Логические ошибки чаще всего это самый сложный тип, чтобы устранить проблему, так как он не всегда ясно их происхождение.</span><span class="sxs-lookup"><span data-stu-id="8995b-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8995b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8995b-123">See also</span></span>

- [<span data-ttu-id="8995b-124">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="8995b-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="8995b-125">Основы отладки</span><span class="sxs-lookup"><span data-stu-id="8995b-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
