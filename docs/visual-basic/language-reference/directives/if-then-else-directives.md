---
title: '#Директивы If…Then…#Else'
ms.date: 04/11/2018
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
ms.openlocfilehash: 40e93b718241c9819e3c0fd84595e76eb0c86472
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343817"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="02d7b-102">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="02d7b-102">#If...Then...#Else Directives</span></span>

<span data-ttu-id="02d7b-103">Условно компилирует выбранные блоки кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="02d7b-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>

## <a name="syntax"></a><span data-ttu-id="02d7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02d7b-104">Syntax</span></span>

```vb
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

## <a name="parts"></a><span data-ttu-id="02d7b-105">Части</span><span class="sxs-lookup"><span data-stu-id="02d7b-105">Parts</span></span>

`expression`  
<span data-ttu-id="02d7b-106">Требуется для инструкций `#If` и `#ElseIf`, необязательно в других местах.</span><span class="sxs-lookup"><span data-stu-id="02d7b-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="02d7b-107">Любое выражение, состоящее исключительно из одной или нескольких условных констант компилятора, литералов и операторов, результатом вычисления которого является `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="02d7b-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>

`statements`  
<span data-ttu-id="02d7b-108">Требуется для блока инструкций `#If`, необязательно в других местах.</span><span class="sxs-lookup"><span data-stu-id="02d7b-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="02d7b-109">Visual Basic строки программы или директивы компилятора, компилируемые, если связанное выражение имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="02d7b-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>

`#End If`  
<span data-ttu-id="02d7b-110">Завершает блок оператора `#If`.</span><span class="sxs-lookup"><span data-stu-id="02d7b-110">Terminates the `#If` statement block.</span></span>

## <a name="remarks"></a><span data-ttu-id="02d7b-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="02d7b-111">Remarks</span></span>

<span data-ttu-id="02d7b-112">На поверхности поведение директив `#If...Then...#Else` выглядит так же, как и инструкции `If...Then...Else`.</span><span class="sxs-lookup"><span data-stu-id="02d7b-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="02d7b-113">Однако директивы `#If...Then...#Else` оценивают, что компилируется компилятором, в то время как инструкции `If...Then...Else` оценивают условия во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="02d7b-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>

<span data-ttu-id="02d7b-114">Условная компиляция обычно используется для компиляции одной и той же программы для разных платформ.</span><span class="sxs-lookup"><span data-stu-id="02d7b-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="02d7b-115">Он также используется для предотвращения появления отладочного кода в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="02d7b-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="02d7b-116">Код, исключенный во время условной компиляции, полностью опускается из финального исполняемого файла, поэтому он не влияет на размер и производительность.</span><span class="sxs-lookup"><span data-stu-id="02d7b-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>

<span data-ttu-id="02d7b-117">Независимо от результата вычисления все выражения оцениваются с помощью `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="02d7b-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="02d7b-118">Инструкция `Option Compare` не влияет на выражения в инструкциях `#If` и `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="02d7b-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>

> [!NOTE]
> <span data-ttu-id="02d7b-119">Не существует однострочной формы директив `#If`, `#Else`, `#ElseIf`и `#End If`.</span><span class="sxs-lookup"><span data-stu-id="02d7b-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="02d7b-120">Никакой другой код не может отображаться в той же строке, что и любая из директив.</span><span class="sxs-lookup"><span data-stu-id="02d7b-120">No other code can appear on the same line as any of the directives.</span></span>

<span data-ttu-id="02d7b-121">Инструкции в блоке условной компиляции должны быть полными логическими операторами.</span><span class="sxs-lookup"><span data-stu-id="02d7b-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="02d7b-122">Например, невозможно условно компилировать только атрибуты функции, но можно условно объявить функцию вместе с ее атрибутами:</span><span class="sxs-lookup"><span data-stu-id="02d7b-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a><span data-ttu-id="02d7b-123">Пример</span><span class="sxs-lookup"><span data-stu-id="02d7b-123">Example</span></span>

<span data-ttu-id="02d7b-124">В этом примере используется конструкция `#If...Then...#Else` для определения необходимости компиляции определенных инструкций.</span><span class="sxs-lookup"><span data-stu-id="02d7b-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="02d7b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="02d7b-125">See also</span></span>

- [<span data-ttu-id="02d7b-126">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="02d7b-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="02d7b-127">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="02d7b-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="02d7b-128">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="02d7b-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
