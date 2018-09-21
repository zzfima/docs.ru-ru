---
title: '#Директива #const (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 58d786c5e16b1e667f7c7c78b0f7857cd9711239
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537804"
---
# <a name="const-directive"></a><span data-ttu-id="6937c-102">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="6937c-102">#Const Directive</span></span>
<span data-ttu-id="6937c-103">Задает константы условной компиляции для Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6937c-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6937c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6937c-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6937c-105">Части</span><span class="sxs-lookup"><span data-stu-id="6937c-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="6937c-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="6937c-106">Required.</span></span> <span data-ttu-id="6937c-107">Имя определяемой константы.</span><span class="sxs-lookup"><span data-stu-id="6937c-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="6937c-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="6937c-108">Required.</span></span> <span data-ttu-id="6937c-109">Литерал, другая константа условной компиляции или какое-либо сочетание включает любые или все арифметические или логические операторы, за исключением `Is`.</span><span class="sxs-lookup"><span data-stu-id="6937c-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6937c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6937c-110">Remarks</span></span>  
 <span data-ttu-id="6937c-111">Константы условной компиляции всегда являются закрытыми для файла, в котором они появляются.</span><span class="sxs-lookup"><span data-stu-id="6937c-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="6937c-112">Не удается создать открытые константы компилятора с помощью `#Const` директив; их можно создать только в пользовательском интерфейсе или с помощью `/define` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="6937c-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="6937c-113">Можно использовать только константы условной компиляции и литералы в `expression`.</span><span class="sxs-lookup"><span data-stu-id="6937c-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="6937c-114">Это стандартная константа, определенная с помощью `Const` приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="6937c-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="6937c-115">И наоборот, можно использовать константы, определенные с помощью `#Const` ключевое слово только для условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="6937c-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="6937c-116">Константы могут также быть неопределенными, в противном случае они имеют значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6937c-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6937c-117">Пример</span><span class="sxs-lookup"><span data-stu-id="6937c-117">Example</span></span>  
 <span data-ttu-id="6937c-118">В этом примере используется директива `#Const`.</span><span class="sxs-lookup"><span data-stu-id="6937c-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6937c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6937c-119">See Also</span></span>  
 [<span data-ttu-id="6937c-120">/ define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6937c-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)  
 [<span data-ttu-id="6937c-121">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="6937c-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="6937c-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="6937c-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="6937c-123">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="6937c-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="6937c-124">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="6937c-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
