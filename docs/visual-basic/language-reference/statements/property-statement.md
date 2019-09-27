---
title: Оператор Property (Visual Basic)
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
ms.openlocfilehash: 2c3e417aad404171a43342dc92773615ec350ef5
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332750"
---
# <a name="property-statement"></a><span data-ttu-id="92fa4-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="92fa4-102">Property Statement</span></span>

<span data-ttu-id="92fa4-103">Объявляет имя свойства и процедуры свойства, используемые для хранения и извлечения значения свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="92fa4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92fa4-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="92fa4-105">Части</span><span class="sxs-lookup"><span data-stu-id="92fa4-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="92fa4-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-106">Optional.</span></span> <span data-ttu-id="92fa4-107">Список атрибутов, применяемых к этому свойству, или `Get` или `Set` процедура.</span><span class="sxs-lookup"><span data-stu-id="92fa4-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="92fa4-108">См. [список атрибутов](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="92fa4-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-109">Optional.</span></span> <span data-ttu-id="92fa4-110">Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="92fa4-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="92fa4-111">Свойства по умолчанию должны принимать параметры и могут быть заданы и получены без указания имени свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="92fa4-112">Если вы объявили свойство как `Default`, нельзя использовать `Private` в свойстве или в любой из его процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="92fa4-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="92fa4-113">Необязательно для оператора `Property` и не более чем в одном из операторов `Get` и `Set`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="92fa4-114">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="92fa4-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="92fa4-115">Public</span><span class="sxs-lookup"><span data-stu-id="92fa4-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="92fa4-116">Protected</span><span class="sxs-lookup"><span data-stu-id="92fa4-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="92fa4-117">Friend</span><span class="sxs-lookup"><span data-stu-id="92fa4-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="92fa4-118">Закрытые</span><span class="sxs-lookup"><span data-stu-id="92fa4-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="92fa4-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="92fa4-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="92fa4-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="92fa4-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="92fa4-121">См. раздел [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="92fa4-122">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-122">Optional.</span></span> <span data-ttu-id="92fa4-123">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="92fa4-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="92fa4-124">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="92fa4-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="92fa4-125">Переопределения</span><span class="sxs-lookup"><span data-stu-id="92fa4-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="92fa4-126">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="92fa4-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="92fa4-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="92fa4-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="92fa4-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="92fa4-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="92fa4-129">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-129">Optional.</span></span> <span data-ttu-id="92fa4-130">См. раздел [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="92fa4-131">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-131">Optional.</span></span> <span data-ttu-id="92fa4-132">См. раздел [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="92fa4-133">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-133">Optional.</span></span> <span data-ttu-id="92fa4-134">См. раздел [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="92fa4-135">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-135">Optional.</span></span> <span data-ttu-id="92fa4-136">См. раздел [WriteOnly](../modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="92fa4-137">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-137">Optional.</span></span> <span data-ttu-id="92fa4-138">См. [итератор](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="92fa4-139">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="92fa4-139">Required.</span></span> <span data-ttu-id="92fa4-140">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-140">Name of the property.</span></span> <span data-ttu-id="92fa4-141">См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="92fa4-142">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-142">Optional.</span></span> <span data-ttu-id="92fa4-143">Список имен локальных переменных, представляющих параметры этого свойства, и возможные дополнительные параметры процедуры `Set`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="92fa4-144">См. [список параметров](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="92fa4-145">Требуется, если `Option Strict` имеет значение `On`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="92fa4-146">Тип данных значения, возвращаемого этим свойством.</span><span class="sxs-lookup"><span data-stu-id="92fa4-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="92fa4-147">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-147">Optional.</span></span> <span data-ttu-id="92fa4-148">Указывает, что это свойство реализует одно или несколько свойств, каждое из которых определено в интерфейсе, реализуемом классом или структурой этого свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="92fa4-149">См. [инструкцию Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="92fa4-150">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="92fa4-151">Список реализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="92fa4-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="92fa4-152">Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="92fa4-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="92fa4-153">Отделение</span><span class="sxs-lookup"><span data-stu-id="92fa4-153">Part</span></span>|<span data-ttu-id="92fa4-154">Описание</span><span class="sxs-lookup"><span data-stu-id="92fa4-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="92fa4-155">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="92fa4-155">Required.</span></span> <span data-ttu-id="92fa4-156">Имя интерфейса, реализованного в классе или структуре этого свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="92fa4-157">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="92fa4-157">Required.</span></span> <span data-ttu-id="92fa4-158">Имя, по которому определяется свойство в `interface`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="92fa4-159">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-159">Optional.</span></span> <span data-ttu-id="92fa4-160">Требуется, если свойство помечено как `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="92fa4-161">Запускает процедуру свойства `Get`, которая используется для возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="92fa4-162">Инструкция `Get` не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="92fa4-163">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-163">Optional.</span></span> <span data-ttu-id="92fa4-164">Блок инструкций для выполнения в процедуре `Get` или `Set`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="92fa4-165">Завершает процедуру свойства `Get`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="92fa4-166">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="92fa4-166">Optional.</span></span> <span data-ttu-id="92fa4-167">Требуется, если свойство помечено как `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="92fa4-168">Запускает процедуру свойства `Set`, используемую для хранения значения свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="92fa4-169">Инструкция `Set` не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="92fa4-170">Завершает процедуру свойства `Set`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="92fa4-171">Завершает определение этого свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="92fa4-172">Примечания</span><span class="sxs-lookup"><span data-stu-id="92fa4-172">Remarks</span></span>

<span data-ttu-id="92fa4-173">Оператор `Property` вводит объявление свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="92fa4-174">Свойство может иметь процедуру `Get` (только для чтения), процедуру `Set` (только для записи) или и то, и другое (чтение и запись).</span><span class="sxs-lookup"><span data-stu-id="92fa4-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="92fa4-175">При использовании автоматического реализуемого свойства можно опустить процедуру `Get` и `Set`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="92fa4-176">Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="92fa4-177">@No__t-0 можно использовать только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="92fa4-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="92fa4-178">Это означает, что *контекст объявления* для свойства должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком.</span><span class="sxs-lookup"><span data-stu-id="92fa4-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="92fa4-179">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="92fa4-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="92fa4-180">По умолчанию свойства используют общий доступ.</span><span class="sxs-lookup"><span data-stu-id="92fa4-180">By default, properties use public access.</span></span> <span data-ttu-id="92fa4-181">Уровень доступа свойства можно настроить с помощью модификатора доступа в операторе `Property`. при необходимости можно изменить одну из процедур свойств на более ограниченный уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="92fa4-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="92fa4-182">Visual Basic передает параметр в процедуру `Set` во время назначения свойств.</span><span class="sxs-lookup"><span data-stu-id="92fa4-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="92fa4-183">Если параметр для `Set` не указан, в интегрированной среде разработки (IDE) используется неявный параметр с именем `value`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="92fa4-184">Этот параметр содержит значение, присваиваемое свойству.</span><span class="sxs-lookup"><span data-stu-id="92fa4-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="92fa4-185">Обычно это значение сохраняется в закрытой локальной переменной и возвращается при каждом вызове процедуры `Get`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="92fa4-186">Правила</span><span class="sxs-lookup"><span data-stu-id="92fa4-186">Rules</span></span>

- <span data-ttu-id="92fa4-187">**Уровни смешанного доступа.**</span><span class="sxs-lookup"><span data-stu-id="92fa4-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="92fa4-188">При определении свойства для чтения и записи можно дополнительно указать другой уровень доступа для `Get` или `Set`, но не для обоих.</span><span class="sxs-lookup"><span data-stu-id="92fa4-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="92fa4-189">В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="92fa4-190">Например, если свойство объявлено `Friend`, можно объявить процедуру `Set` `Private`, но не `Public`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="92fa4-191">Если вы определяете свойство `ReadOnly` или `WriteOnly`, то процедура с одним свойством (`Get` или `Set` соответственно) представляет все свойство.</span><span class="sxs-lookup"><span data-stu-id="92fa4-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="92fa4-192">Для такой процедуры нельзя объявить другой уровень доступа, поскольку в этом случае для свойства будет задано два уровня доступа.</span><span class="sxs-lookup"><span data-stu-id="92fa4-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="92fa4-193">**Тип возвращаемого значения.**</span><span class="sxs-lookup"><span data-stu-id="92fa4-193">**Return Type.**</span></span> <span data-ttu-id="92fa4-194">Оператор `Property` может объявлять тип данных возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="92fa4-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="92fa4-195">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="92fa4-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="92fa4-196">Если не указать `returntype`, свойство возвращает значение `Object`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="92fa4-197">**Реализации.**</span><span class="sxs-lookup"><span data-stu-id="92fa4-197">**Implementation.**</span></span> <span data-ttu-id="92fa4-198">Если в этом свойстве используется ключевое слово `Implements`, содержащий класс или структуру должны содержать оператор `Implements` сразу после оператора `Class` или `Structure`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="92fa4-199">Оператор `Implements` должен содержать каждый интерфейс, указанный в `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="92fa4-200">Однако имя, по которому интерфейс определяет `Property` (в `definedname`), не обязательно должно совпадать с именем этого свойства (в `name`).</span><span class="sxs-lookup"><span data-stu-id="92fa4-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="92fa4-201">Поведение</span><span class="sxs-lookup"><span data-stu-id="92fa4-201">Behavior</span></span>

- <span data-ttu-id="92fa4-202">**Возврат из процедуры свойства.**</span><span class="sxs-lookup"><span data-stu-id="92fa4-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="92fa4-203">Когда процедура `Get` или `Set` возвращает в вызывающий код, выполнение продолжится с оператора, следующего за оператором, вызвавшим ее.</span><span class="sxs-lookup"><span data-stu-id="92fa4-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="92fa4-204">Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="92fa4-205">Любое число инструкций `Exit Property` и `Return` может использоваться в любом месте процедуры, и можно сочетать операторы `Exit Property` и `Return`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="92fa4-206">**Возвращаемое значение.**</span><span class="sxs-lookup"><span data-stu-id="92fa4-206">**Return Value.**</span></span> <span data-ttu-id="92fa4-207">Чтобы вернуть значение из процедуры `Get`, можно либо присвоить значение имени свойства, либо включить его в инструкцию `Return`.</span><span class="sxs-lookup"><span data-stu-id="92fa4-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="92fa4-208">В следующем примере возвращаемое значение присваивается имени свойства `quoteForTheDay`, а затем используется инструкция `Exit Property` для возврата.</span><span class="sxs-lookup"><span data-stu-id="92fa4-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="92fa4-209">Если вы используете `Exit Property` без присвоения значения `name`, процедура `Get` Возвращает значение по умолчанию для типа данных свойства.</span><span class="sxs-lookup"><span data-stu-id="92fa4-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="92fa4-210">В то же время инструкция `Return` назначает возвращаемое значение процедуры `Get` и завершает процедуру.</span><span class="sxs-lookup"><span data-stu-id="92fa4-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="92fa4-211">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="92fa4-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="92fa4-212">Пример</span><span class="sxs-lookup"><span data-stu-id="92fa4-212">Example</span></span>

<span data-ttu-id="92fa4-213">В следующем примере объявляется свойство в классе.</span><span class="sxs-lookup"><span data-stu-id="92fa4-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="92fa4-214">См. также</span><span class="sxs-lookup"><span data-stu-id="92fa4-214">See also</span></span>

- [<span data-ttu-id="92fa4-215">Автоматически реализуемые свойства</span><span class="sxs-lookup"><span data-stu-id="92fa4-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="92fa4-216">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="92fa4-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="92fa4-217">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="92fa4-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="92fa4-218">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="92fa4-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="92fa4-219">Список параметров</span><span class="sxs-lookup"><span data-stu-id="92fa4-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="92fa4-220">Default</span><span class="sxs-lookup"><span data-stu-id="92fa4-220">Default</span></span>](../modifiers/default.md)
