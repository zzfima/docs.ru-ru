---
title: Оператор Enum (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: be1780b00b4d58964e1de5ec199cb80dc0f9dba5
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583408"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="772ed-102">Оператор Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="772ed-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="772ed-103">Объявляет перечисление и определяет значения его элементов.</span><span class="sxs-lookup"><span data-stu-id="772ed-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="772ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="772ed-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="772ed-105">Части</span><span class="sxs-lookup"><span data-stu-id="772ed-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="772ed-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-106">Optional.</span></span> <span data-ttu-id="772ed-107">Список атрибутов, которые применяются к этому перечислению.</span><span class="sxs-lookup"><span data-stu-id="772ed-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="772ed-108">[Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) необходимо заключить в угловые скобки ("`<`" и "`>`").</span><span class="sxs-lookup"><span data-stu-id="772ed-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="772ed-109">Атрибут <xref:System.FlagsAttribute> указывает, что значение экземпляра перечисления может включать несколько членов перечисления и что каждый элемент представляет битовое поле в значении перечисления.</span><span class="sxs-lookup"><span data-stu-id="772ed-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="772ed-110">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-110">Optional.</span></span> <span data-ttu-id="772ed-111">Указывает, какой код может получить доступ к этому перечислению.</span><span class="sxs-lookup"><span data-stu-id="772ed-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="772ed-112">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="772ed-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="772ed-113">Public</span><span class="sxs-lookup"><span data-stu-id="772ed-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="772ed-114">Protected</span><span class="sxs-lookup"><span data-stu-id="772ed-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="772ed-115">Friend</span><span class="sxs-lookup"><span data-stu-id="772ed-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="772ed-116">Закрытые</span><span class="sxs-lookup"><span data-stu-id="772ed-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="772ed-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="772ed-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="772ed-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="772ed-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="772ed-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-119">Optional.</span></span> <span data-ttu-id="772ed-120">Указывает, что это перечисление повторно объявляет и скрывает идентично именованный элемент программирования или набор перегруженных элементов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="772ed-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="772ed-121">[Тени](../../../visual-basic/language-reference/modifiers/shadows.md) можно указывать только в самом перечислении, а не на любом из его членов.</span><span class="sxs-lookup"><span data-stu-id="772ed-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="772ed-122">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-122">Required.</span></span> <span data-ttu-id="772ed-123">Имя перечисления.</span><span class="sxs-lookup"><span data-stu-id="772ed-123">Name of the enumeration.</span></span> <span data-ttu-id="772ed-124">Сведения о допустимых именах см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="772ed-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="772ed-125">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-125">Optional.</span></span> <span data-ttu-id="772ed-126">Тип данных перечисления и всех его элементов.</span><span class="sxs-lookup"><span data-stu-id="772ed-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="772ed-127">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-127">Required.</span></span> <span data-ttu-id="772ed-128">Список констант членов, объявляемых в этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="772ed-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="772ed-129">В отдельных строках исходного кода отображаются несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="772ed-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="772ed-130">Каждый `member` имеет следующий синтаксис и фрагменты: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="772ed-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="772ed-131">Отделение</span><span class="sxs-lookup"><span data-stu-id="772ed-131">Part</span></span>|<span data-ttu-id="772ed-132">Описание</span><span class="sxs-lookup"><span data-stu-id="772ed-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="772ed-133">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-133">Required.</span></span> <span data-ttu-id="772ed-134">Имя этого элемента.</span><span class="sxs-lookup"><span data-stu-id="772ed-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="772ed-135">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="772ed-135">Optional.</span></span> <span data-ttu-id="772ed-136">Выражение, которое вычисляется во время компиляции и присваивается этому элементу.</span><span class="sxs-lookup"><span data-stu-id="772ed-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="772ed-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="772ed-137">`End` `Enum`</span></span>

  <span data-ttu-id="772ed-138">Завершает блок `Enum`.</span><span class="sxs-lookup"><span data-stu-id="772ed-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="772ed-139">Заметки</span><span class="sxs-lookup"><span data-stu-id="772ed-139">Remarks</span></span>

<span data-ttu-id="772ed-140">Если имеется набор неизменяемых значений, логически связанных друг с другом, их можно определить вместе в перечислении.</span><span class="sxs-lookup"><span data-stu-id="772ed-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="772ed-141">Это дает осмысленные имена для перечисления и его членов, которые проще запомнить, чем их значения.</span><span class="sxs-lookup"><span data-stu-id="772ed-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="772ed-142">Затем можно использовать элементы перечисления во многих местах кода.</span><span class="sxs-lookup"><span data-stu-id="772ed-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="772ed-143">Ниже перечислены преимущества использования перечислений.</span><span class="sxs-lookup"><span data-stu-id="772ed-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="772ed-144">Сокращает количество ошибок, вызванных перечислением или неотрицательным вводом чисел.</span><span class="sxs-lookup"><span data-stu-id="772ed-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="772ed-145">Упрощает изменение значений в будущем.</span><span class="sxs-lookup"><span data-stu-id="772ed-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="772ed-146">Упрощает чтение кода, что означает меньшее количество ошибок, которые могут возникать.</span><span class="sxs-lookup"><span data-stu-id="772ed-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="772ed-147">Обеспечивает прямую совместимость.</span><span class="sxs-lookup"><span data-stu-id="772ed-147">Ensures forward compatibility.</span></span> <span data-ttu-id="772ed-148">При использовании перечислений код менее вероятен, если в будущем кто-то изменит значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="772ed-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="772ed-149">Перечисление имеет имя, базовый тип данных и набор элементов.</span><span class="sxs-lookup"><span data-stu-id="772ed-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="772ed-150">Каждый элемент представляет константу.</span><span class="sxs-lookup"><span data-stu-id="772ed-150">Each member represents a constant.</span></span>

<span data-ttu-id="772ed-151">Перечисление, объявленное на уровне класса, структуры, модуля или интерфейса, за пределами любой процедуры, является *перечислителем элементов*.</span><span class="sxs-lookup"><span data-stu-id="772ed-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="772ed-152">Он является членом класса, структуры, модуля или интерфейса, объявляющего его.</span><span class="sxs-lookup"><span data-stu-id="772ed-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="772ed-153">К перечислениям членов можно обращаться из любого места в своем классе, структуре, модуле или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="772ed-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="772ed-154">Код за пределами класса, структуры или модуля должен уточнять имя перечисления членов именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="772ed-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="772ed-155">Можно избежать необходимости использовать полные имена, добавив оператор [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) в исходный файл.</span><span class="sxs-lookup"><span data-stu-id="772ed-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="772ed-156">Перечисление, объявленное на уровне пространства имен вне любого класса, структуры, модуля или интерфейса, является членом пространства имен, в котором оно отображается.</span><span class="sxs-lookup"><span data-stu-id="772ed-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="772ed-157">*Контекст объявления* для перечисления должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом и не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="772ed-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="772ed-158">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="772ed-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="772ed-159">К перечислению можно применять атрибуты в целом, но не в отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="772ed-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="772ed-160">Атрибут вносит сведения в метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="772ed-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="772ed-161">Тип данных</span><span class="sxs-lookup"><span data-stu-id="772ed-161">Data Type</span></span>

<span data-ttu-id="772ed-162">Оператор `Enum` может объявлять тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="772ed-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="772ed-163">Каждый член принимает тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="772ed-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="772ed-164">Можно указать `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong` или `UShort`.</span><span class="sxs-lookup"><span data-stu-id="772ed-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="772ed-165">Если не указать `datatype` для перечисления, каждый элемент принимает тип данных его `initializer`.</span><span class="sxs-lookup"><span data-stu-id="772ed-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="772ed-166">Если заданы и `datatype`, и `initializer`, тип данных `initializer` должен быть преобразован в `datatype`.</span><span class="sxs-lookup"><span data-stu-id="772ed-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="772ed-167">Если ни `datatype`, ни `initializer` не указаны, по умолчанию используется тип данных `Integer`.</span><span class="sxs-lookup"><span data-stu-id="772ed-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="772ed-168">Инициализация членов</span><span class="sxs-lookup"><span data-stu-id="772ed-168">Initializing Members</span></span>

<span data-ttu-id="772ed-169">Оператор `Enum` может инициализировать содержимое выбранных элементов в `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="772ed-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="772ed-170">Для указания выражения, присваиваемого элементу, используется `initializer`.</span><span class="sxs-lookup"><span data-stu-id="772ed-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="772ed-171">Если не указать `initializer` для члена, Visual Basic инициализирует его как ноль (если он является первым `member` в `memberlist`) или значение, большее значения, равное значению, отличному от предыдущего `member`.</span><span class="sxs-lookup"><span data-stu-id="772ed-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="772ed-172">Выражение, передаваемое в каждой `initializer`, может быть любым сочетанием литералов, других уже определенных констант и уже определенных членов перечисления, включая предыдущий элемент этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="772ed-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="772ed-173">Для объединения таких элементов можно использовать арифметические и логические операторы.</span><span class="sxs-lookup"><span data-stu-id="772ed-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="772ed-174">В `initializer` нельзя использовать переменные или функции.</span><span class="sxs-lookup"><span data-stu-id="772ed-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="772ed-175">Однако можно использовать ключевые слова преобразования, такие как `CByte` и `CShort`.</span><span class="sxs-lookup"><span data-stu-id="772ed-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="772ed-176">Можно также использовать `AscW`, если он вызывается с константой `String` или аргументом `Char`, так как это может быть вычислено во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="772ed-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="772ed-177">Перечисления не могут иметь значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="772ed-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="772ed-178">Если члену присваивается значение с плавающей запятой, а `Option Strict` устанавливается в on, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="772ed-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="772ed-179">Если `Option Strict` находится в состоянии OFF, значение автоматически преобразуется в тип `Enum`.</span><span class="sxs-lookup"><span data-stu-id="772ed-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="772ed-180">Если значение элемента превышает допустимый диапазон для базового типа данных или если любой элемент инициализируется максимальным значением, разрешенным базовым типом данных, то компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="772ed-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="772ed-181">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="772ed-181">Modifiers</span></span>

<span data-ttu-id="772ed-182">Перечисления членов класса, структуры, модуля и интерфейса по умолчанию имеют открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="772ed-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="772ed-183">Уровни доступа можно изменить с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="772ed-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="772ed-184">Перечисления членов пространств имен по умолчанию имеют дружественный доступ.</span><span class="sxs-lookup"><span data-stu-id="772ed-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="772ed-185">Уровни доступа можно изменить на "общий", но не на "частный" или "защищенный".</span><span class="sxs-lookup"><span data-stu-id="772ed-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="772ed-186">Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="772ed-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="772ed-187">Все члены перечисления имеют общий доступ, и в них нельзя использовать никакие модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="772ed-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="772ed-188">Однако если перечисление имеет более ограниченный уровень доступа, приоритет имеет указанный уровень доступа к перечислению.</span><span class="sxs-lookup"><span data-stu-id="772ed-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="772ed-189">По умолчанию все перечисления являются типами, а их поля — константами.</span><span class="sxs-lookup"><span data-stu-id="772ed-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="772ed-190">Поэтому ключевые слова `Shared`, `Static` и `ReadOnly` нельзя использовать при объявлении перечисления или его членов.</span><span class="sxs-lookup"><span data-stu-id="772ed-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="772ed-191">Присваивание нескольких значений</span><span class="sxs-lookup"><span data-stu-id="772ed-191">Assigning Multiple Values</span></span>

<span data-ttu-id="772ed-192">Перечисления обычно представляют взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="772ed-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="772ed-193">Включив атрибут <xref:System.FlagsAttribute> в объявление `Enum`, можно присвоить экземпляру перечисления несколько значений.</span><span class="sxs-lookup"><span data-stu-id="772ed-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="772ed-194">Атрибут <xref:System.FlagsAttribute> указывает, что перечисление будет рассматриваться как битовое поле, то есть набор флагов.</span><span class="sxs-lookup"><span data-stu-id="772ed-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="772ed-195">Они называются *побитовыми* перечислениями.</span><span class="sxs-lookup"><span data-stu-id="772ed-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="772ed-196">При объявлении перечисления с помощью атрибута <xref:System.FlagsAttribute> для значений рекомендуется использовать степени 2, то есть 1, 2, 4, 8, 16 и т. д.</span><span class="sxs-lookup"><span data-stu-id="772ed-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="772ed-197">Также рекомендуется, чтобы "None" было именем члена, значение которого равно 0.</span><span class="sxs-lookup"><span data-stu-id="772ed-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="772ed-198">Дополнительные рекомендации см. в разделе <xref:System.FlagsAttribute> и <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="772ed-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="772ed-199">Пример</span><span class="sxs-lookup"><span data-stu-id="772ed-199">Example</span></span>

<span data-ttu-id="772ed-200">В следующем примере показано использование оператора `Enum`.</span><span class="sxs-lookup"><span data-stu-id="772ed-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="772ed-201">Обратите внимание, что элемент называется `EggSizeEnum.Medium`, а не `Medium`.</span><span class="sxs-lookup"><span data-stu-id="772ed-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="772ed-202">Пример</span><span class="sxs-lookup"><span data-stu-id="772ed-202">Example</span></span>

<span data-ttu-id="772ed-203">Метод в следующем примере находится за пределами `Egg` класса.</span><span class="sxs-lookup"><span data-stu-id="772ed-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="772ed-204">Таким образом, `EggSizeEnum` полностью уточняется как `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="772ed-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="772ed-205">Пример</span><span class="sxs-lookup"><span data-stu-id="772ed-205">Example</span></span>

<span data-ttu-id="772ed-206">В следующем примере оператор `Enum` используется для определения связанного набора именованных постоянных значений.</span><span class="sxs-lookup"><span data-stu-id="772ed-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="772ed-207">В этом случае значения представляют собой цвета, которые можно выбрать для создания форм ввода данных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="772ed-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="772ed-208">Пример</span><span class="sxs-lookup"><span data-stu-id="772ed-208">Example</span></span>

<span data-ttu-id="772ed-209">В следующем примере показаны значения, включающие положительные и отрицательные числа.</span><span class="sxs-lookup"><span data-stu-id="772ed-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="772ed-210">Пример</span><span class="sxs-lookup"><span data-stu-id="772ed-210">Example</span></span>

<span data-ttu-id="772ed-211">В следующем примере для указания `datatype` перечисления используется предложение `As`.</span><span class="sxs-lookup"><span data-stu-id="772ed-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="772ed-212">Пример</span><span class="sxs-lookup"><span data-stu-id="772ed-212">Example</span></span>

<span data-ttu-id="772ed-213">В следующем примере показано, как использовать побитовое перечисление.</span><span class="sxs-lookup"><span data-stu-id="772ed-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="772ed-214">Экземпляру побитового перечисления можно назначить несколько значений.</span><span class="sxs-lookup"><span data-stu-id="772ed-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="772ed-215">Объявление `Enum` включает атрибут <xref:System.FlagsAttribute>, указывающий, что перечисление может рассматриваться как набор флагов.</span><span class="sxs-lookup"><span data-stu-id="772ed-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="772ed-216">Пример</span><span class="sxs-lookup"><span data-stu-id="772ed-216">Example</span></span>

<span data-ttu-id="772ed-217">В следующем примере выполняется итерация по перечислению.</span><span class="sxs-lookup"><span data-stu-id="772ed-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="772ed-218">Он использует метод <xref:System.Enum.GetNames%2A> для получения массива имен членов из перечисления и <xref:System.Enum.GetValues%2A> для получения массива значений элементов.</span><span class="sxs-lookup"><span data-stu-id="772ed-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="772ed-219">См. также</span><span class="sxs-lookup"><span data-stu-id="772ed-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="772ed-220">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="772ed-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="772ed-221">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="772ed-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="772ed-222">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="772ed-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="772ed-223">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="772ed-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="772ed-224">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="772ed-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
