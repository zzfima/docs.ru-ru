---
title: Оператор REM (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 3c63c5613b40cb2014c77a0a996e3acb2cc304d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783943"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="8c52c-102">Оператор REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c52c-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="8c52c-103">Используется для включения поясняющими замечаниями в исходном коде программы.</span><span class="sxs-lookup"><span data-stu-id="8c52c-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c52c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c52c-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="8c52c-105">Части</span><span class="sxs-lookup"><span data-stu-id="8c52c-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="8c52c-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8c52c-106">Optional.</span></span> <span data-ttu-id="8c52c-107">Текст комментария, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="8c52c-107">The text of any comment you want to include.</span></span> <span data-ttu-id="8c52c-108">Пробел между `REM` ключевое слово и `comment`.</span><span class="sxs-lookup"><span data-stu-id="8c52c-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c52c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c52c-109">Remarks</span></span>  
 <span data-ttu-id="8c52c-110">Вы можете поместить `REM` инструкции только в строке, или вы можете поместить его в строке после другого оператора.</span><span class="sxs-lookup"><span data-stu-id="8c52c-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="8c52c-111">`REM` Инструкция должна быть последней инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="8c52c-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="8c52c-112">За другого оператора, `REM` должен отделяться от этого оператора пробелом.</span><span class="sxs-lookup"><span data-stu-id="8c52c-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="8c52c-113">Можно использовать одинарную кавычку (`'`) вместо `REM`.</span><span class="sxs-lookup"><span data-stu-id="8c52c-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="8c52c-114">Это верно ли ваш комментарий после другого оператора в той же строке или примечания, занимающего всю строку.</span><span class="sxs-lookup"><span data-stu-id="8c52c-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c52c-115">Не удается продолжить `REM` инструкции с помощью последовательности продолжения строки (`_`).</span><span class="sxs-lookup"><span data-stu-id="8c52c-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="8c52c-116">После начала, компилятор не проверяет символы для специального значения.</span><span class="sxs-lookup"><span data-stu-id="8c52c-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="8c52c-117">Для многострочных комментариев, используйте другой `REM` оператор или символ комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="8c52c-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c52c-118">Пример</span><span class="sxs-lookup"><span data-stu-id="8c52c-118">Example</span></span>  
 <span data-ttu-id="8c52c-119">В следующем примере показано `REM` инструкцию, которая используется для включения поясняющими замечаниями в программе.</span><span class="sxs-lookup"><span data-stu-id="8c52c-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="8c52c-120">Он также демонстрируется использование символа одинарной кавычки (`'`) вместо `REM`.</span><span class="sxs-lookup"><span data-stu-id="8c52c-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8c52c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8c52c-121">See also</span></span>

- [<span data-ttu-id="8c52c-122">Комментарии в коде</span><span class="sxs-lookup"><span data-stu-id="8c52c-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="8c52c-123">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="8c52c-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
