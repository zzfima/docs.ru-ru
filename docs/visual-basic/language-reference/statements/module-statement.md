---
title: Оператор Module (Visual Basic)
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
ms.openlocfilehash: 08268fd473a3a916f41f2f46090e3245acda07dd
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513009"
---
# <a name="module-statement"></a><span data-ttu-id="a7af9-102">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="a7af9-102">Module Statement</span></span>
<span data-ttu-id="a7af9-103">Объявляет имя модуля и вводит определение переменных, свойств, событий и процедур, которые входят в модуль.</span><span class="sxs-lookup"><span data-stu-id="a7af9-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7af9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7af9-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="a7af9-105">Части</span><span class="sxs-lookup"><span data-stu-id="a7af9-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="a7af9-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a7af9-106">Optional.</span></span> <span data-ttu-id="a7af9-107">См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="a7af9-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a7af9-108">Optional.</span></span> <span data-ttu-id="a7af9-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="a7af9-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="a7af9-110">Public</span><span class="sxs-lookup"><span data-stu-id="a7af9-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
- [<span data-ttu-id="a7af9-111">Friend</span><span class="sxs-lookup"><span data-stu-id="a7af9-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="a7af9-112">См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="a7af9-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a7af9-113">Required.</span></span> <span data-ttu-id="a7af9-114">Имя этого модуля.</span><span class="sxs-lookup"><span data-stu-id="a7af9-114">Name of this module.</span></span> <span data-ttu-id="a7af9-115">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="a7af9-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a7af9-116">Optional.</span></span> <span data-ttu-id="a7af9-117">Инструкции, которые определяют переменные, свойства, события, процедуры и вложенные типы этого модуля.</span><span class="sxs-lookup"><span data-stu-id="a7af9-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="a7af9-118">`Module` Завершает определение.</span><span class="sxs-lookup"><span data-stu-id="a7af9-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7af9-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7af9-119">Remarks</span></span>  
 <span data-ttu-id="a7af9-120">`Module` Оператор определяет ссылочный тип, доступный в пределах его пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a7af9-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="a7af9-121">*Модуль* (иногда называемый *стандартным модулем*) аналогичен классу, но с некоторыми важными различиями.</span><span class="sxs-lookup"><span data-stu-id="a7af9-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="a7af9-122">Каждый модуль имеет ровно один экземпляр и не требует создания или назначения переменной.</span><span class="sxs-lookup"><span data-stu-id="a7af9-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="a7af9-123">Модули не поддерживают наследование или реализуют интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="a7af9-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="a7af9-124">Обратите внимание, что модуль не является *типом* в том смысле, что класс или структура — нельзя объявить программный элемент для типа данных модуля.</span><span class="sxs-lookup"><span data-stu-id="a7af9-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="a7af9-125">Можно использовать `Module` только на уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a7af9-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="a7af9-126">Это означает, что *контекст объявления* для модуля должен быть исходным файлом или пространством имен и не может быть классом, структурой, модулем, интерфейсом, процедурой или блоком.</span><span class="sxs-lookup"><span data-stu-id="a7af9-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="a7af9-127">Модуль нельзя вложить в другой модуль или в любой тип.</span><span class="sxs-lookup"><span data-stu-id="a7af9-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="a7af9-128">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="a7af9-129">Модуль имеет то же время, что и программа.</span><span class="sxs-lookup"><span data-stu-id="a7af9-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="a7af9-130">Так как все его члены `Shared`все же, они также имеют время существования, равное значению программы.</span><span class="sxs-lookup"><span data-stu-id="a7af9-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="a7af9-131">Модули по умолчанию имеют доступ [Friend](../../../visual-basic/language-reference/modifiers/friend.md) .</span><span class="sxs-lookup"><span data-stu-id="a7af9-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="a7af9-132">Уровни доступа можно изменить с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="a7af9-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="a7af9-133">Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="a7af9-134">Все члены модуля являются неявными `Shared`.</span><span class="sxs-lookup"><span data-stu-id="a7af9-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="a7af9-135">Классы и модули</span><span class="sxs-lookup"><span data-stu-id="a7af9-135">Classes and Modules</span></span>  
 <span data-ttu-id="a7af9-136">У этих элементов много сходства, но есть и некоторые важные отличия.</span><span class="sxs-lookup"><span data-stu-id="a7af9-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
- <span data-ttu-id="a7af9-137">**Терминология.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-137">**Terminology.**</span></span> <span data-ttu-id="a7af9-138">В предыдущих версиях Visual Basic распознаются два типа модулей: *модули классов* (CLS-файлы) и *стандартные модули* (файлы. BAS).</span><span class="sxs-lookup"><span data-stu-id="a7af9-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="a7af9-139">Текущая версия вызывает эти *классы* и *модули*соответственно.</span><span class="sxs-lookup"><span data-stu-id="a7af9-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
- <span data-ttu-id="a7af9-140">**Общие члены.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-140">**Shared Members.**</span></span> <span data-ttu-id="a7af9-141">Можно контролировать, является ли член класса общим или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a7af9-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
- <span data-ttu-id="a7af9-142">**Объектная ориентация.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-142">**Object Orientation.**</span></span> <span data-ttu-id="a7af9-143">Классы являются объектно-ориентированными, но модули — нет.</span><span class="sxs-lookup"><span data-stu-id="a7af9-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="a7af9-144">Таким образом, можно создавать экземпляры только классов в виде объектов.</span><span class="sxs-lookup"><span data-stu-id="a7af9-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="a7af9-145">Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a7af9-146">Правила</span><span class="sxs-lookup"><span data-stu-id="a7af9-146">Rules</span></span>  
  
- <span data-ttu-id="a7af9-147">**Модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-147">**Modifiers.**</span></span> <span data-ttu-id="a7af9-148">Все члены модуля неявно являются [общими](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="a7af9-149">Нельзя использовать `Shared` ключевое слово при объявлении члена, и изменить общее состояние любого члена нельзя.</span><span class="sxs-lookup"><span data-stu-id="a7af9-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
- <span data-ttu-id="a7af9-150">**Наследование.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-150">**Inheritance.**</span></span> <span data-ttu-id="a7af9-151">Модуль не может наследовать ни от какого типа <xref:System.Object>, от которого наследуют все модули.</span><span class="sxs-lookup"><span data-stu-id="a7af9-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="a7af9-152">В частности, один модуль не может наследовать от другого.</span><span class="sxs-lookup"><span data-stu-id="a7af9-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="a7af9-153">Нельзя использовать инструкцию [Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) в определении модуля, даже для указания <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="a7af9-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
- <span data-ttu-id="a7af9-154">**Свойство по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-154">**Default Property.**</span></span> <span data-ttu-id="a7af9-155">В модуле нельзя определить свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7af9-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="a7af9-156">Дополнительные сведения см. в разделе [Default](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a7af9-157">Поведение</span><span class="sxs-lookup"><span data-stu-id="a7af9-157">Behavior</span></span>  
  
- <span data-ttu-id="a7af9-158">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-158">**Access Level.**</span></span> <span data-ttu-id="a7af9-159">Внутри модуля можно объявить каждый элемент с собственным уровнем доступа.</span><span class="sxs-lookup"><span data-stu-id="a7af9-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="a7af9-160">Члены модуля по умолчанию имеют [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ, за исключением переменных и констант, которые по умолчанию имеют [частный](../../../visual-basic/language-reference/modifiers/private.md) доступ.</span><span class="sxs-lookup"><span data-stu-id="a7af9-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="a7af9-161">Если модуль имеет более ограниченный доступ, чем один из его членов, приоритет имеет указанный уровень доступа к модулю.</span><span class="sxs-lookup"><span data-stu-id="a7af9-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
- <span data-ttu-id="a7af9-162">**Которых.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-162">**Scope.**</span></span> <span data-ttu-id="a7af9-163">Модуль находится в пределах пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a7af9-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="a7af9-164">Областью действия каждого члена модуля является весь модуль.</span><span class="sxs-lookup"><span data-stu-id="a7af9-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="a7af9-165">Обратите внимание, что все члены проводят *продвижение по типам*, что приводит к повышению уровня их области до пространства имен, содержащего модуль.</span><span class="sxs-lookup"><span data-stu-id="a7af9-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="a7af9-166">Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
- <span data-ttu-id="a7af9-167">**Квалификацию.**</span><span class="sxs-lookup"><span data-stu-id="a7af9-167">**Qualification.**</span></span> <span data-ttu-id="a7af9-168">В проекте может быть несколько модулей, и члены с одинаковыми именами можно объявить в двух или более модулях.</span><span class="sxs-lookup"><span data-stu-id="a7af9-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="a7af9-169">Однако необходимо определить любую ссылку на такой элемент с соответствующим именем модуля, если ссылка находится за пределами этого модуля.</span><span class="sxs-lookup"><span data-stu-id="a7af9-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="a7af9-170">Для получения дополнительной информации см. [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="a7af9-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7af9-171">Пример</span><span class="sxs-lookup"><span data-stu-id="a7af9-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a><span data-ttu-id="a7af9-172">См. также</span><span class="sxs-lookup"><span data-stu-id="a7af9-172">See also</span></span>

- [<span data-ttu-id="a7af9-173">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="a7af9-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="a7af9-174">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="a7af9-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="a7af9-175">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="a7af9-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="a7af9-176">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="a7af9-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="a7af9-177">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="a7af9-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="a7af9-178">Повышение типа</span><span class="sxs-lookup"><span data-stu-id="a7af9-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
