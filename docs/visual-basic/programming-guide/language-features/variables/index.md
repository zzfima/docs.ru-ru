---
title: "Переменные в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2fdc670bf4f17000809e75e32c32edb39abf0fed
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="f8d59-102">Переменные в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8d59-102">Variables in Visual Basic</span></span>
<span data-ttu-id="f8d59-103">Часто при выполнении вычислений с [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] требуется сохранять значения.</span><span class="sxs-lookup"><span data-stu-id="f8d59-103">You often have to store values when you perform calculations with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="f8d59-104">Например, может потребоваться вычислить несколько значений, сравнить их и (в зависимости от результата сравнения) выполнить с ними различные операции.</span><span class="sxs-lookup"><span data-stu-id="f8d59-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="f8d59-105">Чтобы сравнить значения, их необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="f8d59-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f8d59-106">Использование</span><span class="sxs-lookup"><span data-stu-id="f8d59-106">Usage</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f8d59-107">, как и большинство языков программирования, использует для хранения значений переменные.</span><span class="sxs-lookup"><span data-stu-id="f8d59-107">, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="f8d59-108">*Переменная* имеет имя (слово, которое используется для ссылки на содержащееся в переменной значение).</span><span class="sxs-lookup"><span data-stu-id="f8d59-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="f8d59-109">Переменная также имеет тип данных (который определяет, какие данные можно хранить в переменной).</span><span class="sxs-lookup"><span data-stu-id="f8d59-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="f8d59-110">Переменная может представлять массив, если она должна хранить индексированный набор близко связанных элементов данных.</span><span class="sxs-lookup"><span data-stu-id="f8d59-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="f8d59-111">Вывод локального типа позволяет объявлять переменные без явного указания типа данных.</span><span class="sxs-lookup"><span data-stu-id="f8d59-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="f8d59-112">Вместо этого компилятор выводит тип переменной из типа инициализирующего выражения.</span><span class="sxs-lookup"><span data-stu-id="f8d59-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="f8d59-113">Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f8d59-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="f8d59-114">Назначение значений</span><span class="sxs-lookup"><span data-stu-id="f8d59-114">Assigning Values</span></span>  
 <span data-ttu-id="f8d59-115">Для выполнения вычислений и присвоения результата переменной используются операторы присваивания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8d59-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 <span data-ttu-id="f8d59-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f8d59-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8d59-117">В этом примере знак равенства (`=`) является оператором присваивания, а не оператором равенства.</span><span class="sxs-lookup"><span data-stu-id="f8d59-117">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="f8d59-118">Значение присваивается переменной `applesSold`.</span><span class="sxs-lookup"><span data-stu-id="f8d59-118">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="f8d59-119">Подробнее см. в разделе [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="f8d59-119">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="f8d59-120">Переменные и свойства</span><span class="sxs-lookup"><span data-stu-id="f8d59-120">Variables and Properties</span></span>  
 <span data-ttu-id="f8d59-121">Как и переменная, *свойство* соответствует значению, к которому можно получить доступ.</span><span class="sxs-lookup"><span data-stu-id="f8d59-121">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="f8d59-122">Но оно является более сложным, чем переменная.</span><span class="sxs-lookup"><span data-stu-id="f8d59-122">However, it is more complex than a variable.</span></span> <span data-ttu-id="f8d59-123">Свойство использует блоки кода, определяющие способ задания и получения его значения.</span><span class="sxs-lookup"><span data-stu-id="f8d59-123">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="f8d59-124">Подробнее см. в разделе [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f8d59-124">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d59-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f8d59-125">See Also</span></span>  
 <span data-ttu-id="f8d59-126">[Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="f8d59-126">[Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
 <span data-ttu-id="f8d59-127">[Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f8d59-127">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
 <span data-ttu-id="f8d59-128">[Устранение неполадок, связанных с переменными](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f8d59-128">[Troubleshooting Variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span></span>  
 <span data-ttu-id="f8d59-129">[Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="f8d59-129">[How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
 <span data-ttu-id="f8d59-130">[Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f8d59-130">[Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span></span>  
 [<span data-ttu-id="f8d59-131">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="f8d59-131">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

