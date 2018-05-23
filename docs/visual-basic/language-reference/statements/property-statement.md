---
title: Property Statement
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 3f3ced3f0c441518594820f75243c71fb0c3babd
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="property-statement"></a><span data-ttu-id="ada2f-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="ada2f-102">Property Statement</span></span>
<span data-ttu-id="ada2f-103">Объявляет имя свойства и процедуры свойств, используемых для хранения и извлечения значения свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ada2f-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ada2f-105">Части</span><span class="sxs-lookup"><span data-stu-id="ada2f-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="ada2f-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-106">Optional.</span></span> <span data-ttu-id="ada2f-107">Список атрибутов, которые применяются к этому свойству или `Get` или `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ada2f-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="ada2f-108">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="ada2f-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-109">Optional.</span></span> <span data-ttu-id="ada2f-110">Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой она определена.</span><span class="sxs-lookup"><span data-stu-id="ada2f-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="ada2f-111">Свойства по умолчанию, должен принимать параметры и можно задавать и получать без указания имени свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="ada2f-112">Если объявляется свойство как `Default`, нельзя использовать `Private` для свойства или любой из его процедур.</span><span class="sxs-lookup"><span data-stu-id="ada2f-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="ada2f-113">Является необязательным `Property` инструкции и на более одного `Get` и `Set` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ada2f-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="ada2f-114">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="ada2f-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="ada2f-115">Public</span><span class="sxs-lookup"><span data-stu-id="ada2f-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="ada2f-116">Protected</span><span class="sxs-lookup"><span data-stu-id="ada2f-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="ada2f-117">Friend</span><span class="sxs-lookup"><span data-stu-id="ada2f-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="ada2f-118">Закрытые</span><span class="sxs-lookup"><span data-stu-id="ada2f-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="ada2f-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="ada2f-119">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md) 

    - [<span data-ttu-id="ada2f-120">Protected Private</span><span class="sxs-lookup"><span data-stu-id="ada2f-120">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="ada2f-121">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-121">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="ada2f-122">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-122">Optional.</span></span> <span data-ttu-id="ada2f-123">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="ada2f-123">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="ada2f-124">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="ada2f-124">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="ada2f-125">Переопределения</span><span class="sxs-lookup"><span data-stu-id="ada2f-125">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="ada2f-126">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="ada2f-126">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="ada2f-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ada2f-127">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="ada2f-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="ada2f-128">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="ada2f-129">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-129">Optional.</span></span> <span data-ttu-id="ada2f-130">В разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-130">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="ada2f-131">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-131">Optional.</span></span> <span data-ttu-id="ada2f-132">В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-132">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="ada2f-133">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-133">Optional.</span></span> <span data-ttu-id="ada2f-134">В разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-134">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="ada2f-135">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-135">Optional.</span></span> <span data-ttu-id="ada2f-136">В разделе [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-136">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="ada2f-137">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-137">Optional.</span></span> <span data-ttu-id="ada2f-138">В разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-138">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="ada2f-139">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ada2f-139">Required.</span></span> <span data-ttu-id="ada2f-140">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-140">Name of the property.</span></span> <span data-ttu-id="ada2f-141">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-141">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="ada2f-142">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-142">Optional.</span></span> <span data-ttu-id="ada2f-143">Список имен локальных переменных, представляющих параметры этого свойства и возможные дополнительные параметры `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ada2f-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="ada2f-144">В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-144">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="ada2f-145">Обязателен, если `Option``Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-145">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="ada2f-146">Тип данных значения, возвращаемого этим свойством.</span><span class="sxs-lookup"><span data-stu-id="ada2f-146">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="ada2f-147">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-147">Optional.</span></span> <span data-ttu-id="ada2f-148">Указывает, что это свойство реализует один или несколько свойств, каждая из которых определена в интерфейс, реализуемый это свойство классом или структурой.</span><span class="sxs-lookup"><span data-stu-id="ada2f-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="ada2f-149">В разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-149">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="ada2f-150">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="ada2f-151">Список реализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="ada2f-151">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="ada2f-152">Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="ada2f-152">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="ada2f-153">Отделение</span><span class="sxs-lookup"><span data-stu-id="ada2f-153">Part</span></span>|<span data-ttu-id="ada2f-154">Описание</span><span class="sxs-lookup"><span data-stu-id="ada2f-154">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="ada2f-155">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ada2f-155">Required.</span></span> <span data-ttu-id="ada2f-156">Имя интерфейса, реализуемого этим свойством, содержащего класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="ada2f-156">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="ada2f-157">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ada2f-157">Required.</span></span> <span data-ttu-id="ada2f-158">Имя, с помощью которого это свойство определено в `interface`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-158">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="ada2f-159">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-159">Optional.</span></span> <span data-ttu-id="ada2f-160">Требуется, если свойство помечено как `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-160">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="ada2f-161">Запускает `Get` свойство процедуру, которая используется для возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="ada2f-162">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-162">Optional.</span></span> <span data-ttu-id="ada2f-163">Блок операторов для работы в рамках `Get` или `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ada2f-163">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="ada2f-164">Завершает `Get` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-164">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="ada2f-165">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ada2f-165">Optional.</span></span> <span data-ttu-id="ada2f-166">Требуется, если свойство помечено как `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-166">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="ada2f-167">Запускает `Set` свойство процедуру, которая используется для хранения значения свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-167">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="ada2f-168">Завершает `Set` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-168">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="ada2f-169">Завершает определение данного свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-169">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ada2f-170">Примечания</span><span class="sxs-lookup"><span data-stu-id="ada2f-170">Remarks</span></span>  
 <span data-ttu-id="ada2f-171">`Property` Оператор представляет объявление свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-171">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="ada2f-172">Свойство может иметь `Get` (только для чтения), процедура `Set` процедура (только запись) или обе (чтение и запись).</span><span class="sxs-lookup"><span data-stu-id="ada2f-172">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="ada2f-173">Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-173">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="ada2f-174">Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-174">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="ada2f-175">Можно использовать `Property` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="ada2f-175">You can use `Property` only at class level.</span></span> <span data-ttu-id="ada2f-176">Это означает *контекст объявления* свойство должно быть класс, структура, модуль или интерфейс, оно не может быть исходным файлом, пространство имен, процедура или блок.</span><span class="sxs-lookup"><span data-stu-id="ada2f-176">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="ada2f-177">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ada2f-177">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="ada2f-178">По умолчанию свойства используют общий доступ.</span><span class="sxs-lookup"><span data-stu-id="ada2f-178">By default, properties use public access.</span></span> <span data-ttu-id="ada2f-179">Можно настроить уровень доступа свойства с модификатором доступа на `Property` инструкции и позволяет настроить один из его процедур более строгий уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="ada2f-179">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="ada2f-180">Visual Basic передает параметр `Set` процедуры во время назначения свойств.</span><span class="sxs-lookup"><span data-stu-id="ada2f-180">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="ada2f-181">Если не указать параметр для `Set`, интегрированной среды разработки (IDE) использует неявный параметр с именем `value`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-181">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="ada2f-182">Этот параметр содержит значение, присваиваемое свойству.</span><span class="sxs-lookup"><span data-stu-id="ada2f-182">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="ada2f-183">Обычно сохраните значение в частной локальной переменной и возвращается при каждом `Get` при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="ada2f-183">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ada2f-184">Правила</span><span class="sxs-lookup"><span data-stu-id="ada2f-184">Rules</span></span>  
  
-   <span data-ttu-id="ada2f-185">**Смешанные уровни доступа.**</span><span class="sxs-lookup"><span data-stu-id="ada2f-185">**Mixed Access Levels.**</span></span> <span data-ttu-id="ada2f-186">При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба.</span><span class="sxs-lookup"><span data-stu-id="ada2f-186">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="ada2f-187">После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-187">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="ada2f-188">Например, если свойство объявлено `Friend`, можно объявить `Set` процедура `Private`, но не `Public`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-188">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="ada2f-189">При определении `ReadOnly` или `WriteOnly` свойство, одна процедура (`Get` или `Set`соответственно) представляет все свойство.</span><span class="sxs-lookup"><span data-stu-id="ada2f-189">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="ada2f-190">Нельзя объявлять другой уровень доступа для процедуры, так как это установит два уровня доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-190">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="ada2f-191">**Тип возвращаемого значения.**</span><span class="sxs-lookup"><span data-stu-id="ada2f-191">**Return Type.**</span></span> <span data-ttu-id="ada2f-192">`Property` Инструкции можно объявить тип данных, возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="ada2f-192">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="ada2f-193">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ada2f-193">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="ada2f-194">Если вы не укажете `returntype`, это свойство возвращает `Object`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-194">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="ada2f-195">**Реализация.**</span><span class="sxs-lookup"><span data-stu-id="ada2f-195">**Implementation.**</span></span> <span data-ttu-id="ada2f-196">Если это свойство использует `Implements` ключевое слово, содержащего класса или структуры, должен иметь `Implements` инструкции сразу после его `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ada2f-196">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="ada2f-197">`Implements` Инструкция должна включать каждого интерфейса, указанным в `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="ada2f-197">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="ada2f-198">Тем не менее имя, по которому интерфейс определяет `Property` (в `definedname`) не должен совпадать с именем этого свойства (в `name`).</span><span class="sxs-lookup"><span data-stu-id="ada2f-198">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ada2f-199">Поведение</span><span class="sxs-lookup"><span data-stu-id="ada2f-199">Behavior</span></span>  
  
