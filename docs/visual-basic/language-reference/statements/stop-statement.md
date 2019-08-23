---
title: Оператор Stop (Visual Basic)
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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957622"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="214e0-102">Оператор Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="214e0-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="214e0-103">Приостанавливает выполнение.</span><span class="sxs-lookup"><span data-stu-id="214e0-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="214e0-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="214e0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="214e0-105">Remarks</span></span>  
 <span data-ttu-id="214e0-106">Операторы можно разместить `Stop` в любом месте процедуры, чтобы приостановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="214e0-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="214e0-107">`Stop` Использование инструкции аналогично установке точки останова в коде.</span><span class="sxs-lookup"><span data-stu-id="214e0-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="214e0-108">Инструкция приостанавливает выполнение, но в отличие от `End`этого она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe). `Stop`</span><span class="sxs-lookup"><span data-stu-id="214e0-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="214e0-109">`Stop` Если инструкция обнаружена в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик.</span><span class="sxs-lookup"><span data-stu-id="214e0-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="214e0-110">Это справедливо независимо от того, был ли код скомпилирован в режиме отладки или розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="214e0-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="214e0-111">Пример</span><span class="sxs-lookup"><span data-stu-id="214e0-111">Example</span></span>  
 <span data-ttu-id="214e0-112">В этом примере используется `Stop` оператор для приостановки выполнения для каждой итерации `For...Next` в цикле.</span><span class="sxs-lookup"><span data-stu-id="214e0-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="214e0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="214e0-113">See also</span></span>

- [<span data-ttu-id="214e0-114">Оператор End</span><span class="sxs-lookup"><span data-stu-id="214e0-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
