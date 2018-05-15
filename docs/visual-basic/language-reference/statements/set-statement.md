---
title: Инструкция Set (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: dbc48d14bac54809e4ddd12c87429bf407169950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="5c6b4-102">Инструкция Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c6b4-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="5c6b4-103">Объявляет `Set` процедуру, которая используется для присвоения значения свойству.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c6b4-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="5c6b4-105">Части</span><span class="sxs-lookup"><span data-stu-id="5c6b4-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="5c6b4-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-106">Optional.</span></span> <span data-ttu-id="5c6b4-107">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b4-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="5c6b4-108">Необязательный на более одного `Get` и `Set` инструкции в этом свойстве.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="5c6b4-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="5c6b4-110">Protected</span><span class="sxs-lookup"><span data-stu-id="5c6b4-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [<span data-ttu-id="5c6b4-111">Friend</span><span class="sxs-lookup"><span data-stu-id="5c6b4-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [<span data-ttu-id="5c6b4-112">Закрытые</span><span class="sxs-lookup"><span data-stu-id="5c6b4-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 <span data-ttu-id="5c6b4-113">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b4-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="5c6b4-114">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-114">Required.</span></span> <span data-ttu-id="5c6b4-115">Параметр, содержащий новое значение для свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="5c6b4-116">Обязателен, если `Option Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="5c6b4-117">Тип данных `value` параметра.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="5c6b4-118">Указанный тип данных должен быть таким же, как тип данных свойства, где это `Set` оператор объявлен.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="5c6b4-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-119">Optional.</span></span> <span data-ttu-id="5c6b4-120">Один или несколько операторов, выполняемых при `Set` вызывается процедура свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="5c6b4-121">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-121">Required.</span></span> <span data-ttu-id="5c6b4-122">Завершает определение `Set` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c6b4-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c6b4-123">Remarks</span></span>  
 <span data-ttu-id="5c6b4-124">Каждое свойство должно иметь `Set` процедуры свойства, если свойство помечено как `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="5c6b4-125">`Set` Процедура используется для задания значения свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="5c6b4-126">Visual Basic автоматически вызывает свойство `Set` процедуру, когда оператор присваивания предоставляет значение хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="5c6b4-127">Visual Basic передает параметр `Set` процедуры во время назначения свойств.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="5c6b4-128">Если не указать параметр для `Set`, интегрированной среды разработки (IDE) использует неявный параметр с именем `value`.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="5c6b4-129">Параметр содержит значение, присваиваемое свойству.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="5c6b4-130">Обычно сохраните значение в частной локальной переменной и возвращается при каждом `Get` при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="5c6b4-131">Тело объявления свойства может содержать только свойства `Get` и `Set` процедур между [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="5c6b4-132">Оно не может хранить ничего, кроме этих процедур.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="5c6b4-133">В частности он не может хранить текущее значение свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="5c6b4-134">Это значение за пределами свойства, необходимо сохранить, поскольку при сохранении внутри любой из процедур свойства, процедуры свойства не может получить доступ к его.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="5c6b4-135">Обычный способ — хранить значение в [закрытый](../../../visual-basic/language-reference/modifiers/private.md) переменной, объявленной в том же уровне, что и свойство.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="5c6b4-136">Необходимо определить `Set` процедуры внутри свойства, к которому он применяется.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="5c6b4-137">`Set` Процедуры по умолчанию устанавливается уровень доступа свойства, содержащего Если вы используете `accessmodifier` в `Set` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5c6b4-138">Правила</span><span class="sxs-lookup"><span data-stu-id="5c6b4-138">Rules</span></span>  
  
-   <span data-ttu-id="5c6b4-139">**Смешанные уровни доступа.**</span><span class="sxs-lookup"><span data-stu-id="5c6b4-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="5c6b4-140">При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="5c6b4-141">После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="5c6b4-142">Например, если свойство объявлено `Friend`, можно объявить `Set` процедура `Private`, но не `Public`.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="5c6b4-143">При определении `WriteOnly` свойства `Set` процедура представляет все свойство.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="5c6b4-144">Нельзя объявлять разные права доступа уровня для `Set`, так как это установит два уровня доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="5c6b4-145">Поведение</span><span class="sxs-lookup"><span data-stu-id="5c6b4-145">Behavior</span></span>  
  
-   <span data-ttu-id="5c6b4-146">**Возвращение из процедуры свойства.**</span><span class="sxs-lookup"><span data-stu-id="5c6b4-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="5c6b4-147">Когда `Set` процедура возвращает в вызывающий код, выполнение продолжается после инструкции, которая предоставляет значение для сохранения.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="5c6b4-148">`Set` процедуры свойств можно вернуть с помощью [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) или [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b4-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="5c6b4-149">`Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="5c6b4-150">Любое количество `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Property` и `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c6b4-151">Пример</span><span class="sxs-lookup"><span data-stu-id="5c6b4-151">Example</span></span>  
 <span data-ttu-id="5c6b4-152">В следующем примере используется `Set` инструкции, чтобы задать значение свойства.</span><span class="sxs-lookup"><span data-stu-id="5c6b4-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5c6b4-153">См. также</span><span class="sxs-lookup"><span data-stu-id="5c6b4-153">See Also</span></span>  
 [<span data-ttu-id="5c6b4-154">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="5c6b4-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="5c6b4-155">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="5c6b4-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="5c6b4-156">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="5c6b4-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="5c6b4-157">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="5c6b4-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
