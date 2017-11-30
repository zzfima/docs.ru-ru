---
title: "#<a name=\"const-directive\"></a>Директива #const"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="const-directive"></a><span data-ttu-id="bdb8d-102">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="bdb8d-102">#Const Directive</span></span>
<span data-ttu-id="bdb8d-103">Задает константы условной компиляции для Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdb8d-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="bdb8d-105">Части</span><span class="sxs-lookup"><span data-stu-id="bdb8d-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="bdb8d-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-106">Required.</span></span> <span data-ttu-id="bdb8d-107">Имя определяемой константы.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="bdb8d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-108">Required.</span></span> <span data-ttu-id="bdb8d-109">Литерал, другая константа условной компиляции или любой их комбинацией, включающей любые или все арифметические или логические операторы, за исключением `Is`.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdb8d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bdb8d-110">Remarks</span></span>  
 <span data-ttu-id="bdb8d-111">Константы условной компиляции всегда являются закрытыми для файла, в котором они отображаются.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="bdb8d-112">Не удается создать открытые константы условной компиляции с помощью `#Const` директив; их можно создать только в пользовательском интерфейсе или с `/define` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="bdb8d-113">Можно использовать только константы условной компиляции и литералы в `expression`.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="bdb8d-114">С помощью стандартных констант в определении `Const` приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="bdb8d-115">И наоборот, можно использовать константы, определенные с `#Const` ключевое слово только для условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="bdb8d-116">Константы могут также быть неопределенными, при этом они имеют значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdb8d-117">Пример</span><span class="sxs-lookup"><span data-stu-id="bdb8d-117">Example</span></span>  
 <span data-ttu-id="bdb8d-118">В этом примере используется директива `#Const`.</span><span class="sxs-lookup"><span data-stu-id="bdb8d-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bdb8d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bdb8d-119">See Also</span></span>  
 [<span data-ttu-id="bdb8d-120">/ define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdb8d-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)  
 [<span data-ttu-id="bdb8d-121">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="bdb8d-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="bdb8d-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="bdb8d-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="bdb8d-123">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="bdb8d-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="bdb8d-124">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="bdb8d-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
