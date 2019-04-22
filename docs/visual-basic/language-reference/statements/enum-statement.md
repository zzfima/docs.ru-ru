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
ms.openlocfilehash: fa97a374d4570e014222bf44844271b3394453da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830075"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="b2795-102">Оператор Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2795-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="b2795-103">Объявляет перечисление и определяет значения его членов.</span><span class="sxs-lookup"><span data-stu-id="b2795-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2795-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2795-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="b2795-105">Части</span><span class="sxs-lookup"><span data-stu-id="b2795-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="b2795-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b2795-106">Optional.</span></span> <span data-ttu-id="b2795-107">Список атрибутов, применяемых к этому перечислению.</span><span class="sxs-lookup"><span data-stu-id="b2795-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="b2795-108">Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки (»`<`«и»`>`«).</span><span class="sxs-lookup"><span data-stu-id="b2795-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="b2795-109"><xref:System.FlagsAttribute> Атрибут указывает, что значение экземпляра перечисления может содержать несколько членов перечисления, и что каждый элемент представляет собой битовое поле, в значение перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="b2795-110">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b2795-110">Optional.</span></span> <span data-ttu-id="b2795-111">Указывает, какой код может обращаться к этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="b2795-112">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="b2795-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="b2795-113">Public</span><span class="sxs-lookup"><span data-stu-id="b2795-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="b2795-114">Protected</span><span class="sxs-lookup"><span data-stu-id="b2795-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="b2795-115">Friend</span><span class="sxs-lookup"><span data-stu-id="b2795-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="b2795-116">Закрытые</span><span class="sxs-lookup"><span data-stu-id="b2795-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="b2795-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="b2795-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="b2795-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="b2795-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

