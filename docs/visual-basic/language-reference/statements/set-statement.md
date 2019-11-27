---
title: Оператор Set
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
ms.openlocfilehash: 75ad6d87f1785fea13a282d953f117c9c234e203
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349558"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="0172b-102">Инструкция Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0172b-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="0172b-103">Объявляет процедуру свойства `Set`, используемую для присвоения значения свойству.</span><span class="sxs-lookup"><span data-stu-id="0172b-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0172b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0172b-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="0172b-105">Части</span><span class="sxs-lookup"><span data-stu-id="0172b-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="0172b-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0172b-106">Optional.</span></span> <span data-ttu-id="0172b-107">См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="0172b-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="0172b-108">(Необязательно) не более одного из инструкций `Get` и `Set` в этом свойстве.</span><span class="sxs-lookup"><span data-stu-id="0172b-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="0172b-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="0172b-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="0172b-110">Protected</span><span class="sxs-lookup"><span data-stu-id="0172b-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="0172b-111">Friend</span><span class="sxs-lookup"><span data-stu-id="0172b-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="0172b-112">Закрытые</span><span class="sxs-lookup"><span data-stu-id="0172b-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="0172b-113">См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0172b-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="0172b-114">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0172b-114">Required.</span></span> <span data-ttu-id="0172b-115">Параметр, содержащий новое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="0172b-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="0172b-116">Требуется, если `Option Strict` `On`.</span><span class="sxs-lookup"><span data-stu-id="0172b-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="0172b-117">Тип данных параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="0172b-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="0172b-118">Указанный тип данных должен совпадать с типом данных свойства, в котором объявлена эта `Set`ая инструкция.</span><span class="sxs-lookup"><span data-stu-id="0172b-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="0172b-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0172b-119">Optional.</span></span> <span data-ttu-id="0172b-120">Одна или несколько инструкций, выполняемых при вызове процедуры свойства `Set`.</span><span class="sxs-lookup"><span data-stu-id="0172b-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="0172b-121">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0172b-121">Required.</span></span> <span data-ttu-id="0172b-122">Завершает определение процедуры свойства `Set`.</span><span class="sxs-lookup"><span data-stu-id="0172b-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0172b-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="0172b-123">Remarks</span></span>  
 <span data-ttu-id="0172b-124">Каждое свойство должно иметь `Set` процедуру свойства, если только свойство не помечено как `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="0172b-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="0172b-125">Процедура `Set` используется для задания значения свойства.</span><span class="sxs-lookup"><span data-stu-id="0172b-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="0172b-126">Visual Basic автоматически вызывает процедуру `Set` свойства, когда оператор присваивания предоставляет значение, которое должно храниться в свойстве.</span><span class="sxs-lookup"><span data-stu-id="0172b-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="0172b-127">Visual Basic передает параметр в процедуру `Set` во время назначения свойств.</span><span class="sxs-lookup"><span data-stu-id="0172b-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="0172b-128">Если параметр для `Set`не указан, в интегрированной среде разработки (IDE) используется неявный параметр с именем `value`.</span><span class="sxs-lookup"><span data-stu-id="0172b-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="0172b-129">Параметр содержит значение, присваиваемое свойству.</span><span class="sxs-lookup"><span data-stu-id="0172b-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="0172b-130">Обычно это значение сохраняется в закрытой локальной переменной и возвращается при каждом вызове процедуры `Get`.</span><span class="sxs-lookup"><span data-stu-id="0172b-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="0172b-131">Тело объявления свойства может содержать только `Get` и `Set` процедуры свойства между [оператором Property](../../../visual-basic/language-reference/statements/property-statement.md) и оператором `End Property`.</span><span class="sxs-lookup"><span data-stu-id="0172b-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="0172b-132">Он не может хранить ничего, Кроме этих процедур.</span><span class="sxs-lookup"><span data-stu-id="0172b-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="0172b-133">В частности, он не может хранить текущее значение свойства.</span><span class="sxs-lookup"><span data-stu-id="0172b-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="0172b-134">Это значение необходимо хранить за пределами свойства, так как при хранении в любой из процедур свойств другая процедура свойства не может получить к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="0172b-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="0172b-135">Обычным подходом является сохранение значения в [закрытой](../../../visual-basic/language-reference/modifiers/private.md) переменной, объявленной на том же уровне, что и свойство.</span><span class="sxs-lookup"><span data-stu-id="0172b-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="0172b-136">Необходимо определить `Set` процедуру внутри свойства, к которому она применяется.</span><span class="sxs-lookup"><span data-stu-id="0172b-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="0172b-137">`Set` процедура по умолчанию имеет уровень доступа содержащего его свойства, если в инструкции `Set` не используется `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="0172b-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0172b-138">Правила</span><span class="sxs-lookup"><span data-stu-id="0172b-138">Rules</span></span>  
  
- <span data-ttu-id="0172b-139">**Уровни смешанного доступа.**</span><span class="sxs-lookup"><span data-stu-id="0172b-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="0172b-140">Если вы определяете свойство для чтения и записи, при необходимости можно указать другой уровень доступа либо для `Get`, либо для `Set` процедуры, но не для обоих.</span><span class="sxs-lookup"><span data-stu-id="0172b-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="0172b-141">В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства.</span><span class="sxs-lookup"><span data-stu-id="0172b-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="0172b-142">Например, если свойство объявлено `Friend`, можно объявить `Set` процедуру `Private`, но не `Public`.</span><span class="sxs-lookup"><span data-stu-id="0172b-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="0172b-143">При определении свойства `WriteOnly` `Set` процедура представляет все свойство.</span><span class="sxs-lookup"><span data-stu-id="0172b-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="0172b-144">Нельзя объявить другой уровень доступа для `Set`, так как для свойства будет задано два уровня доступа.</span><span class="sxs-lookup"><span data-stu-id="0172b-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="0172b-145">Поведение</span><span class="sxs-lookup"><span data-stu-id="0172b-145">Behavior</span></span>  
  
- <span data-ttu-id="0172b-146">**Возврат из процедуры свойства.**</span><span class="sxs-lookup"><span data-stu-id="0172b-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="0172b-147">Когда процедура `Set` возвращается в вызывающий код, выполнение продолжится после оператора, который предоставил значение для сохранения.</span><span class="sxs-lookup"><span data-stu-id="0172b-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="0172b-148">`Set` процедуры свойств могут возвращаться с помощью [оператора return](../../../visual-basic/language-reference/statements/return-statement.md) или [оператора Exit](../../../visual-basic/language-reference/statements/exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0172b-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="0172b-149">Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="0172b-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="0172b-150">Любое число инструкций `Exit Property` и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Property` и `Return` операторы.</span><span class="sxs-lookup"><span data-stu-id="0172b-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0172b-151">Пример</span><span class="sxs-lookup"><span data-stu-id="0172b-151">Example</span></span>  
 <span data-ttu-id="0172b-152">В следующем примере оператор `Set` используется для задания значения свойства.</span><span class="sxs-lookup"><span data-stu-id="0172b-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="0172b-153">См. также</span><span class="sxs-lookup"><span data-stu-id="0172b-153">See also</span></span>

- [<span data-ttu-id="0172b-154">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="0172b-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="0172b-155">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="0172b-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="0172b-156">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="0172b-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="0172b-157">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="0172b-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
