---
title: "Оператор Enum (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: "44"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a8244318e0be8e50f3384b56cf63e59182b6cda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="a7691-102">Оператор Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7691-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="a7691-103">Объявляет перечисление и определяет значения его членов.</span><span class="sxs-lookup"><span data-stu-id="a7691-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7691-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7691-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="a7691-105">Части</span><span class="sxs-lookup"><span data-stu-id="a7691-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="a7691-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a7691-106">Optional.</span></span> <span data-ttu-id="a7691-107">Список атрибутов, которые применяются для этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="a7691-108">Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).</span><span class="sxs-lookup"><span data-stu-id="a7691-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="a7691-109"><xref:System.FlagsAttribute> Атрибут указывает, что значение экземпляра перечисления может содержать несколько членов перечисления, и что каждый элемент представляет собой битовое поле, в значение перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="a7691-110">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a7691-110">Optional.</span></span> <span data-ttu-id="a7691-111">Указывает, какой код может получить доступ этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="a7691-112">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="a7691-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="a7691-113">Public</span><span class="sxs-lookup"><span data-stu-id="a7691-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="a7691-114">Protected</span><span class="sxs-lookup"><span data-stu-id="a7691-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="a7691-115">Friend</span><span class="sxs-lookup"><span data-stu-id="a7691-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="a7691-116">Закрытые</span><span class="sxs-lookup"><span data-stu-id="a7691-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="a7691-117">Можно указать `Protected``Friend` для предоставления доступа из кода внутри класса перечисления, производном классе или той же сборки.</span><span class="sxs-lookup"><span data-stu-id="a7691-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="a7691-118">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a7691-118">Optional.</span></span> <span data-ttu-id="a7691-119">Указывает, что это перечисление повторно объявляет и скрывает идентично именованный программный элемент или набор перегруженных элементов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="a7691-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="a7691-120">Можно указать [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) только на самом перечислении, а не на любой из его элементов.</span><span class="sxs-lookup"><span data-stu-id="a7691-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="a7691-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a7691-121">Required.</span></span> <span data-ttu-id="a7691-122">Имя перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-122">Name of the enumeration.</span></span> <span data-ttu-id="a7691-123">Сведения о допустимых именах см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a7691-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="a7691-124">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a7691-124">Optional.</span></span> <span data-ttu-id="a7691-125">Тип данных перечисления и все его члены.</span><span class="sxs-lookup"><span data-stu-id="a7691-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="a7691-126">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a7691-126">Required.</span></span> <span data-ttu-id="a7691-127">Список констант элементов, объявляемых в этом операторе.</span><span class="sxs-lookup"><span data-stu-id="a7691-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="a7691-128">Несколько элементов отображаются на отдельных строках исходного кода.</span><span class="sxs-lookup"><span data-stu-id="a7691-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="a7691-129">Каждый `member` имеет следующий синтаксис и компоненты:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="a7691-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="a7691-130">Отделение</span><span class="sxs-lookup"><span data-stu-id="a7691-130">Part</span></span>|<span data-ttu-id="a7691-131">Описание</span><span class="sxs-lookup"><span data-stu-id="a7691-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="a7691-132">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a7691-132">Required.</span></span> <span data-ttu-id="a7691-133">Имя данного элемента.</span><span class="sxs-lookup"><span data-stu-id="a7691-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="a7691-134">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a7691-134">Optional.</span></span> <span data-ttu-id="a7691-135">Выражение, которое вычисляется во время компиляции и присваивается этому элементу.</span><span class="sxs-lookup"><span data-stu-id="a7691-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="a7691-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="a7691-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="a7691-137">Завершает блок `Enum`.</span><span class="sxs-lookup"><span data-stu-id="a7691-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7691-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7691-138">Remarks</span></span>  
 <span data-ttu-id="a7691-139">Если имеется набор неизменных значений, логически связанных друг с другом, можно определить их вместе в перечислении.</span><span class="sxs-lookup"><span data-stu-id="a7691-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="a7691-140">Это обеспечивает значимые имена для перечисления и его элементов, которые легче запомнить, чем их значения.</span><span class="sxs-lookup"><span data-stu-id="a7691-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="a7691-141">Затем можно использовать члены перечисления во многих местах в коде.</span><span class="sxs-lookup"><span data-stu-id="a7691-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="a7691-142">Ниже приведены преимущества использования перечисления:</span><span class="sxs-lookup"><span data-stu-id="a7691-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="a7691-143">Уменьшает количество ошибок, вызванных перемещением или неправильным вводом значений.</span><span class="sxs-lookup"><span data-stu-id="a7691-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="a7691-144">Позволяет легко изменять значения в будущем.</span><span class="sxs-lookup"><span data-stu-id="a7691-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="a7691-145">Делает код более удобным для чтения, это означает, что это менее вероятно, что ошибки будут вводиться.</span><span class="sxs-lookup"><span data-stu-id="a7691-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="a7691-146">Обеспечение прямой совместимости.</span><span class="sxs-lookup"><span data-stu-id="a7691-146">Ensures forward compatibility.</span></span> <span data-ttu-id="a7691-147">При использовании перечисления код является менее вероятны, если в будущем уведомлений об изменении значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="a7691-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="a7691-148">Перечисление имеет имя, базовый тип данных и набор элементов.</span><span class="sxs-lookup"><span data-stu-id="a7691-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="a7691-149">Каждый элемент представляет константу.</span><span class="sxs-lookup"><span data-stu-id="a7691-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="a7691-150">Перечисление, объявленные на уровне интерфейса, вне любых процедур, модуля, класса или структуры является *член перечисления*.</span><span class="sxs-lookup"><span data-stu-id="a7691-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="a7691-151">Он является членом класса, структуры, модуля или интерфейса, объявляющего его.</span><span class="sxs-lookup"><span data-stu-id="a7691-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="a7691-152">Член перечисления может осуществляться из в любом месте в пределах их класса, структуры, модуля или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a7691-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="a7691-153">Код вне класса, структуры или модуля необходимо предварять именем перечисления элементов с именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="a7691-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="a7691-154">Можно исключить необходимость использования полных имен, добавив [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) инструкции в исходный файл.</span><span class="sxs-lookup"><span data-stu-id="a7691-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="a7691-155">Перечисление, объявленное на уровне пространства имен, вне класса, структуры, модуля или интерфейса, является членом пространства имен, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="a7691-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="a7691-156">*Контекст объявления* для перечисления должен быть исходным файлом, пространства имен, класса, структуры, модуля или интерфейса и не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="a7691-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="a7691-157">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7691-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="a7691-158">Можно применить атрибуты к перечислению в целом, но не к его членам по отдельности.</span><span class="sxs-lookup"><span data-stu-id="a7691-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="a7691-159">Атрибут вносит сведения для метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="a7691-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="a7691-160">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a7691-160">Data Type</span></span>  
 <span data-ttu-id="a7691-161">`Enum` Инструкция может объявить тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="a7691-162">Каждый элемент принимает тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="a7691-163">Можно указать `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, или `UShort`.</span><span class="sxs-lookup"><span data-stu-id="a7691-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="a7691-164">Если вы не укажете `datatype` для перечисления, каждый элемент имеет тип данных его `initializer`.</span><span class="sxs-lookup"><span data-stu-id="a7691-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="a7691-165">Если заданы оба `datatype` и `initializer`, тип данных `initializer` должно быть преобразуемым `datatype`.</span><span class="sxs-lookup"><span data-stu-id="a7691-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="a7691-166">Если ни одна из `datatype` , ни `initializer` присутствует, по умолчанию используется тип данных `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a7691-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="a7691-167">Инициализации членов</span><span class="sxs-lookup"><span data-stu-id="a7691-167">Initializing Members</span></span>  
 <span data-ttu-id="a7691-168">`Enum` Оператор может инициализировать содержимое выбранных элементов в `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="a7691-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="a7691-169">Вы используете `initializer` позволяет указать выражение для назначения члена.</span><span class="sxs-lookup"><span data-stu-id="a7691-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="a7691-170">Если вы не укажете `initializer` для члена, Visual Basic инициализирует ее с нуля (если он является первым `member` в `memberlist`), или значение, на единицу, непосредственно предшествующий чем `member`.</span><span class="sxs-lookup"><span data-stu-id="a7691-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="a7691-171">Выражения, предоставленного в каждом `initializer` может быть любое сочетание литералов, другие константы, которые уже определены и членов перечисления, которые уже определены, включая предыдущего члена этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="a7691-172">Можно использовать арифметические и логические операторы для объединения этих элементов.</span><span class="sxs-lookup"><span data-stu-id="a7691-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="a7691-173">Нельзя использовать переменные или функции в `initializer`.</span><span class="sxs-lookup"><span data-stu-id="a7691-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="a7691-174">Тем не менее, можно использовать ключевые слова преобразования, такие как `CByte` и `CShort`.</span><span class="sxs-lookup"><span data-stu-id="a7691-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="a7691-175">Можно также использовать `AscW` при ее вызове с константой `String` или `Char` аргумент, поскольку, может быть вычислено во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="a7691-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="a7691-176">Перечисления не могут иметь значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="a7691-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="a7691-177">Если члену присваивается значение с плавающей запятой и `Option Strict` имеет значение on, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="a7691-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="a7691-178">Если `Option Strict` выключен, то значение автоматически преобразуется в `Enum` типа.</span><span class="sxs-lookup"><span data-stu-id="a7691-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="a7691-179">Если значение элемента превышает допустимого диапазона для базового типа данных или инициализации любого члена к допустимому значению базового типа данных, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a7691-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="a7691-180">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="a7691-180">Modifiers</span></span>  
 <span data-ttu-id="a7691-181">Класс, структура, модуль и интерфейс элемента перечисления по умолчанию для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="a7691-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="a7691-182">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="a7691-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="a7691-183">Пространство имен члены перечисления по умолчанию дружественный доступ.</span><span class="sxs-lookup"><span data-stu-id="a7691-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="a7691-184">Вы можете настроить уровни доступа к открытым, но не к личным или защищенным.</span><span class="sxs-lookup"><span data-stu-id="a7691-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="a7691-185">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7691-185">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="a7691-186">Все члены перечисления имеют общий доступ, и на них нельзя использовать модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="a7691-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="a7691-187">Однако если перечисление само имеет более ограниченный уровень доступа, указанный уровень доступа перечисления имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="a7691-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="a7691-188">По умолчанию все перечисления являются типами и их поля являются константами.</span><span class="sxs-lookup"><span data-stu-id="a7691-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="a7691-189">Поэтому `Shared`, `Static`, и `ReadOnly` ключевые слова нельзя использовать при объявлении перечисления или его члены.</span><span class="sxs-lookup"><span data-stu-id="a7691-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="a7691-190">Назначение нескольких значений</span><span class="sxs-lookup"><span data-stu-id="a7691-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="a7691-191">Перечисления обычно представляют собой взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="a7691-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="a7691-192">Включив <xref:System.FlagsAttribute> атрибута в `Enum` объявление, можно вместо этого назначить несколько значений перечисления экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a7691-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="a7691-193"><xref:System.FlagsAttribute> Атрибут указывает, что перечисление обрабатываться как битовое поле, то есть набор флагов.</span><span class="sxs-lookup"><span data-stu-id="a7691-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="a7691-194">Это называется *побитовое* перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="a7691-195">При объявлении перечисления с помощью <xref:System.FlagsAttribute> атрибут, рекомендуется использовать степени числа 2, который является, 1, 2, 4, 8, 16 и т. д., для значений.</span><span class="sxs-lookup"><span data-stu-id="a7691-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="a7691-196">Кроме того, мы рекомендуем «None» использовать имя элемента, значение которого равно 0.</span><span class="sxs-lookup"><span data-stu-id="a7691-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="a7691-197">Дополнительные рекомендации см. в разделе <xref:System.FlagsAttribute> и <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="a7691-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7691-198">Пример</span><span class="sxs-lookup"><span data-stu-id="a7691-198">Example</span></span>  
 <span data-ttu-id="a7691-199">В следующем примере показано, как использовать `Enum` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a7691-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="a7691-200">Обратите внимание, что элемент называется `EggSizeEnum.Medium`, а не как `Medium`.</span><span class="sxs-lookup"><span data-stu-id="a7691-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7691-201">Пример</span><span class="sxs-lookup"><span data-stu-id="a7691-201">Example</span></span>  
 <span data-ttu-id="a7691-202">В следующем примере метод находится за пределами `Egg` класса.</span><span class="sxs-lookup"><span data-stu-id="a7691-202">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="a7691-203">Таким образом `EggSizeEnum` полностью определено как `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="a7691-203">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7691-204">Пример</span><span class="sxs-lookup"><span data-stu-id="a7691-204">Example</span></span>  
 <span data-ttu-id="a7691-205">В следующем примере используется `Enum` инструкцию, чтобы определить набор связанных именованных констант.</span><span class="sxs-lookup"><span data-stu-id="a7691-205">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="a7691-206">В этом случае значения являются цветов, которые можно выбрать для создаваемых форм ввода данных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="a7691-206">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7691-207">Пример</span><span class="sxs-lookup"><span data-stu-id="a7691-207">Example</span></span>  
 <span data-ttu-id="a7691-208">В следующем примере показано значений, которые включают положительные и отрицательные числа.</span><span class="sxs-lookup"><span data-stu-id="a7691-208">The following example shows values that include both positive and negative numbers.</span></span>  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7691-209">Пример</span><span class="sxs-lookup"><span data-stu-id="a7691-209">Example</span></span>  
 <span data-ttu-id="a7691-210">В следующем примере `As` предложение используется для указания `datatype` перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-210">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7691-211">Пример</span><span class="sxs-lookup"><span data-stu-id="a7691-211">Example</span></span>  
 <span data-ttu-id="a7691-212">В следующем примере показано использование побитового перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-212">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="a7691-213">Несколько значений могут назначаться в экземпляр побитового перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-213">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="a7691-214">`Enum` Объявление включает <xref:System.FlagsAttribute> атрибут, который указывает, что перечисление может обрабатываться как набор флагов.</span><span class="sxs-lookup"><span data-stu-id="a7691-214">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7691-215">Пример</span><span class="sxs-lookup"><span data-stu-id="a7691-215">Example</span></span>  
 <span data-ttu-id="a7691-216">Следующий пример перебор элементов перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7691-216">The following example iterates through an enumeration.</span></span> <span data-ttu-id="a7691-217">Она использует <xref:System.Enum.GetNames%2A> метод для извлечения массива имен членов из перечисления, и <xref:System.Enum.GetValues%2A> для извлечения массива значений элементов.</span><span class="sxs-lookup"><span data-stu-id="a7691-217">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a7691-218">См. также</span><span class="sxs-lookup"><span data-stu-id="a7691-218">See Also</span></span>  
 <xref:System.Enum>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [<span data-ttu-id="a7691-219">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="a7691-219">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="a7691-220">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="a7691-220">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="a7691-221">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="a7691-221">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="a7691-222">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="a7691-222">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a7691-223">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="a7691-223">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