-   `Shadows`  
  
     <span data-ttu-id="b2795-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b2795-119">Optional.</span></span> <span data-ttu-id="b2795-120">Указывает, что это перечисление повторно объявляет и скрывает одинаково названные элементы программирования или набор перегруженных элементов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="b2795-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="b2795-121">Можно указать [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) только на самом перечислении, а не на любой из его элементов.</span><span class="sxs-lookup"><span data-stu-id="b2795-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="b2795-122">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2795-122">Required.</span></span> <span data-ttu-id="b2795-123">Имя перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-123">Name of the enumeration.</span></span> <span data-ttu-id="b2795-124">Сведения о допустимых именах см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b2795-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="b2795-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b2795-125">Optional.</span></span> <span data-ttu-id="b2795-126">Тип данных перечисления и все его члены.</span><span class="sxs-lookup"><span data-stu-id="b2795-126">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="b2795-127">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2795-127">Required.</span></span> <span data-ttu-id="b2795-128">Список констант элементов, объявляемых в данной инструкции.</span><span class="sxs-lookup"><span data-stu-id="b2795-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="b2795-129">Несколько элементов отображаются на отдельных строках исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b2795-129">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="b2795-130">Каждый `member` имеет следующие синтаксис и составляющие: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="b2795-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="b2795-131">Отделение</span><span class="sxs-lookup"><span data-stu-id="b2795-131">Part</span></span>|<span data-ttu-id="b2795-132">Описание</span><span class="sxs-lookup"><span data-stu-id="b2795-132">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="b2795-133">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2795-133">Required.</span></span> <span data-ttu-id="b2795-134">Имя данного элемента.</span><span class="sxs-lookup"><span data-stu-id="b2795-134">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="b2795-135">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b2795-135">Optional.</span></span> <span data-ttu-id="b2795-136">Выражение, вычисляемое во время компиляции и назначены этому члену.</span><span class="sxs-lookup"><span data-stu-id="b2795-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="b2795-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="b2795-137">`End` `Enum`</span></span>  
  
     <span data-ttu-id="b2795-138">Завершает блок `Enum`.</span><span class="sxs-lookup"><span data-stu-id="b2795-138">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2795-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2795-139">Remarks</span></span>  
 <span data-ttu-id="b2795-140">Если у вас есть набор неизменных значений, логически связанных друг с другом, их можно определить друг с другом в перечислении.</span><span class="sxs-lookup"><span data-stu-id="b2795-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="b2795-141">Это обеспечивает значимые имена для перечисления и его элементы, которые являются легче для запоминания, чем их значения.</span><span class="sxs-lookup"><span data-stu-id="b2795-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="b2795-142">Затем можно использовать члены перечисления во многих местах в коде.</span><span class="sxs-lookup"><span data-stu-id="b2795-142">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="b2795-143">Преимущества использования перечисления включают следующее:</span><span class="sxs-lookup"><span data-stu-id="b2795-143">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="b2795-144">Сокращает число ошибок, вызванных перемещением или неправильным вводом значений.</span><span class="sxs-lookup"><span data-stu-id="b2795-144">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="b2795-145">Позволяет легко изменять значения в будущем.</span><span class="sxs-lookup"><span data-stu-id="b2795-145">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="b2795-146">Делает код более удобным для чтения, это означает, что маловероятно, что появилось новых ошибок.</span><span class="sxs-lookup"><span data-stu-id="b2795-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="b2795-147">Обеспечение прямой совместимости.</span><span class="sxs-lookup"><span data-stu-id="b2795-147">Ensures forward compatibility.</span></span> <span data-ttu-id="b2795-148">Если вы используете перечисления, код является менее вероятны ошибки, если в будущем кто-то изменяет значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="b2795-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="b2795-149">Перечисление имеет имя, базовый тип данных и набор элементов.</span><span class="sxs-lookup"><span data-stu-id="b2795-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="b2795-150">Каждый элемент представляет константу.</span><span class="sxs-lookup"><span data-stu-id="b2795-150">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="b2795-151">Перечисление, объявленные на уровне класса, структуры, модуля или интерфейс, вне любых процедур — *член перечисления*.</span><span class="sxs-lookup"><span data-stu-id="b2795-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="b2795-152">Он является членом класса, структуры, модуля или интерфейса, объявляющего его.</span><span class="sxs-lookup"><span data-stu-id="b2795-152">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="b2795-153">Член перечисления может быть организован в любом месте в пределах их класса, структуры, модуля или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b2795-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="b2795-154">Код вне класса, структуры или модуля необходимо указать имя перечисления элементов с именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="b2795-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="b2795-155">Можно избежать необходимости использовать полные имена, добавив [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) инструкции к исходному файлу.</span><span class="sxs-lookup"><span data-stu-id="b2795-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="b2795-156">Перечисление, объявленное на уровне пространства имен, за пределами класса, структуры, модуля или интерфейса, является членом пространства имен, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="b2795-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="b2795-157">*Контекст объявления* для перечисления должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс, а не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="b2795-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="b2795-158">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b2795-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="b2795-159">Можно применять атрибуты к перечислению в целом, но не к его членам по отдельности.</span><span class="sxs-lookup"><span data-stu-id="b2795-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="b2795-160">Атрибут вносит сведения для метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="b2795-160">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="b2795-161">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b2795-161">Data Type</span></span>  
 <span data-ttu-id="b2795-162">`Enum` Инструкции можно объявить тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="b2795-163">Каждый элемент имеет тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="b2795-164">Можно указать `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, или `UShort`.</span><span class="sxs-lookup"><span data-stu-id="b2795-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="b2795-165">Если вы не укажете `datatype` для перечисления, каждый элемент имеет тип данных его `initializer`.</span><span class="sxs-lookup"><span data-stu-id="b2795-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="b2795-166">Если задан и `datatype` и `initializer`, тип данных `initializer` должно быть преобразуемым в `datatype`.</span><span class="sxs-lookup"><span data-stu-id="b2795-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="b2795-167">Если ни один из `datatype` , ни `initializer` присутствует, по умолчанию тип данных `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b2795-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="b2795-168">Инициализация членов</span><span class="sxs-lookup"><span data-stu-id="b2795-168">Initializing Members</span></span>  
 <span data-ttu-id="b2795-169">`Enum` Оператор может инициализировать содержимое выбранных элементов в `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="b2795-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="b2795-170">Использовании `initializer` позволяет указать выражение для назначения к элементу.</span><span class="sxs-lookup"><span data-stu-id="b2795-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="b2795-171">Если вы не укажете `initializer` для члена, Visual Basic инициализирует его, либо до нуля (если он является первым `member` в `memberlist`), или значение на единицу, чем непосредственно перед `member`.</span><span class="sxs-lookup"><span data-stu-id="b2795-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="b2795-172">Выражения, предоставленного в каждом `initializer` может быть любое сочетание литералов, другие константы, которые уже определены и членов перечисления, которые уже определены, включая предыдущего члена этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="b2795-173">Арифметические и логические операторы можно использовать для объединения этих элементов.</span><span class="sxs-lookup"><span data-stu-id="b2795-173">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="b2795-174">Нельзя использовать переменные или функции в `initializer`.</span><span class="sxs-lookup"><span data-stu-id="b2795-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="b2795-175">Тем не менее, можно использовать ключевое слово преобразования, такие как `CByte` и `CShort`.</span><span class="sxs-lookup"><span data-stu-id="b2795-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="b2795-176">Можно также использовать `AscW` при ее вызове с константой `String` или `Char` аргумент, поскольку, может быть вычислено во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b2795-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="b2795-177">Перечисления не могут иметь значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="b2795-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="b2795-178">Если члену присваивается значение с плавающей запятой и `Option Strict` установлен в значение on, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="b2795-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="b2795-179">Если `Option Strict` выключен, то значение автоматически преобразуется в `Enum` типа.</span><span class="sxs-lookup"><span data-stu-id="b2795-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="b2795-180">Если значение элемента, превышает диапазон допустимых значений для базового типа данных или инициализации любого члена, максимальное значение для базового типа данных, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b2795-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="b2795-181">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="b2795-181">Modifiers</span></span>  
 <span data-ttu-id="b2795-182">Класс, структура, модуль и интерфейс элемента перечисления по умолчанию для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="b2795-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="b2795-183">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="b2795-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="b2795-184">Пространство имен члены перечисления по умолчанию дружественный доступ.</span><span class="sxs-lookup"><span data-stu-id="b2795-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="b2795-185">Вы можете настроить уровни доступа к общедоступным, но не к закрытым или защищенным.</span><span class="sxs-lookup"><span data-stu-id="b2795-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="b2795-186">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b2795-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="b2795-187">Все члены перечисления имеют общий доступ, и их невозможно использовать модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="b2795-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="b2795-188">Тем не менее если перечисление само имеет более ограниченный уровень доступа, указанный уровень доступа перечисления имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="b2795-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="b2795-189">По умолчанию все перечисления являются типами и их полей являются константами.</span><span class="sxs-lookup"><span data-stu-id="b2795-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="b2795-190">Таким образом `Shared`, `Static`, и `ReadOnly` ключевые слова нельзя использовать при объявлении перечисления или его элементов.</span><span class="sxs-lookup"><span data-stu-id="b2795-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="b2795-191">Назначение нескольких значений</span><span class="sxs-lookup"><span data-stu-id="b2795-191">Assigning Multiple Values</span></span>  
 <span data-ttu-id="b2795-192">Перечисления обычно представляют собой взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="b2795-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="b2795-193">Включив <xref:System.FlagsAttribute> атрибут в `Enum` объявление, можно вместо этого назначить несколько значений экземпляра перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="b2795-194"><xref:System.FlagsAttribute> Атрибут указывает, что перечисление рассматриваться как битовое поле, то есть набор флагов.</span><span class="sxs-lookup"><span data-stu-id="b2795-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="b2795-195">Они называются *побитовое* перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-195">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="b2795-196">При объявлении перечисления с помощью <xref:System.FlagsAttribute> атрибут, мы рекомендуем использовать степени числа 2, который является, 1, 2, 4, 8, 16 и т. д., для значений.</span><span class="sxs-lookup"><span data-stu-id="b2795-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="b2795-197">Мы также рекомендуем использовать «None» имя элемента, значение которого равно 0.</span><span class="sxs-lookup"><span data-stu-id="b2795-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="b2795-198">Дополнительные рекомендации см. в разделе <xref:System.FlagsAttribute> и <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="b2795-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2795-199">Пример</span><span class="sxs-lookup"><span data-stu-id="b2795-199">Example</span></span>  
 <span data-ttu-id="b2795-200">В следующем примере показано использование оператора `Enum`.</span><span class="sxs-lookup"><span data-stu-id="b2795-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="b2795-201">Обратите внимание, что элемент называется `EggSizeEnum.Medium`, а не как `Medium`.</span><span class="sxs-lookup"><span data-stu-id="b2795-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 [!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="b2795-202">Пример</span><span class="sxs-lookup"><span data-stu-id="b2795-202">Example</span></span>  
 <span data-ttu-id="b2795-203">В следующем примере метод находится за пределами `Egg` класса.</span><span class="sxs-lookup"><span data-stu-id="b2795-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="b2795-204">Таким образом `EggSizeEnum` полностью принимается в качестве `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="b2795-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 [!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]  
  
