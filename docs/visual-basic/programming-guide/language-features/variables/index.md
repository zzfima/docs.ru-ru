---
title: Переменные в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7a47ad7e4ade9f15159c27ac672aeb937a05493
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="faaca-102">Переменные в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="faaca-102">Variables in Visual Basic</span></span>
<span data-ttu-id="faaca-103">Часто при выполнении вычислений с [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] требуется сохранять значения.</span><span class="sxs-lookup"><span data-stu-id="faaca-103">You often have to store values when you perform calculations with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="faaca-104">Например, может потребоваться вычислить несколько значений, сравнить их и (в зависимости от результата сравнения) выполнить с ними различные операции.</span><span class="sxs-lookup"><span data-stu-id="faaca-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="faaca-105">Чтобы сравнить значения, их необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="faaca-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="faaca-106">Использование</span><span class="sxs-lookup"><span data-stu-id="faaca-106">Usage</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="faaca-107">, как и большинство языков программирования, использует для хранения значений переменные.</span><span class="sxs-lookup"><span data-stu-id="faaca-107">, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="faaca-108">*Переменная* имеет имя (слово, которое используется для ссылки на содержащееся в переменной значение).</span><span class="sxs-lookup"><span data-stu-id="faaca-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="faaca-109">Переменная также имеет тип данных (который определяет, какие данные можно хранить в переменной).</span><span class="sxs-lookup"><span data-stu-id="faaca-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="faaca-110">Переменная может представлять массив, если она должна хранить индексированный набор близко связанных элементов данных.</span><span class="sxs-lookup"><span data-stu-id="faaca-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="faaca-111">Вывод локального типа позволяет объявлять переменные без явного указания типа данных.</span><span class="sxs-lookup"><span data-stu-id="faaca-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="faaca-112">Вместо этого компилятор выводит тип переменной из типа инициализирующего выражения.</span><span class="sxs-lookup"><span data-stu-id="faaca-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="faaca-113">Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="faaca-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="faaca-114">Назначение значений</span><span class="sxs-lookup"><span data-stu-id="faaca-114">Assigning Values</span></span>  
 <span data-ttu-id="faaca-115">Для выполнения вычислений и присвоения результата переменной используются операторы присваивания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="faaca-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="faaca-116">В этом примере знак равенства (`=`) является оператором присваивания, а не оператором равенства.</span><span class="sxs-lookup"><span data-stu-id="faaca-116">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="faaca-117">Значение присваивается переменной `applesSold`.</span><span class="sxs-lookup"><span data-stu-id="faaca-117">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="faaca-118">Подробнее см. в разделе [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="faaca-118">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="faaca-119">Переменные и свойства</span><span class="sxs-lookup"><span data-stu-id="faaca-119">Variables and Properties</span></span>  
 <span data-ttu-id="faaca-120">Как и переменная, *свойство* соответствует значению, к которому можно получить доступ.</span><span class="sxs-lookup"><span data-stu-id="faaca-120">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="faaca-121">Но оно является более сложным, чем переменная.</span><span class="sxs-lookup"><span data-stu-id="faaca-121">However, it is more complex than a variable.</span></span> <span data-ttu-id="faaca-122">Свойство использует блоки кода, определяющие способ задания и получения его значения.</span><span class="sxs-lookup"><span data-stu-id="faaca-122">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="faaca-123">Подробнее см. в разделе [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="faaca-123">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faaca-124">См. также</span><span class="sxs-lookup"><span data-stu-id="faaca-124">See Also</span></span>  
 [<span data-ttu-id="faaca-125">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="faaca-125">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="faaca-126">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="faaca-126">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="faaca-127">Устранение неполадок, связанных с переменными</span><span class="sxs-lookup"><span data-stu-id="faaca-127">Troubleshooting Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)  
 [<span data-ttu-id="faaca-128">Практическое руководство. Запись данных в переменную и их извлечение из переменной</span><span class="sxs-lookup"><span data-stu-id="faaca-128">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [<span data-ttu-id="faaca-129">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="faaca-129">Differences Between Properties and Variables in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)  
 [<span data-ttu-id="faaca-130">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="faaca-130">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