-   <span data-ttu-id="ada2f-200">**Возвращение из процедуры свойства.**</span><span class="sxs-lookup"><span data-stu-id="ada2f-200">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="ada2f-201">Когда `Get` или `Set` процедура возвращает в вызывающий код, выполнение продолжается с оператора, следующего инструкции, вызвавшей его.</span><span class="sxs-lookup"><span data-stu-id="ada2f-201">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="ada2f-202">`Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-202">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="ada2f-203">Любое количество `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Property` и `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ada2f-203">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="ada2f-204">**Возвращаемое значение.**</span><span class="sxs-lookup"><span data-stu-id="ada2f-204">**Return Value.**</span></span> <span data-ttu-id="ada2f-205">Для возврата значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ada2f-205">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="ada2f-206">В следующем примере возвращаемое значение присваивается имя свойства `quoteForTheDay` , а затем использует `Exit Property` для возврата.</span><span class="sxs-lookup"><span data-stu-id="ada2f-206">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="ada2f-207">Если вы используете `Exit Property` без присвоения значения `name`, `Get` процедура возвращает значение по умолчанию для типа данных свойства.</span><span class="sxs-lookup"><span data-stu-id="ada2f-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="ada2f-208">`Return` Оператор, в то же время назначает `Get` процедура возвращать значение и завершает процедуру.</span><span class="sxs-lookup"><span data-stu-id="ada2f-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="ada2f-209">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ada2f-209">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="ada2f-210">Пример</span><span class="sxs-lookup"><span data-stu-id="ada2f-210">Example</span></span>  
 <span data-ttu-id="ada2f-211">В следующем примере объявляется свойство в классе.</span><span class="sxs-lookup"><span data-stu-id="ada2f-211">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ada2f-212">См. также</span><span class="sxs-lookup"><span data-stu-id="ada2f-212">See Also</span></span>  
 [<span data-ttu-id="ada2f-213">Автоматически реализуемые свойства</span><span class="sxs-lookup"><span data-stu-id="ada2f-213">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="ada2f-214">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="ada2f-214">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="ada2f-215">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="ada2f-215">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="ada2f-216">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="ada2f-216">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="ada2f-217">Список параметров</span><span class="sxs-lookup"><span data-stu-id="ada2f-217">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="ada2f-218">Default</span><span class="sxs-lookup"><span data-stu-id="ada2f-218">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
