---
title: "Оператор Enum (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Enum
dev_langs:
- VB
helpviewer_keywords:
- enumerated constants
- Enum statement
- Private keyword, Enum statements
- Public keyword, in Enum statement
- variables [Visual Basic], enumeration
- constants, enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ff075349756bd4c568833d049b50b3c3721d1b08
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="53d69-102">Оператор Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53d69-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="53d69-103">Объявляет перечисление и определяет значения его членов.</span><span class="sxs-lookup"><span data-stu-id="53d69-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53d69-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="53d69-105">Части</span><span class="sxs-lookup"><span data-stu-id="53d69-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="53d69-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-106">Optional.</span></span> <span data-ttu-id="53d69-107">Список атрибутов, применяемых для данного перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="53d69-108">Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).</span><span class="sxs-lookup"><span data-stu-id="53d69-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="53d69-109"><xref:System.FlagsAttribute>Атрибут указывает, что значение экземпляра перечисления может содержать несколько членов перечисления, и что каждый элемент представляет собой битовое поле, в значение перечисления.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="53d69-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="53d69-110">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-110">Optional.</span></span> <span data-ttu-id="53d69-111">Указывает, какой код может получить доступ к этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="53d69-112">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="53d69-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="53d69-113">Public</span><span class="sxs-lookup"><span data-stu-id="53d69-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="53d69-114">Protected</span><span class="sxs-lookup"><span data-stu-id="53d69-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="53d69-115">Friend</span><span class="sxs-lookup"><span data-stu-id="53d69-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="53d69-116">Закрытые</span><span class="sxs-lookup"><span data-stu-id="53d69-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="53d69-117">Можно указать `Protected``Friend` для доступа из кода внутри класса перечисления, производного класса или той же сборки.</span><span class="sxs-lookup"><span data-stu-id="53d69-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="53d69-118">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-118">Optional.</span></span> <span data-ttu-id="53d69-119">Указывает, что данное перечисление повторно объявляет и скрывает идентично именованный программный элемент или набор перегружаемых элементов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="53d69-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="53d69-120">Можно указать [тени](../../../visual-basic/language-reference/modifiers/shadows.md) только на самом перечислении, а не на все его члены.</span><span class="sxs-lookup"><span data-stu-id="53d69-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="53d69-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-121">Required.</span></span> <span data-ttu-id="53d69-122">Имя перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-122">Name of the enumeration.</span></span> <span data-ttu-id="53d69-123">Сведения о допустимых именах см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="53d69-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="53d69-124">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-124">Optional.</span></span> <span data-ttu-id="53d69-125">Тип данных перечисления и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="53d69-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="53d69-126">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-126">Required.</span></span> <span data-ttu-id="53d69-127">Список констант элементов, объявляемых в этом операторе.</span><span class="sxs-lookup"><span data-stu-id="53d69-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="53d69-128">Несколько элементов отображаются на отдельных строках исходного кода.</span><span class="sxs-lookup"><span data-stu-id="53d69-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="53d69-129">Каждый `member` имеет следующий синтаксис и компоненты:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="53d69-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="53d69-130">Отделение</span><span class="sxs-lookup"><span data-stu-id="53d69-130">Part</span></span>|<span data-ttu-id="53d69-131">Описание</span><span class="sxs-lookup"><span data-stu-id="53d69-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="53d69-132">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-132">Required.</span></span> <span data-ttu-id="53d69-133">Имя данного элемента.</span><span class="sxs-lookup"><span data-stu-id="53d69-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="53d69-134">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="53d69-134">Optional.</span></span> <span data-ttu-id="53d69-135">Выражение, которое вычисляется во время компиляции и присваивается этому элементу.</span><span class="sxs-lookup"><span data-stu-id="53d69-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="53d69-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="53d69-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="53d69-137">Завершает блок `Enum`.</span><span class="sxs-lookup"><span data-stu-id="53d69-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53d69-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="53d69-138">Remarks</span></span>  
 <span data-ttu-id="53d69-139">Если имеется набор неизменных значений, логически связанных друг с другом, можно определить их вместе в перечислении.</span><span class="sxs-lookup"><span data-stu-id="53d69-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="53d69-140">Это обеспечивает значимые имена для перечисления и его членов, которые проще запомнить, чем их значения.</span><span class="sxs-lookup"><span data-stu-id="53d69-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="53d69-141">Затем можно использовать члены перечисления во многих местах в коде.</span><span class="sxs-lookup"><span data-stu-id="53d69-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="53d69-142">Преимущества использования перечисления включают следующие:</span><span class="sxs-lookup"><span data-stu-id="53d69-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="53d69-143">Уменьшает количество ошибок, вызванных перемещением или неправильным вводом значений.</span><span class="sxs-lookup"><span data-stu-id="53d69-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="53d69-144">Позволяет легко изменять значения в будущем.</span><span class="sxs-lookup"><span data-stu-id="53d69-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="53d69-145">Делает код более удобными для чтения, это означает, что маловероятно, что появилось новых ошибок.</span><span class="sxs-lookup"><span data-stu-id="53d69-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="53d69-146">Обеспечение прямой совместимости.</span><span class="sxs-lookup"><span data-stu-id="53d69-146">Ensures forward compatibility.</span></span> <span data-ttu-id="53d69-147">При использовании перечисления вероятность возникновения ошибок, если в будущем кто-то изменяет значения, соответствующие именам элементов кода.</span><span class="sxs-lookup"><span data-stu-id="53d69-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="53d69-148">Перечисления имеет имя, базовый тип данных и набор элементов.</span><span class="sxs-lookup"><span data-stu-id="53d69-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="53d69-149">Каждый элемент представляет константу.</span><span class="sxs-lookup"><span data-stu-id="53d69-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="53d69-150">Перечисление, объявленное на уровне интерфейса, вне любой процедуры, модуля, класса или структуры является *член перечисления*.</span><span class="sxs-lookup"><span data-stu-id="53d69-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="53d69-151">Она является членом класса, структуры, модуля или интерфейса, объявляющего его.</span><span class="sxs-lookup"><span data-stu-id="53d69-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="53d69-152">Член перечисления из может осуществляться в любом месте в пределах их класса, структуры, модуля или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="53d69-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="53d69-153">Код вне класса, структуры или модуля необходимо определять имя перечисления элементов с именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="53d69-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="53d69-154">Можно избежать необходимости использовать полные имена, добавив [импорта](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) инструкции к файлу исходного кода.</span><span class="sxs-lookup"><span data-stu-id="53d69-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="53d69-155">Перечисление, объявленное на уровне пространства имен, вне класса, структуры, модуля или интерфейса, является членом пространства имен, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="53d69-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="53d69-156">*Контекст объявления* для перечисления должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс и не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="53d69-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="53d69-157">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="53d69-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="53d69-158">Можно применять атрибуты к перечислению в целом, но не к его члены по отдельности.</span><span class="sxs-lookup"><span data-stu-id="53d69-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="53d69-159">Атрибут вносит сведения для метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="53d69-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="53d69-160">Тип данных</span><span class="sxs-lookup"><span data-stu-id="53d69-160">Data Type</span></span>  
 <span data-ttu-id="53d69-161">`Enum` Оператора можно объявлять тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="53d69-162">Каждый элемент принимает тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="53d69-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span><span class="sxs-lookup"><span data-stu-id="53d69-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="53d69-164">Если вы не укажете `datatype` для перечисления, каждый элемент имеет тип данных его `initializer`.</span><span class="sxs-lookup"><span data-stu-id="53d69-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="53d69-165">Если указываются оба `datatype` и `initializer`, тип данных `initializer` должен быть преобразуемым к `datatype`.</span><span class="sxs-lookup"><span data-stu-id="53d69-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="53d69-166">Если ни одна из `datatype` , ни `initializer` присутствует, по умолчанию для типа данных `Integer`.</span><span class="sxs-lookup"><span data-stu-id="53d69-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="53d69-167">Инициализация элементов</span><span class="sxs-lookup"><span data-stu-id="53d69-167">Initializing Members</span></span>  
 <span data-ttu-id="53d69-168">`Enum` Оператор может инициализировать содержимое выбранных элементов в `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="53d69-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="53d69-169">Использовать `initializer` позволяет указать выражение для назначения члена.</span><span class="sxs-lookup"><span data-stu-id="53d69-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="53d69-170">Если не указать `initializer` для члена, Visual Basic инициализирует его, либо ноль (если он является первым `member` в `memberlist`), или в значение на единицу, чем непосредственно перед `member`.</span><span class="sxs-lookup"><span data-stu-id="53d69-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="53d69-171">Выражения, предоставленного в каждом `initializer` может быть любым сочетанием литералов, других, уже определенные константы и члены перечисления, которые уже определены, включая предыдущего члена этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="53d69-172">Для комбинирования этих элементов можно использовать арифметические и логические операторы.</span><span class="sxs-lookup"><span data-stu-id="53d69-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="53d69-173">Нельзя использовать переменные или функции в `initializer`.</span><span class="sxs-lookup"><span data-stu-id="53d69-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="53d69-174">Однако можно использовать ключевые слова преобразования, такие как `CByte` и `CShort`.</span><span class="sxs-lookup"><span data-stu-id="53d69-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="53d69-175">Можно также использовать `AscW` при вызове с константой `String` или `Char` аргумент, поскольку, может быть вычислено во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="53d69-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="53d69-176">Перечисления не могут иметь значений с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="53d69-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="53d69-177">Если член присваивается значение с плавающей запятой и `Option Strict` имеет значение on, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="53d69-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="53d69-178">Если `Option Strict` выключен, то значение автоматически преобразуется в `Enum` типа.</span><span class="sxs-lookup"><span data-stu-id="53d69-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="53d69-179">Если значение члена превосходит верхнюю границу для базового типа данных или инициализации любого члена к допустимому значению базового типа данных, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="53d69-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="53d69-180">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="53d69-180">Modifiers</span></span>  
 <span data-ttu-id="53d69-181">Класс, структура, модуль и интерфейс элемента перечисления по умолчанию общий доступ.</span><span class="sxs-lookup"><span data-stu-id="53d69-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="53d69-182">Можно настроить их уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="53d69-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="53d69-183">Пространство имен элемента перечисления по умолчанию дружественный доступ.</span><span class="sxs-lookup"><span data-stu-id="53d69-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="53d69-184">Можно настроить их уровни доступа к общедоступным, но не к закрытым или защищенным.</span><span class="sxs-lookup"><span data-stu-id="53d69-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="53d69-185">Дополнительные сведения см. в разделе [уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="53d69-185">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="53d69-186">Все элементы перечисления имеют общий доступ, и на них нельзя использовать никакие модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="53d69-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="53d69-187">Однако если перечисление само имеет более ограниченный уровень доступа, указанный уровень доступа перечисления имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="53d69-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="53d69-188">По умолчанию все перечисления являются типами и их поля являются константами.</span><span class="sxs-lookup"><span data-stu-id="53d69-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="53d69-189">Поэтому `Shared`, `Static`, и `ReadOnly` ключевые слова нельзя использовать при объявлении перечисления или его элементов.</span><span class="sxs-lookup"><span data-stu-id="53d69-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="53d69-190">Назначение нескольких значений</span><span class="sxs-lookup"><span data-stu-id="53d69-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="53d69-191">Перечисления обычно представляют собой взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="53d69-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="53d69-192">Включив <xref:System.FlagsAttribute>атрибут `Enum` объявление, можно вместо этого назначить несколько значений экземпляра перечисления.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="53d69-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="53d69-193"><xref:System.FlagsAttribute>Атрибут указывает, что перечисление рассматриваться как битовое поле, то есть набор флагов.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="53d69-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="53d69-194">Это называется *побитовое* перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="53d69-195">При объявлении перечисления с помощью <xref:System.FlagsAttribute>атрибут, рекомендуется использовать степени числа 2, который является, 1, 2, 4, 8, 16 и так далее, для значения.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="53d69-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="53d69-196">Также рекомендуется «None» имя элемента, значение которого равно 0.</span><span class="sxs-lookup"><span data-stu-id="53d69-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="53d69-197">Дополнительные рекомендации см. в разделе <xref:System.FlagsAttribute>и <xref:System.Enum>.</xref:System.Enum> </xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="53d69-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d69-198">Пример</span><span class="sxs-lookup"><span data-stu-id="53d69-198">Example</span></span>  
 <span data-ttu-id="53d69-199">В следующем примере показано, как использовать `Enum` инструкции.</span><span class="sxs-lookup"><span data-stu-id="53d69-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="53d69-200">Обратите внимание, что элемент называется `EggSizeEnum.Medium`, а не как `Medium`.</span><span class="sxs-lookup"><span data-stu-id="53d69-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 <span data-ttu-id="53d69-201">[!code-vb[VbEnumsTask&#41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="53d69-201">[!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d69-202">Пример</span><span class="sxs-lookup"><span data-stu-id="53d69-202">Example</span></span>  
 <span data-ttu-id="53d69-203">В следующем примере метод находится за пределами `Egg` класса.</span><span class="sxs-lookup"><span data-stu-id="53d69-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="53d69-204">Таким образом `EggSizeEnum` которого полностью определено как `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="53d69-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 <span data-ttu-id="53d69-205">[!code-vb[VbEnumsTask&#42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="53d69-205">[!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d69-206">Пример</span><span class="sxs-lookup"><span data-stu-id="53d69-206">Example</span></span>  
 <span data-ttu-id="53d69-207">В следующем примере используется `Enum` инструкции для определения связанного набора именованных констант.</span><span class="sxs-lookup"><span data-stu-id="53d69-207">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="53d69-208">В этом случае значения цветов, которые можно выбрать для создаваемых форм ввода данных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="53d69-208">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 <span data-ttu-id="53d69-209">[!code-vb[VbEnumsTask&#30;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="53d69-209">[!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d69-210">Пример</span><span class="sxs-lookup"><span data-stu-id="53d69-210">Example</span></span>  
 <span data-ttu-id="53d69-211">В следующем примере показано значений, которые включают положительные и отрицательные числа.</span><span class="sxs-lookup"><span data-stu-id="53d69-211">The following example shows values that include both positive and negative numbers.</span></span>  
  
 <span data-ttu-id="53d69-212">[!code-vb[VbEnumsTask&#31;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="53d69-212">[!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d69-213">Пример</span><span class="sxs-lookup"><span data-stu-id="53d69-213">Example</span></span>  
 <span data-ttu-id="53d69-214">В следующем примере `As` предложение используется для указания `datatype` перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-214">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 <span data-ttu-id="53d69-215">[!code-vb[VbEnumsTask №&6;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="53d69-215">[!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d69-216">Пример</span><span class="sxs-lookup"><span data-stu-id="53d69-216">Example</span></span>  
 <span data-ttu-id="53d69-217">Следующий пример показывает использование побитового перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-217">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="53d69-218">Несколько значений может быть присвоено экземпляру побитового перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-218">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="53d69-219">`Enum` Объявление включает в себя <xref:System.FlagsAttribute>атрибут, который указывает, что перечисление может обрабатываться как набор флагов.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="53d69-219">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 <span data-ttu-id="53d69-220">[!code-vb[VbEnumsTask&#61;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="53d69-220">[!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d69-221">Пример</span><span class="sxs-lookup"><span data-stu-id="53d69-221">Example</span></span>  
 <span data-ttu-id="53d69-222">В следующем примере выполняется итерация по перечисления.</span><span class="sxs-lookup"><span data-stu-id="53d69-222">The following example iterates through an enumeration.</span></span> <span data-ttu-id="53d69-223">Он использует <xref:System.Enum.GetNames%2A>метод для получения массива имен членов из перечисления, и <xref:System.Enum.GetValues%2A>для извлечения массива значений членов.</xref:System.Enum.GetValues%2A> </xref:System.Enum.GetNames%2A></span><span class="sxs-lookup"><span data-stu-id="53d69-223">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 <span data-ttu-id="53d69-224">[!code-vb[VbEnumsTask&#51;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="53d69-224">[!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d69-225">См. также</span><span class="sxs-lookup"><span data-stu-id="53d69-225">See Also</span></span>  
 <span data-ttu-id="53d69-226"><xref:System.Enum></xref:System.Enum></span><span class="sxs-lookup"><span data-stu-id="53d69-226"><xref:System.Enum></span></span>   
 <span data-ttu-id="53d69-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="53d69-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
<span data-ttu-id="53d69-228"> [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="53d69-228"> [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="53d69-229"> [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="53d69-229"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="53d69-230"> [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="53d69-230"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="53d69-231"> [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="53d69-231"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="53d69-232"> [Константы и перечисления](../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="53d69-232"> [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
