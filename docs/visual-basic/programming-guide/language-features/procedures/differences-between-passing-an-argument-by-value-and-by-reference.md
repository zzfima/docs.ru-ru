---
title: "Различия между передачей аргумента по значению и по ссылке (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- procedures, passing arguments
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 706c64cd316791a748e2b68fe406e34084b04d5a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="f020c-102">Различия между передачей аргумента по значению и по ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f020c-102">Differences Between Passing an Argument By Value and By Reference (Visual Basic)</span></span>
<span data-ttu-id="f020c-103">При передаче одного или нескольких аргументов в процедуру, каждый аргумент соответствует базовому элементу программирования в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="f020c-103">When you pass one or more arguments to a procedure, each argument corresponds to an underlying programming element in the calling code.</span></span> <span data-ttu-id="f020c-104">Можно передать либо значение этого базового элемента, либо ссылку на него.</span><span class="sxs-lookup"><span data-stu-id="f020c-104">You can pass either the value of this underlying element, or a reference to it.</span></span> <span data-ttu-id="f020c-105">Это называется *механизм передачи*.</span><span class="sxs-lookup"><span data-stu-id="f020c-105">This is known as the *passing mechanism*.</span></span>  
  
## <a name="passing-by-value"></a><span data-ttu-id="f020c-106">передача по значению</span><span class="sxs-lookup"><span data-stu-id="f020c-106">Passing by Value</span></span>  
 <span data-ttu-id="f020c-107">При передаче аргумента *по значению* , указав [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ключевое слово для соответствующего параметра в определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="f020c-107">You pass an argument *by value* by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="f020c-108">При использовании этого механизма передачи [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] копирует значение из базового элемента программирования в локальную переменную в процедуре.</span><span class="sxs-lookup"><span data-stu-id="f020c-108">When you use this passing mechanism, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the value of the underlying programming element into a local variable in the procedure.</span></span> <span data-ttu-id="f020c-109">Код процедуры не имеет доступа к базовому элементу в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="f020c-109">The procedure code does not have any access to the underlying element in the calling code.</span></span>  
  
## <a name="passing-by-reference"></a><span data-ttu-id="f020c-110">Передача по ссылке</span><span class="sxs-lookup"><span data-stu-id="f020c-110">Passing by Reference</span></span>  
 <span data-ttu-id="f020c-111">При передаче аргумента *по ссылке* , указав [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово для соответствующего параметра в определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="f020c-111">You pass an argument *by reference* by specifying the [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="f020c-112">При использовании этого механизма передачи [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет процедуре прямую ссылку на основной элемент программирования в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="f020c-112">When you use this passing mechanism, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure a direct reference to the underlying programming element in the calling code.</span></span>  
  
## <a name="passing-mechanism-and-element-type"></a><span data-ttu-id="f020c-113">Механизм передачи и тип элемента</span><span class="sxs-lookup"><span data-stu-id="f020c-113">Passing Mechanism and Element Type</span></span>  
 <span data-ttu-id="f020c-114">Выбор механизма передачи отличается от классификации типа базового элемента.</span><span class="sxs-lookup"><span data-stu-id="f020c-114">The choice of passing mechanism is not the same as the classification of the underlying element type.</span></span> <span data-ttu-id="f020c-115">Передача по значению или по ссылке указывает на то, что [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет коду процедуры.</span><span class="sxs-lookup"><span data-stu-id="f020c-115">Passing by value or by reference refers to what [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies to the procedure code.</span></span> <span data-ttu-id="f020c-116">Тип значения или ссылочный тип ссылается на способ хранения элемента программирования в памяти.</span><span class="sxs-lookup"><span data-stu-id="f020c-116">A value type or reference type refers to how a programming element is stored in memory.</span></span>  
  
 <span data-ttu-id="f020c-117">Однако механизм передачи и тип элемента являются взаимосвязанными.</span><span class="sxs-lookup"><span data-stu-id="f020c-117">However, the passing mechanism and element type are interrelated.</span></span> <span data-ttu-id="f020c-118">Значение ссылочного типа — указатель на данные в другом месте в памяти.</span><span class="sxs-lookup"><span data-stu-id="f020c-118">The value of a reference type is a pointer to the data elsewhere in memory.</span></span> <span data-ttu-id="f020c-119">Это означает, что при передаче ссылочного типа по значению код процедуры имеет указатель на базовые данные элемента, даже если нет доступа к самому базовому элементу.</span><span class="sxs-lookup"><span data-stu-id="f020c-119">This means that when you pass a reference type by value, the procedure code has a pointer to the underlying element's data, even though it cannot access the underlying element itself.</span></span> <span data-ttu-id="f020c-120">Например если элемент является переменной массива, код процедуры не имеет доступа к самой переменной, но он имеет доступ к членам массива.</span><span class="sxs-lookup"><span data-stu-id="f020c-120">For example, if the element is an array variable, the procedure code does not have access to the variable itself, but it can access the array members.</span></span>  
  
## <a name="ability-to-modify"></a><span data-ttu-id="f020c-121">Возможность изменения</span><span class="sxs-lookup"><span data-stu-id="f020c-121">Ability to Modify</span></span>  
 <span data-ttu-id="f020c-122">Когда неизменяемый элемент передается в качестве аргумента, процедура не может изменить его в вызывающем коде, был ли он передан `ByVal` или `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="f020c-122">When you pass a nonmodifiable element as an argument, the procedure can never modify it in the calling code, whether it is passed `ByVal` or `ByRef`.</span></span>  
  
 <span data-ttu-id="f020c-123">Для изменяемого элемента в следующей таблице перечислены взаимодействия тип элемента и механизм передачи.</span><span class="sxs-lookup"><span data-stu-id="f020c-123">For a modifiable element, the following table summarizes the interaction between the element type and the passing mechanism.</span></span>  
  
|<span data-ttu-id="f020c-124">Тип элемента</span><span class="sxs-lookup"><span data-stu-id="f020c-124">Element type</span></span>|<span data-ttu-id="f020c-125">Передан`ByVal`</span><span class="sxs-lookup"><span data-stu-id="f020c-125">Passed `ByVal`</span></span>|<span data-ttu-id="f020c-126">Передан`ByRef`</span><span class="sxs-lookup"><span data-stu-id="f020c-126">Passed `ByRef`</span></span>|  
|------------------|--------------------|--------------------|  
|<span data-ttu-id="f020c-127">Тип значения (содержит только значение)</span><span class="sxs-lookup"><span data-stu-id="f020c-127">Value type (contains only a value)</span></span>|<span data-ttu-id="f020c-128">Процедура не может изменять переменную или любого из его элементов.</span><span class="sxs-lookup"><span data-stu-id="f020c-128">The procedure cannot change the variable or any of its members.</span></span>|<span data-ttu-id="f020c-129">Процедура может изменять переменную и ее членов.</span><span class="sxs-lookup"><span data-stu-id="f020c-129">The procedure can change the variable and its members.</span></span>|  
|<span data-ttu-id="f020c-130">Ссылочный тип (содержит указатель на экземпляр класса или структуры)</span><span class="sxs-lookup"><span data-stu-id="f020c-130">Reference type (contains a pointer to a class or structure instance)</span></span>|<span data-ttu-id="f020c-131">Процедура не может изменить переменную, но можно изменить члены экземпляра, на который он указывает.</span><span class="sxs-lookup"><span data-stu-id="f020c-131">The procedure cannot change the variable but can change members of the instance to which it points.</span></span>|<span data-ttu-id="f020c-132">Процедура может изменять переменную и члены экземпляра, на который он указывает.</span><span class="sxs-lookup"><span data-stu-id="f020c-132">The procedure can change the variable and members of the instance to which it points.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f020c-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f020c-133">See Also</span></span>  
 <span data-ttu-id="f020c-134">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-134">[Procedures](./index.md) </span></span>  
<span data-ttu-id="f020c-135"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="f020c-136"> [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-136"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="f020c-137"> [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-137"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="f020c-138"> [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-138"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="f020c-139"> [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="f020c-140"> [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="f020c-141"> [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-141"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="f020c-142"> [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="f020c-142"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="f020c-143"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="f020c-143"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
