---
title: Оператор модуля (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47086818"
---
# <a name="module-statement"></a><span data-ttu-id="04627-102">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="04627-102">Module Statement</span></span>
<span data-ttu-id="04627-103">Объявляет имя модуля и вводит определение переменных, свойств, событий и процедур, которые включены в модуль.</span><span class="sxs-lookup"><span data-stu-id="04627-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04627-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04627-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="04627-105">Части</span><span class="sxs-lookup"><span data-stu-id="04627-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="04627-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="04627-106">Optional.</span></span> <span data-ttu-id="04627-107">См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="04627-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="04627-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="04627-108">Optional.</span></span> <span data-ttu-id="04627-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="04627-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="04627-110">Public</span><span class="sxs-lookup"><span data-stu-id="04627-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="04627-111">Friend</span><span class="sxs-lookup"><span data-stu-id="04627-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="04627-112">См. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="04627-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="04627-113">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="04627-113">Required.</span></span> <span data-ttu-id="04627-114">Имя этого модуля.</span><span class="sxs-lookup"><span data-stu-id="04627-114">Name of this module.</span></span> <span data-ttu-id="04627-115">См. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="04627-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="04627-116">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="04627-116">Optional.</span></span> <span data-ttu-id="04627-117">Операторы, которые определяют переменные, свойства, события, процедуры и вложенные типы этого модуля.</span><span class="sxs-lookup"><span data-stu-id="04627-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="04627-118">Завершает `Module` определения.</span><span class="sxs-lookup"><span data-stu-id="04627-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04627-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="04627-119">Remarks</span></span>  
 <span data-ttu-id="04627-120">Объект `Module` инструкция определяет ссылочный тип, доступный на протяжении всего его пространство имен.</span><span class="sxs-lookup"><span data-stu-id="04627-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="04627-121">Объект *модуль* (иногда называют *стандартного модуля*) похож на класс, но некоторые важные различия.</span><span class="sxs-lookup"><span data-stu-id="04627-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="04627-122">Каждый модуль имеет только один экземпляр и не должны быть созданы и присваивается переменной.</span><span class="sxs-lookup"><span data-stu-id="04627-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="04627-123">Модули не поддерживают наследование и не реализуют интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="04627-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="04627-124">Обратите внимание, что модуль не является *тип* в том смысле, что класс или структура, нельзя объявлять программный элемент как имеющие тип данных модуля.</span><span class="sxs-lookup"><span data-stu-id="04627-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="04627-125">Можно использовать `Module` только на уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="04627-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="04627-126">Это означает, что *контекст объявления* для модуля должен быть исходным файлом или пространством имен и не может быть класс, структура, модуль, интерфейс, процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="04627-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="04627-127">Нельзя вкладывать модуль в другом модуле, или внутри любого типа.</span><span class="sxs-lookup"><span data-stu-id="04627-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="04627-128">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="04627-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="04627-129">Модуль имеет одинаковое время существования программы.</span><span class="sxs-lookup"><span data-stu-id="04627-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="04627-130">Так как все его члены являются `Shared`, они также имеют время существования, равный программы.</span><span class="sxs-lookup"><span data-stu-id="04627-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="04627-131">По умолчанию модули [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа.</span><span class="sxs-lookup"><span data-stu-id="04627-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="04627-132">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="04627-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="04627-133">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="04627-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="04627-134">Все члены модуля являются неявно `Shared`.</span><span class="sxs-lookup"><span data-stu-id="04627-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="04627-135">Классы и модули</span><span class="sxs-lookup"><span data-stu-id="04627-135">Classes and Modules</span></span>  
 <span data-ttu-id="04627-136">Эти элементы имеют много общего, но существуют также некоторые важные различия.</span><span class="sxs-lookup"><span data-stu-id="04627-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="04627-137">**Терминология.**</span><span class="sxs-lookup"><span data-stu-id="04627-137">**Terminology.**</span></span> <span data-ttu-id="04627-138">Предыдущие версии Visual Basic распознает два типа модулей: *модулей класса* (файлы CLS) и *стандартные модули* (файлы BAS).</span><span class="sxs-lookup"><span data-stu-id="04627-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="04627-139">Текущая версия вызывает эти *классы* и *модули*, соответственно.</span><span class="sxs-lookup"><span data-stu-id="04627-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="04627-140">**Общие члены.**</span><span class="sxs-lookup"><span data-stu-id="04627-140">**Shared Members.**</span></span> <span data-ttu-id="04627-141">Указать, можно ли член класса общим или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="04627-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="04627-142">**Ориентация на объекты.**</span><span class="sxs-lookup"><span data-stu-id="04627-142">**Object Orientation.**</span></span> <span data-ttu-id="04627-143">Классы являются объектно ориентированными, но модули не будут.</span><span class="sxs-lookup"><span data-stu-id="04627-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="04627-144">Поэтому только классы могут быть созданы как объекты.</span><span class="sxs-lookup"><span data-stu-id="04627-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="04627-145">Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="04627-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="04627-146">Правила</span><span class="sxs-lookup"><span data-stu-id="04627-146">Rules</span></span>  
  
-   <span data-ttu-id="04627-147">**Модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="04627-147">**Modifiers.**</span></span> <span data-ttu-id="04627-148">Все элементы модуля являются неявно [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="04627-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="04627-149">Нельзя использовать `Shared` ключевое слово при объявлении члена, а также невозможно изменить состояние любого члена общего доступа.</span><span class="sxs-lookup"><span data-stu-id="04627-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="04627-150">**Наследование.**</span><span class="sxs-lookup"><span data-stu-id="04627-150">**Inheritance.**</span></span> <span data-ttu-id="04627-151">Модуль не может наследовать от любого типа, отличного от <xref:System.Object>, из всех модулей, которые наследуют.</span><span class="sxs-lookup"><span data-stu-id="04627-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="04627-152">В частности один модуль не может наследовать от другого.</span><span class="sxs-lookup"><span data-stu-id="04627-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="04627-153">Нельзя использовать [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) в определении модуля, даже для указания <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="04627-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="04627-154">**Свойство по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="04627-154">**Default Property.**</span></span> <span data-ttu-id="04627-155">Не удается определить свойства по умолчанию в модуле.</span><span class="sxs-lookup"><span data-stu-id="04627-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="04627-156">Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="04627-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="04627-157">Поведение</span><span class="sxs-lookup"><span data-stu-id="04627-157">Behavior</span></span>  
  
-   <span data-ttu-id="04627-158">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="04627-158">**Access Level.**</span></span> <span data-ttu-id="04627-159">Внутри модуля можно объявить каждый член со своим собственным уровнем доступа.</span><span class="sxs-lookup"><span data-stu-id="04627-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="04627-160">Элементы модуля по умолчанию [открытый](../../../visual-basic/language-reference/modifiers/public.md) получить доступ к, за исключением переменных и констант, по умолчанию для [частного](../../../visual-basic/language-reference/modifiers/private.md) доступа.</span><span class="sxs-lookup"><span data-stu-id="04627-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="04627-161">Если модуль более ограниченный доступ, чем один из его членов, уровень доступа указанный модуль имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="04627-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="04627-162">**Область.**</span><span class="sxs-lookup"><span data-stu-id="04627-162">**Scope.**</span></span> <span data-ttu-id="04627-163">Модуль — область действия его пространство имен.</span><span class="sxs-lookup"><span data-stu-id="04627-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="04627-164">Областью для каждого элемента модуля является весь модуль.</span><span class="sxs-lookup"><span data-stu-id="04627-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="04627-165">Обратите внимание, что все элементы претерпевают *повышение типа*, который приводит к их области, повышаются до пространства имен, содержащего модуль.</span><span class="sxs-lookup"><span data-stu-id="04627-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="04627-166">Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="04627-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="04627-167">**Квалификации.**</span><span class="sxs-lookup"><span data-stu-id="04627-167">**Qualification.**</span></span> <span data-ttu-id="04627-168">Может быть несколько модулей в проекте, и можно объявить члены с тем же именем в два или несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="04627-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="04627-169">Тем не менее любая ссылка на элемент с именем соответствующего модуля необходимо уточнить, если ссылка находится за пределами этого модуля.</span><span class="sxs-lookup"><span data-stu-id="04627-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="04627-170">Дополнительные сведения см. в разделе [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="04627-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04627-171">Пример</span><span class="sxs-lookup"><span data-stu-id="04627-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04627-172">См. также</span><span class="sxs-lookup"><span data-stu-id="04627-172">See Also</span></span>  
 [<span data-ttu-id="04627-173">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="04627-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="04627-174">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="04627-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="04627-175">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="04627-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="04627-176">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="04627-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="04627-177">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="04627-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="04627-178">Повышение типа</span><span class="sxs-lookup"><span data-stu-id="04627-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
