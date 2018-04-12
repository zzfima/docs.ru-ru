---
title: Конец &lt;ключевое слово&gt; Statement (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf0ac1221f8a85a8a43599d9c5ec210884205e5e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="01915-102">Конец &lt;ключевое слово&gt; Statement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01915-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>
<span data-ttu-id="01915-103">Когда следует дополнительным ключевым словом, завершает определение блока операторов, представленного ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="01915-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01915-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01915-104">Syntax</span></span>  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="01915-105">Части</span><span class="sxs-lookup"><span data-stu-id="01915-105">Parts</span></span>  
 `End`  
 <span data-ttu-id="01915-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="01915-106">Required.</span></span> <span data-ttu-id="01915-107">Завершает определение элемента программирования.</span><span class="sxs-lookup"><span data-stu-id="01915-107">Terminates the definition of the programming element.</span></span>  
  
 `AddHandler`  
 <span data-ttu-id="01915-108">Обязателен для завершения `AddHandler` начато путем сопоставления доступа `AddHandler` инструкции в пользовательском [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-108">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Class`  
 <span data-ttu-id="01915-109">Обязателен для завершения определения класса начался, сопоставляя [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-109">Required to terminate a class definition begun by a matching [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
 `Enum`  
 <span data-ttu-id="01915-110">Обязателен для завершения начался, сопоставляя определение перечисления [оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-110">Required to terminate an enumeration definition begun by a matching [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 `Event`  
 <span data-ttu-id="01915-111">Обязателен для завершения `Custom` определение события начала, сопоставляя [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-111">Required to terminate a `Custom` event definition begun by a matching [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Function`  
 <span data-ttu-id="01915-112">Обязателен для завершения `Function` начался, соответствующего определения процедуры [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-112">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="01915-113">Если при выполнении `End``Function` инструкции, управление возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="01915-113">If execution encounters an `End``Function` statement, control returns to the calling code.</span></span>  
  
 `Get`  
 <span data-ttu-id="01915-114">Обязателен для завершения `Property` начался, соответствующего определения процедуры [оператор Get](../../../visual-basic/language-reference/statements/get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-114">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md).</span></span> <span data-ttu-id="01915-115">Если при выполнении `End``Get` инструкции, управление возвращается в инструкции, запрашивающего значение свойства.</span><span class="sxs-lookup"><span data-stu-id="01915-115">If execution encounters an `End``Get` statement, control returns to the statement requesting the property's value.</span></span>  
  
 `If`  
 <span data-ttu-id="01915-116">Обязателен для завершения `If`... `Then`... `Else` начался с соответствующим определением блока `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="01915-116">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="01915-117">В разделе [Если... Затем... Оператор Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-117">See [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span>  
  
 `Interface`  
 <span data-ttu-id="01915-118">Обязателен для завершения определения интерфейса начался, сопоставляя [оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-118">Required to terminate an interface definition begun by a matching [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md).</span></span>  
  
 `Module`  
 <span data-ttu-id="01915-119">Требуется для завершения определения начала путем сопоставления [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-119">Required to terminate a module definition begun by a matching [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
 `Namespace`  
 <span data-ttu-id="01915-120">Обязателен для завершения определения начала путем сопоставления пространства имен [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-120">Required to terminate a namespace definition begun by a matching [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span>  
  
 `Operator`  
 <span data-ttu-id="01915-121">Требуется для завершения определения оператора начался, сопоставляя [оператор](../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-121">Required to terminate an operator definition begun by a matching [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 `Property`  
 <span data-ttu-id="01915-122">Обязателен для завершения определения свойства начался, сопоставляя [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-122">Required to terminate a property definition begun by a matching [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
 `RaiseEvent`  
 <span data-ttu-id="01915-123">Обязателен для завершения `RaiseEvent` начато путем сопоставления доступа `RaiseEvent` инструкции в пользовательском [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-123">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `RemoveHandler`  
 <span data-ttu-id="01915-124">Обязателен для завершения `RemoveHandler` начато путем сопоставления доступа `RemoveHandler` инструкции в пользовательском [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-124">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Select`  
 <span data-ttu-id="01915-125">Обязателен для завершения `Select`... `Case` начался с соответствующим определением блока `Select` инструкции.</span><span class="sxs-lookup"><span data-stu-id="01915-125">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="01915-126">В разделе [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-126">See [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
 `Set`  
 <span data-ttu-id="01915-127">Обязателен для завершения `Property` начался, соответствующего определения процедуры [инструкции Set](../../../visual-basic/language-reference/statements/set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-127">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md).</span></span> <span data-ttu-id="01915-128">Если при выполнении `End``Set` инструкции, управление возвращается оператор, который задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="01915-128">If execution encounters an `End``Set` statement, control returns to the statement setting the property's value.</span></span>  
  
 `Structure`  
 <span data-ttu-id="01915-129">Требуется для завершения определения структуры начался, сопоставляя [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-129">Required to terminate a structure definition begun by a matching [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
 `Sub`  
 <span data-ttu-id="01915-130">Обязателен для завершения `Sub` начался, соответствующего определения процедуры [оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-130">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span> <span data-ttu-id="01915-131">Если при выполнении `End``Sub` инструкции, управление возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="01915-131">If execution encounters an `End``Sub` statement, control returns to the calling code.</span></span>  
  
 `SyncLock`  
 <span data-ttu-id="01915-132">Обязателен для завершения `SyncLock` начался с соответствующим определением блока `SyncLock` инструкции.</span><span class="sxs-lookup"><span data-stu-id="01915-132">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="01915-133">В разделе [оператор SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-133">See [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md).</span></span>  
  
 `Try`  
 <span data-ttu-id="01915-134">Обязателен для завершения `Try`... `Catch`... `Finally` начался с соответствующим определением блока `Try` инструкции.</span><span class="sxs-lookup"><span data-stu-id="01915-134">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="01915-135">В разделе [Try... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-135">See [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 `While`  
 <span data-ttu-id="01915-136">Обязателен для завершения `While` цикл определения начала путем сопоставления `While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="01915-136">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="01915-137">В разделе [во время... Завершить оператор While](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-137">See [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
 `With`  
 <span data-ttu-id="01915-138">Обязателен для завершения `With` начался с соответствующим определением блока `With` инструкции.</span><span class="sxs-lookup"><span data-stu-id="01915-138">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="01915-139">В разделе [с... Завершить с инструкцией](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01915-139">See [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01915-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="01915-140">Remarks</span></span>  
 <span data-ttu-id="01915-141">[Оператор End](../../../visual-basic/language-reference/statements/end-statement.md), без дополнительных ключевых слов, немедленно прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="01915-141">The [End Statement](../../../visual-basic/language-reference/statements/end-statement.md), without an additional keyword, terminates execution immediately.</span></span>  
  
 <span data-ttu-id="01915-142">Если предшествует знак решетки (`#`), `End` ключевое слово завершает блок предварительной обработки, представленный соответствующей директивой.</span><span class="sxs-lookup"><span data-stu-id="01915-142">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  
  
 `#End`  
 <span data-ttu-id="01915-143">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="01915-143">Required.</span></span> <span data-ttu-id="01915-144">Завершает определение блока предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="01915-144">Terminates the definition of the preprocessing block.</span></span>  
  
 `#ExternalSource`  
 <span data-ttu-id="01915-145">Обязателен для завершения блока внешнего источника, начался, сопоставляя [директива #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="01915-145">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span></span>  
  
 `#If`  
 <span data-ttu-id="01915-146">Обязателен для завершения блока условной компиляции, начался, сопоставляя `#If` директивы.</span><span class="sxs-lookup"><span data-stu-id="01915-146">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="01915-147">В разделе [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="01915-147">See [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span></span>  
  
 `#Region`  
 <span data-ttu-id="01915-148">Обязателен для завершения блока региона начался, сопоставляя [директива #Region](../../../visual-basic/language-reference/directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="01915-148">Required to terminate a source region block begun by a matching [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md).</span></span>  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="01915-149">Примечания для разработчиков интеллектуальных устройств</span><span class="sxs-lookup"><span data-stu-id="01915-149">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="01915-150">`End` Оператор, используемый без дополнительных ключевых слов, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="01915-150">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01915-151">См. также</span><span class="sxs-lookup"><span data-stu-id="01915-151">See Also</span></span>  
 [<span data-ttu-id="01915-152">Оператор End</span><span class="sxs-lookup"><span data-stu-id="01915-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