## <a name="example"></a><span data-ttu-id="b2795-205">Пример</span><span class="sxs-lookup"><span data-stu-id="b2795-205">Example</span></span>  
 <span data-ttu-id="b2795-206">В следующем примере используется `Enum` инструкции для определения связанного набора именованных констант.</span><span class="sxs-lookup"><span data-stu-id="b2795-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="b2795-207">В этом случае значения являются цветами, которые можно выбрать для создаваемых форм ввода данных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="b2795-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 [!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="b2795-208">Пример</span><span class="sxs-lookup"><span data-stu-id="b2795-208">Example</span></span>  
 <span data-ttu-id="b2795-209">Пример значения, включающих положительные и отрицательные числа.</span><span class="sxs-lookup"><span data-stu-id="b2795-209">The following example shows values that include both positive and negative numbers.</span></span>  
  
 [!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="b2795-210">Пример</span><span class="sxs-lookup"><span data-stu-id="b2795-210">Example</span></span>  
 <span data-ttu-id="b2795-211">В следующем примере `As` предложение используется для указания `datatype` перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="b2795-212">Пример</span><span class="sxs-lookup"><span data-stu-id="b2795-212">Example</span></span>  
 <span data-ttu-id="b2795-213">Приведенный ниже показано, как использовать побитовое перечисление.</span><span class="sxs-lookup"><span data-stu-id="b2795-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="b2795-214">Несколько значений могут назначаться экземпляр побитового перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="b2795-215">`Enum` Объявление включает в себя <xref:System.FlagsAttribute> атрибут, который указывает, что перечисление может обрабатываться как набор флагов.</span><span class="sxs-lookup"><span data-stu-id="b2795-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 [!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="b2795-216">Пример</span><span class="sxs-lookup"><span data-stu-id="b2795-216">Example</span></span>  
 <span data-ttu-id="b2795-217">Приведенный ниже пример проходит через перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2795-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="b2795-218">Она использует <xref:System.Enum.GetNames%2A> метод для получения массива имен членов из перечисления, и <xref:System.Enum.GetValues%2A> для извлечения массива значений элементов.</span><span class="sxs-lookup"><span data-stu-id="b2795-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 [!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]  
  
## <a name="see-also"></a><span data-ttu-id="b2795-219">См. также</span><span class="sxs-lookup"><span data-stu-id="b2795-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="b2795-220">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="b2795-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="b2795-221">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="b2795-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="b2795-222">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="b2795-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="b2795-223">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="b2795-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="b2795-224">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="b2795-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
