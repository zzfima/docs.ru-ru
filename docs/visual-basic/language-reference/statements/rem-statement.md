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
ms.openlocfilehash: 729d0710d65c0cda750061e72309ced527bbcfe7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582061"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="8f2a5-102">Оператор REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f2a5-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="8f2a5-103">Используется для включения пояснительных примечаний в исходный код программы.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f2a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f2a5-104">Syntax</span></span>  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="8f2a5-105">Части</span><span class="sxs-lookup"><span data-stu-id="8f2a5-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="8f2a5-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-106">Optional.</span></span> <span data-ttu-id="8f2a5-107">Текст любого комментария, который требуется включить.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-107">The text of any comment you want to include.</span></span> <span data-ttu-id="8f2a5-108">Между ключевым словом `REM` и `comment` требуется пробел.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f2a5-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="8f2a5-109">Remarks</span></span>  
 <span data-ttu-id="8f2a5-110">Инструкцию `REM` можно добавить только в строку или вставить в строку, следующую за другой инструкцией.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="8f2a5-111">Оператор `REM` должен быть последним оператором в строке.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="8f2a5-112">Если он соответствует другому оператору, `REM` должен быть отделен от этого оператора пробелами.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="8f2a5-113">Вместо `REM` можно использовать одиночную кавычку (`'`).</span><span class="sxs-lookup"><span data-stu-id="8f2a5-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="8f2a5-114">Это верно, если ваш комментарий следует другому оператору в той же строке или расподержаться только в строке.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f2a5-115">Нельзя продолжить инструкцию `REM` с помощью последовательности продолжения строки (`_`).</span><span class="sxs-lookup"><span data-stu-id="8f2a5-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="8f2a5-116">После начала комментария компилятор не проверяет символы на предмет особого значения.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="8f2a5-117">Для многострочного комментария используйте другой оператор `REM` или символ комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f2a5-118">Пример</span><span class="sxs-lookup"><span data-stu-id="8f2a5-118">Example</span></span>  
 <span data-ttu-id="8f2a5-119">В следующем примере показана инструкция `REM`, которая используется для включения пояснительных примечаний в программу.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="8f2a5-120">Кроме того, в нем показано использование одинарной кавычки (`'`) вместо `REM`.</span><span class="sxs-lookup"><span data-stu-id="8f2a5-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8f2a5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8f2a5-121">See also</span></span>

- [<span data-ttu-id="8f2a5-122">Комментарии в коде</span><span class="sxs-lookup"><span data-stu-id="8f2a5-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="8f2a5-123">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="8f2a5-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
