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
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599139"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="3981e-102">Оператор Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3981e-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="3981e-103">Приостанавливает выполнение.</span><span class="sxs-lookup"><span data-stu-id="3981e-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3981e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3981e-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="3981e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3981e-105">Remarks</span></span>  
 <span data-ttu-id="3981e-106">Можно поместить `Stop` инструкций в любом месте процедуры для приостановки выполнения.</span><span class="sxs-lookup"><span data-stu-id="3981e-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="3981e-107">С помощью `Stop` инструкция похожа на задание точки останова в коде.</span><span class="sxs-lookup"><span data-stu-id="3981e-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="3981e-108">`Stop` Оператор приостанавливает выполнение, но в отличие от `End`, не закрывает файлы и не удаляет переменные, если только встречается в компилируемый исполняемый файл (.exe) файл.</span><span class="sxs-lookup"><span data-stu-id="3981e-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3981e-109">Если `Stop` встречается в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик.</span><span class="sxs-lookup"><span data-stu-id="3981e-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="3981e-110">Это верно независимо от того, скомпилирован ли код в режиме отладки или в розницу.</span><span class="sxs-lookup"><span data-stu-id="3981e-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3981e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="3981e-111">Example</span></span>  
 <span data-ttu-id="3981e-112">В этом примере используется `Stop` инструкции для приостановки выполнения на каждом шаге цикла `For...Next` цикла.</span><span class="sxs-lookup"><span data-stu-id="3981e-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3981e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3981e-113">See Also</span></span>  
 [<span data-ttu-id="3981e-114">Оператор End</span><span class="sxs-lookup"><span data-stu-id="3981e-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
