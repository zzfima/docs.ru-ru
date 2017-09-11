---
title: "Комментарии в коде (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Uncomment button
- REM statement
- comments, in code
- comments, Visual Basic code
- Comment button
- buttons, Uncomment
- buttons, Comment
- code comments, Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: 17
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
ms.openlocfilehash: e872c9bb67835573aadcc1016f2c6a98d434201e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="3a0db-102">Комментарии в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a0db-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="3a0db-103">В примерах кодов часто встречается символ начала комментария (`'`).</span><span class="sxs-lookup"><span data-stu-id="3a0db-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="3a0db-104">Этот символ дает [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятору инструкцию проигнорировать последующий текст, или *комментарий*.</span><span class="sxs-lookup"><span data-stu-id="3a0db-104">This symbol tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="3a0db-105">Комментарии — это краткие заметки, внесенные в код, чтобы сделать чтение кода более легким.</span><span class="sxs-lookup"><span data-stu-id="3a0db-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="3a0db-106">Хорошим стилем программирования считается начинать все процедуры с краткого комментария, описывающего функциональные характеристики процедуры (то, что она делает).</span><span class="sxs-lookup"><span data-stu-id="3a0db-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="3a0db-107">Это необходимо для вашего собственного удобства и удобства того, кто читает этот код.</span><span class="sxs-lookup"><span data-stu-id="3a0db-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="3a0db-108">Следует отличать детали реализации (как процедура работает) от комментариев, описывающих функциональные характеристики.</span><span class="sxs-lookup"><span data-stu-id="3a0db-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="3a0db-109">Если в комментарий включены детали реализации, их следует обновлять при редактировании кода.</span><span class="sxs-lookup"><span data-stu-id="3a0db-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="3a0db-110">Комментарии могут располагаться в конце той же строки, где содержится оператор, или занимать отдельную строку.</span><span class="sxs-lookup"><span data-stu-id="3a0db-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="3a0db-111">Оба способа представлены в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="3a0db-111">Both are illustrated in the following code.</span></span>  
  
 <span data-ttu-id="3a0db-112">[!code-vb[VbVbcnConventions №&16;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3a0db-112">[!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="3a0db-113">Если комментарий занимает более одной строки, каждая строка должна начинаться с символа начала комментария, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3a0db-113">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 <span data-ttu-id="3a0db-114">[!code-vb[VbVbcnConventions&17;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="3a0db-114">[!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]</span></span>  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="3a0db-115">Правила комментирования</span><span class="sxs-lookup"><span data-stu-id="3a0db-115">Commenting Guidelines</span></span>  
 <span data-ttu-id="3a0db-116">В следующей таблице приведены общие рекомендации по тому, какие типы комментариев могут предшествовать разделу кода.</span><span class="sxs-lookup"><span data-stu-id="3a0db-116">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="3a0db-117">Данная информация носит рекомендательный характер; в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] нет жестких норм, касающихся добавления комментариев.</span><span class="sxs-lookup"><span data-stu-id="3a0db-117">These are suggestions; [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not enforce rules for adding comments.</span></span> <span data-ttu-id="3a0db-118">В комментарий по желанию автора кода может быть включена любая информация.</span><span class="sxs-lookup"><span data-stu-id="3a0db-118">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="3a0db-119">Тип комментария</span><span class="sxs-lookup"><span data-stu-id="3a0db-119">Comment type</span></span>|<span data-ttu-id="3a0db-120">Описание комментария</span><span class="sxs-lookup"><span data-stu-id="3a0db-120">Comment description</span></span>|  
|<span data-ttu-id="3a0db-121">Назначение</span><span class="sxs-lookup"><span data-stu-id="3a0db-121">Purpose</span></span>|<span data-ttu-id="3a0db-122">Описание действий, совершаемых процедурой (но не того, каким образом совершаются эти действия)</span><span class="sxs-lookup"><span data-stu-id="3a0db-122">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="3a0db-123">Допущения</span><span class="sxs-lookup"><span data-stu-id="3a0db-123">Assumptions</span></span>|<span data-ttu-id="3a0db-124">Список всех внешних переменных, элементов управления, открытых файлов, к которым осуществляется доступ из процедуры </span><span class="sxs-lookup"><span data-stu-id="3a0db-124">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="3a0db-125">Произведенный эффект</span><span class="sxs-lookup"><span data-stu-id="3a0db-125">Effects</span></span>|<span data-ttu-id="3a0db-126">Список внешних переменных, элементов управления или файлов, на которые влияет данная процедура (если это влияние не очевидно)</span><span class="sxs-lookup"><span data-stu-id="3a0db-126">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="3a0db-127">Inputs</span><span class="sxs-lookup"><span data-stu-id="3a0db-127">Inputs</span></span>|<span data-ttu-id="3a0db-128">Описание назначения аргументов</span><span class="sxs-lookup"><span data-stu-id="3a0db-128">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="3a0db-129">Returns</span><span class="sxs-lookup"><span data-stu-id="3a0db-129">Returns</span></span>|<span data-ttu-id="3a0db-130">Описание значений, возвращаемых процедурой</span><span class="sxs-lookup"><span data-stu-id="3a0db-130">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="3a0db-131">Также рекомендуется принять во внимание следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="3a0db-131">Remember the following points:</span></span>  
  
-   <span data-ttu-id="3a0db-132">Объявление каждой важной переменной должно предшествовать комментарию, описывающему ее назначение.</span><span class="sxs-lookup"><span data-stu-id="3a0db-132">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
-   <span data-ttu-id="3a0db-133">Имена переменных, элементов управления и процедур должны быть функционально понятными, чтобы комментарии требовались только в случае особо сложных деталей реализации.</span><span class="sxs-lookup"><span data-stu-id="3a0db-133">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
-   <span data-ttu-id="3a0db-134">Комментарии не могут располагаться за последовательностью продолжения строки в той же строке.</span><span class="sxs-lookup"><span data-stu-id="3a0db-134">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="3a0db-135">Можно добавить или удалить символы комментария для блок кода, выбрав одну или несколько строк кода и выбрав **комментарий** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) и **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) кнопки на **изменить** инструментов.</span><span class="sxs-lookup"><span data-stu-id="3a0db-135">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) and **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a0db-136">Кроме того, можно добавить в код комментарии, поставив в начале текста ключевое слово `REM`.</span><span class="sxs-lookup"><span data-stu-id="3a0db-136">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="3a0db-137">Тем не менее `'` символов и **комментарий**/**Uncomment** кнопки легче использовать и требует меньше места и памяти.</span><span class="sxs-lookup"><span data-stu-id="3a0db-137">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a0db-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3a0db-138">See Also</span></span>  
 <span data-ttu-id="3a0db-139">[Документирование кода с комментариями XML](http://msdn.microsoft.com/magazine/dd722812.aspx) </span><span class="sxs-lookup"><span data-stu-id="3a0db-139">[Documenting Your Code With XML Comments](http://msdn.microsoft.com/magazine/dd722812.aspx) </span></span>  
<span data-ttu-id="3a0db-140"> [Практическое руководство: Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="3a0db-140"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md) </span></span>  
<span data-ttu-id="3a0db-141"> [Теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="3a0db-141"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="3a0db-142"> [Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="3a0db-142"> [Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="3a0db-143"> [Оператор REM](../../../visual-basic/language-reference/statements/rem-statement.md)</span><span class="sxs-lookup"><span data-stu-id="3a0db-143"> [REM Statement](../../../visual-basic/language-reference/statements/rem-statement.md)</span></span>
