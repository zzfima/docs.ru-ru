---
title: "Оператор Property | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
dev_langs:
- VB
helpviewer_keywords:
- Property statement
- default modifier
- property procedures, Property statements
- Property keyword
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: dbd779b4b6a1dd167e8581066b0fbe034cd2d8f2
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="property-statement"></a><span data-ttu-id="63216-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="63216-102">Property Statement</span></span>
<span data-ttu-id="63216-103">Объявляет имя свойства и процедуры свойства, используемые для хранения и извлечения значения свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63216-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63216-104">Syntax</span></span>  
  
```  
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
  
## <a name="parts"></a><span data-ttu-id="63216-105">Части</span><span class="sxs-lookup"><span data-stu-id="63216-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="63216-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-106">Optional.</span></span> <span data-ttu-id="63216-107">Список атрибутов, применяемых к этому свойству или `Get` или `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="63216-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="63216-108">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="63216-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="63216-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-109">Optional.</span></span> <span data-ttu-id="63216-110">Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой она определена.</span><span class="sxs-lookup"><span data-stu-id="63216-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="63216-111">Свойства по умолчанию, должен принимать параметры и их можно задавать и получать без указания имени свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="63216-112">Если объявить свойство как `Default`, нельзя использовать `Private` для свойства или любой из его процедур.</span><span class="sxs-lookup"><span data-stu-id="63216-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="63216-113">Является необязательным `Property` инструкции и на более одного `Get` и `Set` инструкции.</span><span class="sxs-lookup"><span data-stu-id="63216-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="63216-114">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="63216-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="63216-115">Public</span><span class="sxs-lookup"><span data-stu-id="63216-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="63216-116">Protected</span><span class="sxs-lookup"><span data-stu-id="63216-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="63216-117">Friend</span><span class="sxs-lookup"><span data-stu-id="63216-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="63216-118">Закрытые</span><span class="sxs-lookup"><span data-stu-id="63216-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="63216-119">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="63216-119">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="63216-120">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-120">Optional.</span></span> <span data-ttu-id="63216-121">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="63216-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="63216-122">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="63216-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="63216-123">Переопределения</span><span class="sxs-lookup"><span data-stu-id="63216-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="63216-124">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="63216-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="63216-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="63216-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="63216-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="63216-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="63216-127">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-127">Optional.</span></span> <span data-ttu-id="63216-128">В разделе [общего](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="63216-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="63216-129">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-129">Optional.</span></span> <span data-ttu-id="63216-130">В разделе [тени](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="63216-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="63216-131">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-131">Optional.</span></span> <span data-ttu-id="63216-132">В разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="63216-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="63216-133">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-133">Optional.</span></span> <span data-ttu-id="63216-134">В разделе [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="63216-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="63216-135">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-135">Optional.</span></span> <span data-ttu-id="63216-136">В разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="63216-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="63216-137">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-137">Required.</span></span> <span data-ttu-id="63216-138">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-138">Name of the property.</span></span> <span data-ttu-id="63216-139">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="63216-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="63216-140">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-140">Optional.</span></span> <span data-ttu-id="63216-141">Список имен локальных переменных, представляющих параметры этого свойства и возможные дополнительные параметры `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="63216-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="63216-142">В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="63216-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="63216-143">Обязателен, если `Option``Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="63216-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="63216-144">Тип данных значения, возвращаемого этим свойством.</span><span class="sxs-lookup"><span data-stu-id="63216-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="63216-145">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-145">Optional.</span></span> <span data-ttu-id="63216-146">Указывает, что это свойство реализует одно или несколько свойств, каждая из которых определена в интерфейс, реализуемый этого свойства классом или структурой.</span><span class="sxs-lookup"><span data-stu-id="63216-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="63216-147">В разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="63216-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="63216-148">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="63216-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="63216-149">Список реализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="63216-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="63216-150">Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="63216-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="63216-151">Отделение</span><span class="sxs-lookup"><span data-stu-id="63216-151">Part</span></span>|<span data-ttu-id="63216-152">Описание</span><span class="sxs-lookup"><span data-stu-id="63216-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="63216-153">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-153">Required.</span></span> <span data-ttu-id="63216-154">Имя интерфейса, реализуемого этим свойством, содержащей класс или структуру.</span><span class="sxs-lookup"><span data-stu-id="63216-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="63216-155">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-155">Required.</span></span> <span data-ttu-id="63216-156">Имя, в котором определено свойство `interface`.</span><span class="sxs-lookup"><span data-stu-id="63216-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="63216-157">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-157">Optional.</span></span> <span data-ttu-id="63216-158">Требуется, если свойство помечено как `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="63216-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="63216-159">Запускает `Get` свойство процедуру, которая используется для возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="63216-160">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-160">Optional.</span></span> <span data-ttu-id="63216-161">Блок операторов для выполнения в `Get` или `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="63216-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="63216-162">Завершает `Get` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="63216-163">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="63216-163">Optional.</span></span> <span data-ttu-id="63216-164">Требуется, если свойство помечено как `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="63216-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="63216-165">Запускает `Set` свойство процедура, используемая для хранения значения свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="63216-166">Завершает `Set` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="63216-167">Завершает определение данного свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63216-168">Примечания</span><span class="sxs-lookup"><span data-stu-id="63216-168">Remarks</span></span>  
 <span data-ttu-id="63216-169">`Property` Инструкция содержит объявление свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="63216-170">Свойство может иметь `Get` (только для чтения), процедура `Set` процедура (только запись), или обе (чтение и запись).</span><span class="sxs-lookup"><span data-stu-id="63216-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="63216-171">Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="63216-172">Дополнительные сведения см. в разделе [Auto-Implemented свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="63216-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="63216-173">Можно использовать `Property` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="63216-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="63216-174">Это означает *контекст объявления* свойства должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="63216-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="63216-175">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="63216-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="63216-176">По умолчанию свойства используют общий доступ.</span><span class="sxs-lookup"><span data-stu-id="63216-176">By default, properties use public access.</span></span> <span data-ttu-id="63216-177">Можно настроить уровень доступа свойства с модификатором доступа на `Property` инструкции и можно при необходимости настроить одну из его процедур на более строгий уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="63216-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="63216-178">Visual Basic передает параметр `Set` процедуры во время назначения свойств.</span><span class="sxs-lookup"><span data-stu-id="63216-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="63216-179">Если не указать параметр для `Set`, интегрированную среду разработки (IDE) использует неявный параметр с именем `value`.</span><span class="sxs-lookup"><span data-stu-id="63216-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="63216-180">Этот параметр содержит значение, присваиваемое свойству.</span><span class="sxs-lookup"><span data-stu-id="63216-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="63216-181">Обычно хранить данное значение в закрытой локальной переменной и возвращается при каждом `Get` при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="63216-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="63216-182">Правила</span><span class="sxs-lookup"><span data-stu-id="63216-182">Rules</span></span>  
  
-   <span data-ttu-id="63216-183">**Смешанные уровни доступа.**</span><span class="sxs-lookup"><span data-stu-id="63216-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="63216-184">При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба.</span><span class="sxs-lookup"><span data-stu-id="63216-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="63216-185">После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="63216-186">Например, если свойство объявлено `Friend`, можно объявить `Set` процедура `Private`, но не `Public`.</span><span class="sxs-lookup"><span data-stu-id="63216-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="63216-187">При определении `ReadOnly` или `WriteOnly` свойство, одна процедура (`Get` или `Set`соответственно) представляет все свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="63216-188">Нельзя объявлять другой уровень доступа для такой процедуры, так как это установит два уровня доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="63216-189">**Возвращаемый тип.**</span><span class="sxs-lookup"><span data-stu-id="63216-189">**Return Type.**</span></span> <span data-ttu-id="63216-190">`Property` Оператора можно объявлять тип данных, возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="63216-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="63216-191">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="63216-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="63216-192">Если вы не укажете `returntype`, это свойство возвращает `Object`.</span><span class="sxs-lookup"><span data-stu-id="63216-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="63216-193">**Реализация.**</span><span class="sxs-lookup"><span data-stu-id="63216-193">**Implementation.**</span></span> <span data-ttu-id="63216-194">Если это свойство использует `Implements` должен иметь ключевое слово, содержащего класса или структуры `Implements` инструкции сразу после его `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="63216-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="63216-195">`Implements` Инструкция должна включать интерфейсов, указанных в `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="63216-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="63216-196">Тем не менее имя, по которому определяется интерфейс `Property` (в `definedname`) не обязательно совпадает с именем данного свойства (в `name`).</span><span class="sxs-lookup"><span data-stu-id="63216-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="63216-197">Поведение</span><span class="sxs-lookup"><span data-stu-id="63216-197">Behavior</span></span>  
  
-   <span data-ttu-id="63216-198">**Возвращение из процедуры свойства.**</span><span class="sxs-lookup"><span data-stu-id="63216-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="63216-199">Когда `Get` или `Set` процедура возвращает вызывающему коду, выполнение продолжается с оператора, следующего инструкцию, которая его вызвала.</span><span class="sxs-lookup"><span data-stu-id="63216-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="63216-200">`Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="63216-201">Любое число `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и можно смешивать `Exit Property` и `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="63216-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="63216-202">**Возвращаемое значение.**</span><span class="sxs-lookup"><span data-stu-id="63216-202">**Return Value.**</span></span> <span data-ttu-id="63216-203">Для возврата значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="63216-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="63216-204">В следующем примере возвращаемое значение присваивается имени свойства `quoteForTheDay` , а затем использует `Exit Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="63216-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     <span data-ttu-id="63216-205">[!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="63216-205">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="63216-206">[!code-vb[VbVbalrStatements&#28;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="63216-206">[!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span></span>  
  
     <span data-ttu-id="63216-207">Если вы используете `Exit Property` без присвоения значения `name`, `Get` процедура возвращает значение по умолчанию для типа данных свойства.</span><span class="sxs-lookup"><span data-stu-id="63216-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="63216-208">`Return` Оператор, в то же время назначает `Get` процедура возвращает значение и завершает процедуру.</span><span class="sxs-lookup"><span data-stu-id="63216-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="63216-209">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="63216-209">The following example shows this.</span></span>  
  
     <span data-ttu-id="63216-210">[!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="63216-210">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="63216-211">[!code-vb[VbVbalrStatements&#29;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="63216-211">[!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="63216-212">Пример</span><span class="sxs-lookup"><span data-stu-id="63216-212">Example</span></span>  
 <span data-ttu-id="63216-213">В следующем примере объявляется свойство в классе.</span><span class="sxs-lookup"><span data-stu-id="63216-213">The following example declares a property in a class.</span></span>  
  
 <span data-ttu-id="63216-214">[!code-vb[VbVbalrStatements&#51;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="63216-214">[!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63216-215">См. также</span><span class="sxs-lookup"><span data-stu-id="63216-215">See Also</span></span>  
 <span data-ttu-id="63216-216">[Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span><span class="sxs-lookup"><span data-stu-id="63216-216">[Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span></span>  
<span data-ttu-id="63216-217"> [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="63216-217"> [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="63216-218"> [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="63216-218"> [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="63216-219"> [Инструкции SET](../../../visual-basic/language-reference/statements/set-statement.md) </span><span class="sxs-lookup"><span data-stu-id="63216-219"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) </span></span>  
<span data-ttu-id="63216-220"> [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="63216-220"> [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) </span></span>  
<span data-ttu-id="63216-221"> [Default](../../../visual-basic/language-reference/modifiers/default.md)</span><span class="sxs-lookup"><span data-stu-id="63216-221"> [Default](../../../visual-basic/language-reference/modifiers/default.md)</span></span>

