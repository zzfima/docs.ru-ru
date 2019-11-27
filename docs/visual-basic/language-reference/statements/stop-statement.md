---
title: Оператор Stop
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 497c5f207b2228412411cc3eb01976564f82bd6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346470"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="6025a-102">Оператор Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6025a-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="6025a-103">Приостанавливает выполнение.</span><span class="sxs-lookup"><span data-stu-id="6025a-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6025a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6025a-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="6025a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="6025a-105">Remarks</span></span>  
 <span data-ttu-id="6025a-106">Инструкции `Stop` можно разместить в любом месте процедуры, чтобы приостановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="6025a-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="6025a-107">Использование оператора `Stop` аналогично установке точки останова в коде.</span><span class="sxs-lookup"><span data-stu-id="6025a-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="6025a-108">Инструкция `Stop` приостанавливает выполнение, но в отличие от `End`, она не закрывает никакие файлы и не очищает переменные, если только она не обнаружена в скомпилированном исполняемом файле (exe).</span><span class="sxs-lookup"><span data-stu-id="6025a-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6025a-109">Если оператор `Stop` встречается в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик.</span><span class="sxs-lookup"><span data-stu-id="6025a-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="6025a-110">Это справедливо независимо от того, был ли код скомпилирован в режиме отладки или розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="6025a-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6025a-111">Пример</span><span class="sxs-lookup"><span data-stu-id="6025a-111">Example</span></span>  
 <span data-ttu-id="6025a-112">В этом примере используется инструкция `Stop` для приостановки выполнения каждой итерации в цикле `For...Next`.</span><span class="sxs-lookup"><span data-stu-id="6025a-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="6025a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6025a-113">See also</span></span>

- [<span data-ttu-id="6025a-114">Оператор End</span><span class="sxs-lookup"><span data-stu-id="6025a-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
