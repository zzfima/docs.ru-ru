---
title: Оператор Call (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832649"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="06608-102">Оператор Call (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06608-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="06608-103">Передает управление `Function`, `Sub`, или процедуре библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="06608-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06608-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06608-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="06608-105">Части</span><span class="sxs-lookup"><span data-stu-id="06608-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="06608-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="06608-106">Required.</span></span> <span data-ttu-id="06608-107">Имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="06608-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="06608-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="06608-108">Optional.</span></span> <span data-ttu-id="06608-109">Список переменных или выражений, представляющих аргументы, передаваемые в процедуру при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="06608-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="06608-110">Несколько аргументов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="06608-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="06608-111">При включении `argumentList`, его необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="06608-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="06608-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="06608-112">Remarks</span></span>  
 <span data-ttu-id="06608-113">Можно использовать `Call` ключевое слово при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="06608-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="06608-114">Для большинства вызовов процедур не нужно использовать это ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="06608-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="06608-115">Как правило, используется `Call` ключевое слово, если вызываемый выражение не начинается с идентификатора.</span><span class="sxs-lookup"><span data-stu-id="06608-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="06608-116">Использование `Call` ключевое слово для других целей не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="06608-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="06608-117">Если процедура возвращает значение, `Call` инструкции отклоняет его.</span><span class="sxs-lookup"><span data-stu-id="06608-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06608-118">Пример</span><span class="sxs-lookup"><span data-stu-id="06608-118">Example</span></span>  
 <span data-ttu-id="06608-119">В следующем коде показано два примера где `Call` ключевое слово не требуется для вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="06608-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="06608-120">В обоих примерах вызываемой выражение не начинается с идентификатора.</span><span class="sxs-lookup"><span data-stu-id="06608-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="06608-121">См. также</span><span class="sxs-lookup"><span data-stu-id="06608-121">See also</span></span>

- [<span data-ttu-id="06608-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="06608-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="06608-123">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="06608-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="06608-124">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="06608-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="06608-125">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="06608-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
