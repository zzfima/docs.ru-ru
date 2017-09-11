---
title: "Типы ошибок (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
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
ms.openlocfilehash: 51cf5820e79ff9467357619d4f5b067bc4168bfb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="error-types-visual-basic"></a><span data-ttu-id="eee8e-102">Типы ошибок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eee8e-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="eee8e-103">В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], ошибки (также называемый *исключения*) делятся на три категории: синтаксические ошибки, ошибки времени выполнения и логических ошибок.</span><span class="sxs-lookup"><span data-stu-id="eee8e-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="eee8e-104">Синтаксические ошибки</span><span class="sxs-lookup"><span data-stu-id="eee8e-104">Syntax Errors</span></span>  
 <span data-ttu-id="eee8e-105">*Синтаксические ошибки* те, которые появляются при написании кода.</span><span class="sxs-lookup"><span data-stu-id="eee8e-105">*Syntax errors* are those that appear while you write code.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="eee8e-106">проверяет код при вводе в **редактор кода** окна и предупредит вас, если вы сделаете ошибку, например, неправильное написание слова или неправильное использование элемента языка.</span><span class="sxs-lookup"><span data-stu-id="eee8e-106"> checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="eee8e-107">Синтаксические ошибки являются наиболее распространенным типом ошибки.</span><span class="sxs-lookup"><span data-stu-id="eee8e-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="eee8e-108">Их легко исправить в среде кодирования по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="eee8e-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eee8e-109">`Option Explicit` Инструкция является одним из средств предотвращения синтаксических ошибок.</span><span class="sxs-lookup"><span data-stu-id="eee8e-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="eee8e-110">Принудительно объявлять, заранее, все переменные для использования в приложении.</span><span class="sxs-lookup"><span data-stu-id="eee8e-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="eee8e-111">Таким образом когда эти переменные используются в коде, опечатки немедленно обнаруживаются и могут быть исправлены.</span><span class="sxs-lookup"><span data-stu-id="eee8e-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="eee8e-112">Ошибки во время выполнения</span><span class="sxs-lookup"><span data-stu-id="eee8e-112">Run-Time Errors</span></span>  
 <span data-ttu-id="eee8e-113">*Ошибки во время выполнения* те, которые отображаются только после компиляции и выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="eee8e-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="eee8e-114">Они включают в себя код, который может отображаться правильно, он не содержат синтаксических ошибок, но не выполняются.</span><span class="sxs-lookup"><span data-stu-id="eee8e-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="eee8e-115">Например может правильно написать строку кода для открытия файла.</span><span class="sxs-lookup"><span data-stu-id="eee8e-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="eee8e-116">Но если файл поврежден, приложение не может выполнить `Open` функции и будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="eee8e-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="eee8e-117">Большинство ошибок времени выполнения можно устранить, переписав ошибочный код и перекомпилировать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="eee8e-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="eee8e-118">Логические ошибки</span><span class="sxs-lookup"><span data-stu-id="eee8e-118">Logic Errors</span></span>  
 <span data-ttu-id="eee8e-119">*Логические ошибки* те, которые выявляются при использования приложения.</span><span class="sxs-lookup"><span data-stu-id="eee8e-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="eee8e-120">Они являются большинство часто нежелательных или непредвиденных результатов в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="eee8e-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="eee8e-121">Например, ошибочное нажатие клавиши или другое внешнее воздействие может вызвать прекращение работы в ожидаемом приложения или вообще.</span><span class="sxs-lookup"><span data-stu-id="eee8e-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="eee8e-122">Логические ошибки — обычно наиболее сложно исправить, так как он не всегда ясно их происхождение.</span><span class="sxs-lookup"><span data-stu-id="eee8e-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee8e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="eee8e-123">See Also</span></span>  
 <span data-ttu-id="eee8e-124">[Оператор Try... Catch... Finally (Visual Basic)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="eee8e-124">[Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
<span data-ttu-id="eee8e-125"> [Основы отладки](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span><span class="sxs-lookup"><span data-stu-id="eee8e-125"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span></span>
