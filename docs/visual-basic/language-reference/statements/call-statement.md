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
ms.openlocfilehash: af0b62d6cfacbcf94f527e049e07e51bf496a6cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392762"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="d5594-102">Оператор Call (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5594-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="d5594-103">Передает управление в процедуру `Function`, `Sub` или в библиотеку динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="d5594-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5594-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5594-104">Syntax</span></span>

```vb
[ Call ] procedureName [ (argumentList) ]
```

## <a name="parts"></a><span data-ttu-id="d5594-105">Части</span><span class="sxs-lookup"><span data-stu-id="d5594-105">Parts</span></span>

|||
|---|---|
|`procedureName`|<span data-ttu-id="d5594-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d5594-106">Required.</span></span> <span data-ttu-id="d5594-107">Имя вызываемой процедуры.</span><span class="sxs-lookup"><span data-stu-id="d5594-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="d5594-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="d5594-108">Optional.</span></span> <span data-ttu-id="d5594-109">Список переменных или выражений, представляющих аргументы, которые передаются в процедуру при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="d5594-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="d5594-110">Несколько аргументов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="d5594-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="d5594-111">Если включить `argumentList`, необходимо заключить его в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="d5594-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="d5594-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5594-112">Remarks</span></span>

 <span data-ttu-id="d5594-113">При вызове процедуры можно использовать ключевое слово `Call`.</span><span class="sxs-lookup"><span data-stu-id="d5594-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="d5594-114">Для большинства вызовов процедур использовать это ключевое слово не обязательно.</span><span class="sxs-lookup"><span data-stu-id="d5594-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="d5594-115">Обычно используется ключевое слово `Call`, если вызванное выражение не начинается с идентификатора.</span><span class="sxs-lookup"><span data-stu-id="d5594-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="d5594-116">Использование ключевого слова `Call` для других целей не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="d5594-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="d5594-117">Если процедура возвращает значение, то инструкция `Call` отклоняет ее.</span><span class="sxs-lookup"><span data-stu-id="d5594-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="d5594-118">Пример</span><span class="sxs-lookup"><span data-stu-id="d5594-118">Example</span></span>

 <span data-ttu-id="d5594-119">В следующем коде показаны два примера, где ключевое слово `Call` необходимо для вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="d5594-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="d5594-120">В обоих примерах вызванное выражение не начинается с идентификатора.</span><span class="sxs-lookup"><span data-stu-id="d5594-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="d5594-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d5594-121">See also</span></span>

- [<span data-ttu-id="d5594-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="d5594-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="d5594-123">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="d5594-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="d5594-124">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="d5594-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="d5594-125">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="d5594-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
