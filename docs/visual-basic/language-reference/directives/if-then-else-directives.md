---
title: "#<a name=\"ifthenelse-directives\"></a>If... Then... #Else директивы"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77757e441ae937aa86122f237e839d1005644409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="64f41-102">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="64f41-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="64f41-103">Условно компилирует выбранные блоки кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="64f41-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f41-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64f41-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="64f41-105">Части</span><span class="sxs-lookup"><span data-stu-id="64f41-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="64f41-106">Требуется для `#If` и `#ElseIf` операторов в другом месте.</span><span class="sxs-lookup"><span data-stu-id="64f41-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="64f41-107">Любое выражение, состоящее исключительно из константы условной компиляции, литералы и операторов, результатом которого является `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="64f41-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="64f41-108">Требуется для `#If` инструкции блока, необязательно в другом месте.</span><span class="sxs-lookup"><span data-stu-id="64f41-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="64f41-109">Строки кода Visual Basic или директивы компилятора компилируются, если значение выражения, результатом которого является `True`.</span><span class="sxs-lookup"><span data-stu-id="64f41-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="64f41-110">Завершает `#If` блока инструкций.</span><span class="sxs-lookup"><span data-stu-id="64f41-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64f41-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="64f41-111">Remarks</span></span>  
 <span data-ttu-id="64f41-112">В рабочей области, поведение `#If...Then...#Else` директивы отображается одинаково как для `If...Then...Else` инструкций.</span><span class="sxs-lookup"><span data-stu-id="64f41-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="64f41-113">Тем не менее `#If...Then...#Else` директивы оперируют компилятором, тогда как `If...Then...Else` операторов результат вычисления условия во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="64f41-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="64f41-114">Условная компиляция обычно используется для компиляции того же кода для разных платформ.</span><span class="sxs-lookup"><span data-stu-id="64f41-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="64f41-115">Оно также используется для предотвращения появления в исполняемом файле отладочного кода.</span><span class="sxs-lookup"><span data-stu-id="64f41-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="64f41-116">Код, исключаемый при условной компиляции полностью исключается из окончательный исполняемый файл, поэтому не влияет на производительность или размер.</span><span class="sxs-lookup"><span data-stu-id="64f41-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="64f41-117">Независимо от результата любого вычисления, все выражения вычисляются с помощью `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="64f41-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="64f41-118">`Option Compare` Инструкции не влияет на выражения в `#If` и `#ElseIf` инструкции.</span><span class="sxs-lookup"><span data-stu-id="64f41-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64f41-119">Ни в какой форме однострочный `#If`, `#Else`, `#ElseIf`, и `#End If` существует директивы.</span><span class="sxs-lookup"><span data-stu-id="64f41-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="64f41-120">Никакой другой код могут отображаться на одной строке с любой из директивы.</span><span class="sxs-lookup"><span data-stu-id="64f41-120">No other code can appear on the same line as any of the directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f41-121">Пример</span><span class="sxs-lookup"><span data-stu-id="64f41-121">Example</span></span>  
 <span data-ttu-id="64f41-122">В этом примере используется `#If...Then...#Else` для определения, следует ли компилировать определенных операторов.</span><span class="sxs-lookup"><span data-stu-id="64f41-122">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="64f41-123">См. также</span><span class="sxs-lookup"><span data-stu-id="64f41-123">See Also</span></span>  
 [<span data-ttu-id="64f41-124">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="64f41-124">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="64f41-125">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="64f41-125">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="64f41-126">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="64f41-126">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
