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
ms.openlocfilehash: 16149ce42e3476cf07a62298f83734fee9ec7253
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957763"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="ed3de-102">Оператор REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed3de-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="ed3de-103">Используется для включения пояснительных примечаний в исходный код программы.</span><span class="sxs-lookup"><span data-stu-id="ed3de-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed3de-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="ed3de-105">Части</span><span class="sxs-lookup"><span data-stu-id="ed3de-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="ed3de-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ed3de-106">Optional.</span></span> <span data-ttu-id="ed3de-107">Текст любого комментария, который требуется включить.</span><span class="sxs-lookup"><span data-stu-id="ed3de-107">The text of any comment you want to include.</span></span> <span data-ttu-id="ed3de-108">Между `REM` ключевым словом и `comment`должен быть пробел.</span><span class="sxs-lookup"><span data-stu-id="ed3de-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed3de-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed3de-109">Remarks</span></span>  
 <span data-ttu-id="ed3de-110">`REM` Оператор можно разместить только в строке или вставить в строку, следующую за другой инструкцией.</span><span class="sxs-lookup"><span data-stu-id="ed3de-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="ed3de-111">`REM` Оператор должен быть последним оператором в строке.</span><span class="sxs-lookup"><span data-stu-id="ed3de-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="ed3de-112">Если он соответствует другому оператору, `REM` он должен быть отделен от этого оператора пробелом.</span><span class="sxs-lookup"><span data-stu-id="ed3de-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="ed3de-113">Можно использовать одиночную кавычку (`'`) `REM`вместо.</span><span class="sxs-lookup"><span data-stu-id="ed3de-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="ed3de-114">Это верно, если ваш комментарий следует другому оператору в той же строке или расподержаться только в строке.</span><span class="sxs-lookup"><span data-stu-id="ed3de-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed3de-115">Нельзя продолжить выполнение `REM` инструкции с помощью последовательности продолжения строки (`_`).</span><span class="sxs-lookup"><span data-stu-id="ed3de-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="ed3de-116">После начала комментария компилятор не проверяет символы на предмет особого значения.</span><span class="sxs-lookup"><span data-stu-id="ed3de-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="ed3de-117">Для многострочного комментария используйте другую `REM` инструкцию или символ комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="ed3de-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed3de-118">Пример</span><span class="sxs-lookup"><span data-stu-id="ed3de-118">Example</span></span>  
 <span data-ttu-id="ed3de-119">В следующем примере показана `REM` инструкция, которая используется для включения пояснительных примечаний в программу.</span><span class="sxs-lookup"><span data-stu-id="ed3de-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="ed3de-120">Он также показывает альтернативу использованию символа одинарной кавычки (`'`) `REM`вместо.</span><span class="sxs-lookup"><span data-stu-id="ed3de-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ed3de-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ed3de-121">See also</span></span>

- [<span data-ttu-id="ed3de-122">Комментарии в коде</span><span class="sxs-lookup"><span data-stu-id="ed3de-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="ed3de-123">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="ed3de-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
