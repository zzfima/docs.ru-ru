---
title: Оператор End <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343738"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="69efa-102">End \<ключевое слово > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69efa-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="69efa-103">Если за ним следует дополнительное ключевое слово, завершает определение блока операторов, представленного этим ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="69efa-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="69efa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69efa-104">Syntax</span></span>

```vb
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
  
## <a name="parts"></a><span data-ttu-id="69efa-105">Части</span><span class="sxs-lookup"><span data-stu-id="69efa-105">Parts</span></span>

|<span data-ttu-id="69efa-106">Отделение</span><span class="sxs-lookup"><span data-stu-id="69efa-106">Part</span></span>|<span data-ttu-id="69efa-107">Описание</span><span class="sxs-lookup"><span data-stu-id="69efa-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="69efa-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="69efa-108">Required.</span></span> <span data-ttu-id="69efa-109">Завершает определение программного элемента.</span><span class="sxs-lookup"><span data-stu-id="69efa-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="69efa-110">Требуется для завершения `AddHandler` метода доступа, начатого соответствующей инструкцией `AddHandler` в пользовательской [инструкции Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="69efa-111">Требуется для завершения определения класса, начатого соответствующим [оператором класса](class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="69efa-112">Требуется для завершения определения перечисления, начатого соответствующей [инструкцией enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="69efa-113">Требуется для завершения `Custom` определения события, начатого соответствующей [инструкцией Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="69efa-114">Требуется для завершения `Function` определения процедуры, начатой соответствующей [инструкцией Function](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="69efa-115">Если при выполнении обнаруживается оператор `End Function`, управление возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="69efa-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="69efa-116">Требуется для завершения `Property` определения процедуры, начатой соответствующей [инструкцией GET](get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="69efa-117">Если при выполнении обнаруживается оператор `End Get`, управление возвращается инструкции, запрашивающей значение свойства.</span><span class="sxs-lookup"><span data-stu-id="69efa-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="69efa-118">Требуется для завершения `If`...`Then`...`Else` определения блока, начатого соответствующей инструкцией `If`.</span><span class="sxs-lookup"><span data-stu-id="69efa-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="69efa-119">См. раздел [If... Затем... Else, инструкция](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="69efa-120">Требуется для завершения определения интерфейса, начатого соответствующей [инструкцией интерфейса](interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="69efa-121">Требуется для завершения определения модуля, начатого соответствующим [оператором модуля](module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="69efa-122">Требуется для завершения определения пространства имен, начатого соответствующей [инструкцией Namespace](namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="69efa-123">Требуется для завершения определения оператора, начатого соответствующим [оператором оператора](operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="69efa-124">Требуется для завершения определения свойства, начатого соответствующим [оператором Property](property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="69efa-125">Требуется для завершения `RaiseEvent` метода доступа, начатого соответствующей инструкцией `RaiseEvent` в пользовательской [инструкции Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="69efa-126">Требуется для завершения `RemoveHandler` метода доступа, начатого соответствующей инструкцией `RemoveHandler` в пользовательской [инструкции Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="69efa-127">Требуется для завершения `Select`...`Case` определения блока, начатого соответствующей инструкцией `Select`.</span><span class="sxs-lookup"><span data-stu-id="69efa-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="69efa-128">См. раздел [SELECT... Case, инструкция](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="69efa-129">Требуется для завершения `Property` определения процедуры, начатой соответствующей [инструкцией SET](set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="69efa-130">Если при выполнении обнаруживается оператор `End Set`, управление возвращается в инструкцию, устанавливая значение свойства.</span><span class="sxs-lookup"><span data-stu-id="69efa-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="69efa-131">Требуется для завершения определения структуры, начатой соответствующей [инструкцией Structure](structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="69efa-132">Требуется для завершения `Sub` определения процедуры, начатой соответствующим [оператором подвыражения](sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="69efa-133">Если при выполнении обнаруживается оператор `End Sub`, управление возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="69efa-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="69efa-134">Требуется для завершения определения блока `SyncLock`, начатого соответствующей инструкцией `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="69efa-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="69efa-135">См. раздел [оператор SyncLock](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="69efa-136">Требуется для завершения `Try`...`Catch`...`Finally` определения блока, начатого соответствующей инструкцией `Try`.</span><span class="sxs-lookup"><span data-stu-id="69efa-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="69efa-137">См [. раздел try... Перехватить... Оператор finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="69efa-138">Требуется для завершения определения цикла `While`, начатого соответствующей инструкцией `While`.</span><span class="sxs-lookup"><span data-stu-id="69efa-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="69efa-139">См [. раздел while... Конец оператора while](while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="69efa-140">Требуется для завершения определения блока `With`, начатого соответствующей инструкцией `With`.</span><span class="sxs-lookup"><span data-stu-id="69efa-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="69efa-141">См [. раздел with... Конец оператора](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="69efa-142">Директивы</span><span class="sxs-lookup"><span data-stu-id="69efa-142">Directives</span></span>

<span data-ttu-id="69efa-143">Если перед ним стоит знак решетки (`#`), ключевое слово `End` завершает блок предварительной обработки, представленный соответствующей директивой.</span><span class="sxs-lookup"><span data-stu-id="69efa-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="69efa-144">Отделение</span><span class="sxs-lookup"><span data-stu-id="69efa-144">Part</span></span>|<span data-ttu-id="69efa-145">Описание</span><span class="sxs-lookup"><span data-stu-id="69efa-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="69efa-146">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="69efa-146">Required.</span></span> <span data-ttu-id="69efa-147">Завершает определение блока предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="69efa-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="69efa-148">Требуется для завершения внешнего блока источника, начатого соответствующей [директивой #ExternalSource](../directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="69efa-149">Требуется для завершения блока условной компиляции, начатого соответствующей директивой `#If`.</span><span class="sxs-lookup"><span data-stu-id="69efa-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="69efa-150">См [. #If... Then... #Else директивы](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="69efa-151">Требуется для завершения блока исходного региона, начатого соответствующей [директивой #Region](../directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="69efa-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="69efa-152">Примечания</span><span class="sxs-lookup"><span data-stu-id="69efa-152">Remarks</span></span>

<span data-ttu-id="69efa-153">[Оператор End](end-statement.md)без дополнительного ключевого слова завершает выполнение немедленно.</span><span class="sxs-lookup"><span data-stu-id="69efa-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="69efa-154">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="69efa-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="69efa-155">Инструкция `End` без дополнительного ключевого слова не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="69efa-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69efa-156">См. также</span><span class="sxs-lookup"><span data-stu-id="69efa-156">See also</span></span>

- [<span data-ttu-id="69efa-157">Оператор End</span><span class="sxs-lookup"><span data-stu-id="69efa-157">End Statement</span></span>](end-statement.md)
