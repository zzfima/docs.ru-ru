---
title: "Оператор REM (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="6ddda-102">Оператор REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ddda-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="6ddda-103">Используется для включения поясняющий текст в исходном коде программы.</span><span class="sxs-lookup"><span data-stu-id="6ddda-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ddda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ddda-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="6ddda-105">Части</span><span class="sxs-lookup"><span data-stu-id="6ddda-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="6ddda-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="6ddda-106">Optional.</span></span> <span data-ttu-id="6ddda-107">Текст комментария, который требуется включить.</span><span class="sxs-lookup"><span data-stu-id="6ddda-107">The text of any comment you want to include.</span></span> <span data-ttu-id="6ddda-108">Пробел требуется между `REM` ключевое слово и `comment`.</span><span class="sxs-lookup"><span data-stu-id="6ddda-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ddda-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ddda-109">Remarks</span></span>  
 <span data-ttu-id="6ddda-110">Можно поместить `REM` инструкции только в строке, или можно поместить в строке за другим оператором.</span><span class="sxs-lookup"><span data-stu-id="6ddda-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="6ddda-111">`REM` Инструкция должна быть последней инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="6ddda-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="6ddda-112">За инструкцией, `REM` должно отделяться от этого оператора пробелом.</span><span class="sxs-lookup"><span data-stu-id="6ddda-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="6ddda-113">Можно использовать одинарную кавычку (`'`) вместо `REM`.</span><span class="sxs-lookup"><span data-stu-id="6ddda-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="6ddda-114">Это верно ли примечания, следующего за другим оператором в той же строке, и примечания, занимающего всю строку.</span><span class="sxs-lookup"><span data-stu-id="6ddda-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ddda-115">Не удается продолжить `REM` инструкции можно использовать последовательность продолжения строки (`_`).</span><span class="sxs-lookup"><span data-stu-id="6ddda-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="6ddda-116">После начала, компилятор не проверяет символы для особое значение.</span><span class="sxs-lookup"><span data-stu-id="6ddda-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="6ddda-117">Для многострочных комментариев, используйте другой `REM` оператор или символ комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="6ddda-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ddda-118">Пример</span><span class="sxs-lookup"><span data-stu-id="6ddda-118">Example</span></span>  
 <span data-ttu-id="6ddda-119">В следующем примере демонстрируется `REM` инструкцию, которая используется для включения пояснения в программе.</span><span class="sxs-lookup"><span data-stu-id="6ddda-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="6ddda-120">Он также демонстрируется использование символа одинарной кавычки (`'`) вместо `REM`.</span><span class="sxs-lookup"><span data-stu-id="6ddda-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6ddda-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6ddda-121">See Also</span></span>  
 [<span data-ttu-id="6ddda-122">Комментарии в коде</span><span class="sxs-lookup"><span data-stu-id="6ddda-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="6ddda-123">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="6ddda-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
