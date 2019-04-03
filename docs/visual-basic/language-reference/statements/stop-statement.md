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
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827995"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="faec9-102">Оператор Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="faec9-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="faec9-103">Приостанавливает выполнение.</span><span class="sxs-lookup"><span data-stu-id="faec9-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faec9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="faec9-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="faec9-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="faec9-105">Remarks</span></span>  
 <span data-ttu-id="faec9-106">Вы можете поместить `Stop` инструкций в любом месте процедуры для приостановки выполнения.</span><span class="sxs-lookup"><span data-stu-id="faec9-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="faec9-107">С помощью `Stop` инструкция похожа на задание точки останова в коде.</span><span class="sxs-lookup"><span data-stu-id="faec9-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="faec9-108">`Stop` Инструкция приостанавливает выполнение, но в отличие от `End`, закройте все файлы или не удаляет переменные, в том случае, если только встречается в файле скомпилированный исполняемый файл (.exe).</span><span class="sxs-lookup"><span data-stu-id="faec9-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="faec9-109">Если `Stop` встречается в коде, выполняемом вне интегрированной среде разработки (IDE), вызывается отладчик.</span><span class="sxs-lookup"><span data-stu-id="faec9-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="faec9-110">Это верно независимо от того, скомпилирован ли код в режиме debug или retail.</span><span class="sxs-lookup"><span data-stu-id="faec9-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="faec9-111">Пример</span><span class="sxs-lookup"><span data-stu-id="faec9-111">Example</span></span>  
 <span data-ttu-id="faec9-112">В этом примере используется `Stop` инструкции для приостановки выполнения на каждом проходе через `For...Next` цикла.</span><span class="sxs-lookup"><span data-stu-id="faec9-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="faec9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="faec9-113">See also</span></span>

- [<span data-ttu-id="faec9-114">Оператор End</span><span class="sxs-lookup"><span data-stu-id="faec9-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
