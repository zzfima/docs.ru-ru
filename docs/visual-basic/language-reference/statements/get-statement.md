---
title: "Оператор Get"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1ff062a5e3bf41794bd5b4c90f1e188d6d97480
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="get-statement"></a><span data-ttu-id="4853b-102">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="4853b-102">Get Statement</span></span>
<span data-ttu-id="4853b-103">Объявляет `Get` процедуру, которая используется для извлечения значения свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4853b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4853b-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="4853b-105">Части</span><span class="sxs-lookup"><span data-stu-id="4853b-105">Parts</span></span>  
  
|<span data-ttu-id="4853b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="4853b-106">Term</span></span>|<span data-ttu-id="4853b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="4853b-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="4853b-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4853b-108">Optional.</span></span> <span data-ttu-id="4853b-109">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4853b-109">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="4853b-110">Необязательный на более одного `Get` и `Set` инструкции в этом свойстве.</span><span class="sxs-lookup"><span data-stu-id="4853b-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="4853b-111">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="4853b-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="4853b-112">-   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="4853b-112">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)</span></span><br /><span data-ttu-id="4853b-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="4853b-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span></span><br /><span data-ttu-id="4853b-114">-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="4853b-114">-   [Private](../../../visual-basic/language-reference/modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="4853b-115">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4853b-115">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="4853b-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4853b-116">Optional.</span></span> <span data-ttu-id="4853b-117">Один или несколько операторов, выполняемых при `Get` вызывается процедура свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="4853b-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4853b-118">Required.</span></span> <span data-ttu-id="4853b-119">Завершает определение `Get` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4853b-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="4853b-120">Remarks</span></span>  
 <span data-ttu-id="4853b-121">Каждое свойство должно иметь `Get` процедуры свойства, если свойство помечено как `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="4853b-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="4853b-122">`Get` Процедура используется для возврата текущего значения свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="4853b-123">Visual Basic автоматически вызывает свойство `Get` процедуры, когда выражение запрашивает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="4853b-124">Тело объявления свойства может содержать только свойства `Get` и `Set` процедур между [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4853b-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="4853b-125">Оно не может хранить ничего, кроме этих процедур.</span><span class="sxs-lookup"><span data-stu-id="4853b-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="4853b-126">В частности он не может хранить текущее значение свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="4853b-127">Это значение за пределами свойства, необходимо сохранить, поскольку при сохранении внутри любой из процедур свойства, процедуры свойства не может получить доступ к его.</span><span class="sxs-lookup"><span data-stu-id="4853b-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="4853b-128">Обычный способ — хранить значение в [закрытый](../../../visual-basic/language-reference/modifiers/private.md) переменной, объявленной в том же уровне, что и свойство.</span><span class="sxs-lookup"><span data-stu-id="4853b-128">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="4853b-129">Необходимо определить `Get` процедуры внутри свойства, к которому он применяется.</span><span class="sxs-lookup"><span data-stu-id="4853b-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="4853b-130">`Get` Процедуры по умолчанию устанавливается уровень доступа свойства, содержащего Если вы используете `accessmodifier` в `Get` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4853b-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4853b-131">Правила</span><span class="sxs-lookup"><span data-stu-id="4853b-131">Rules</span></span>  
  
-   <span data-ttu-id="4853b-132">**Смешанные уровни доступа.**</span><span class="sxs-lookup"><span data-stu-id="4853b-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="4853b-133">При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба.</span><span class="sxs-lookup"><span data-stu-id="4853b-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="4853b-134">После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="4853b-135">Например, если свойство объявлено `Friend`, можно объявить `Get` процедура `Private`, но не `Public`.</span><span class="sxs-lookup"><span data-stu-id="4853b-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="4853b-136">При определении `ReadOnly` свойства `Get` процедура представляет все свойство.</span><span class="sxs-lookup"><span data-stu-id="4853b-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="4853b-137">Нельзя объявлять разные права доступа уровня для `Get`, так как это установит два уровня доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="4853b-138">**Тип возвращаемого значения.**</span><span class="sxs-lookup"><span data-stu-id="4853b-138">**Return Type.**</span></span> <span data-ttu-id="4853b-139">[Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) можно объявить тип данных, возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="4853b-139">The [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="4853b-140">`Get` Процедура автоматически возвращает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="4853b-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="4853b-141">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4853b-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="4853b-142">Если `Property` инструкции не указан `returntype`, процедура возвращает `Object`.</span><span class="sxs-lookup"><span data-stu-id="4853b-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4853b-143">Поведение</span><span class="sxs-lookup"><span data-stu-id="4853b-143">Behavior</span></span>  
  
-   <span data-ttu-id="4853b-144">**Возвращение из процедуры.**</span><span class="sxs-lookup"><span data-stu-id="4853b-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="4853b-145">Когда `Get` процедура возвращает в вызывающий код, выполнение продолжается в операторе, запрошенное значение свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="4853b-146">`Get`процедуры свойств может возвращать значение с помощью [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) , или присвоить возвращаемое значение имени свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-146">`Get` property procedures can return a value using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="4853b-147">Дополнительные сведения см. в разделе «Возвращение значения» в [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4853b-147">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="4853b-148">`Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="4853b-149">Любое количество `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Property` и `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4853b-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="4853b-150">**Возвращаемое значение.**</span><span class="sxs-lookup"><span data-stu-id="4853b-150">**Return Value.**</span></span> <span data-ttu-id="4853b-151">Для возврата значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4853b-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span> <span data-ttu-id="4853b-152">`Return` Оператор назначает одновременно `Get` процедура возвращать значение и завершает процедуру.</span><span class="sxs-lookup"><span data-stu-id="4853b-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="4853b-153">Если вы используете `Exit Property` без присвоения значения имени свойства `Get` процедура возвращает значение по умолчанию для типа данных свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="4853b-154">Дополнительные сведения см. в разделе «Возвращение значения» в [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4853b-154">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="4853b-155">В следующем примере показано два способа только для чтения свойство `quoteForTheDay` может возвращать значение, содержащееся в закрытой переменной `quoteValue`.</span><span class="sxs-lookup"><span data-stu-id="4853b-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="4853b-156">Пример</span><span class="sxs-lookup"><span data-stu-id="4853b-156">Example</span></span>  
 <span data-ttu-id="4853b-157">В следующем примере используется `Get` для возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="4853b-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4853b-158">См. также</span><span class="sxs-lookup"><span data-stu-id="4853b-158">See Also</span></span>  
 [<span data-ttu-id="4853b-159">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="4853b-159">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="4853b-160">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="4853b-160">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="4853b-161">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="4853b-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="4853b-162">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="4853b-162">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="4853b-163">Пошаговое руководство. Определение классов</span><span class="sxs-lookup"><span data-stu-id="4853b-163">Walkthrough: Defining Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
