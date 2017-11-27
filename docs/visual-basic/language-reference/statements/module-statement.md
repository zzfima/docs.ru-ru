---
title: "Оператор Module"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92cdcd1919f21243118108da3bc382ea5d954130
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="module-statement"></a><span data-ttu-id="982d0-102">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="982d0-102">Module Statement</span></span>
<span data-ttu-id="982d0-103">Объявляет имя модуля и представляет определения переменных, свойств, событий и процедур, которые включены в модуль.</span><span class="sxs-lookup"><span data-stu-id="982d0-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="982d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="982d0-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="982d0-105">Части</span><span class="sxs-lookup"><span data-stu-id="982d0-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="982d0-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="982d0-106">Optional.</span></span> <span data-ttu-id="982d0-107">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="982d0-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="982d0-108">Optional.</span></span> <span data-ttu-id="982d0-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="982d0-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="982d0-110">Public</span><span class="sxs-lookup"><span data-stu-id="982d0-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="982d0-111">Friend</span><span class="sxs-lookup"><span data-stu-id="982d0-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="982d0-112">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="982d0-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="982d0-113">Required.</span></span> <span data-ttu-id="982d0-114">Имя этого модуля.</span><span class="sxs-lookup"><span data-stu-id="982d0-114">Name of this module.</span></span> <span data-ttu-id="982d0-115">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="982d0-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="982d0-116">Optional.</span></span> <span data-ttu-id="982d0-117">Операторы, которые определяют переменные, свойства, события, процедуры и вложенные типы этого модуля.</span><span class="sxs-lookup"><span data-stu-id="982d0-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="982d0-118">Завершает `Module` определения.</span><span class="sxs-lookup"><span data-stu-id="982d0-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="982d0-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="982d0-119">Remarks</span></span>  
 <span data-ttu-id="982d0-120">Объект `Module` инструкция определяет ссылочный тип, доступный всего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="982d0-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="982d0-121">Объект *модуль* (иногда называется *стандартного модуля*) похож на класс, но некоторые важные различия.</span><span class="sxs-lookup"><span data-stu-id="982d0-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="982d0-122">Каждый модуль имеет ровно один экземпляр и не должны быть созданы или присваивается переменной.</span><span class="sxs-lookup"><span data-stu-id="982d0-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="982d0-123">Модули не поддерживают наследование и не реализуют интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="982d0-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="982d0-124">Обратите внимание, что модуль не *типа* в том смысле, что класс или структура, нельзя объявлять элемент программирования с типом данных модуля.</span><span class="sxs-lookup"><span data-stu-id="982d0-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="982d0-125">Можно использовать `Module` только на уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="982d0-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="982d0-126">Это означает *контекст объявления* для модуля должен быть исходным файлом или пространством имен и не может быть класс, структура, модуль, интерфейса, процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="982d0-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="982d0-127">Нельзя вкладывать модуль в другой модуль или в любой тип.</span><span class="sxs-lookup"><span data-stu-id="982d0-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="982d0-128">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="982d0-129">Модуль имеет то же время существования, в ходе выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="982d0-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="982d0-130">Так как все его члены являются `Shared`, они также имеют время жизни, равное программы.</span><span class="sxs-lookup"><span data-stu-id="982d0-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="982d0-131">По умолчанию модули [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа.</span><span class="sxs-lookup"><span data-stu-id="982d0-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="982d0-132">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="982d0-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="982d0-133">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="982d0-134">Все элементы модуля являются неявно `Shared`.</span><span class="sxs-lookup"><span data-stu-id="982d0-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="982d0-135">Классы и модули</span><span class="sxs-lookup"><span data-stu-id="982d0-135">Classes and Modules</span></span>  
 <span data-ttu-id="982d0-136">Эти элементы имеют много общего, но существуют некоторые важные различия.</span><span class="sxs-lookup"><span data-stu-id="982d0-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="982d0-137">**Терминология.**</span><span class="sxs-lookup"><span data-stu-id="982d0-137">**Terminology.**</span></span> <span data-ttu-id="982d0-138">Предыдущие версии Visual Basic распознает два типа модулей: *модулей класса* (файлы CLS) и *стандартные модули* (файлы BAS).</span><span class="sxs-lookup"><span data-stu-id="982d0-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="982d0-139">Текущая версия вызывает эти *классы* и *модули*соответственно.</span><span class="sxs-lookup"><span data-stu-id="982d0-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="982d0-140">**Общие члены.**</span><span class="sxs-lookup"><span data-stu-id="982d0-140">**Shared Members.**</span></span> <span data-ttu-id="982d0-141">Можно управлять ли член класса общим или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="982d0-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="982d0-142">**Ориентация на объекты.**</span><span class="sxs-lookup"><span data-stu-id="982d0-142">**Object Orientation.**</span></span> <span data-ttu-id="982d0-143">Классы являются объектно ориентированного, но модули не будут.</span><span class="sxs-lookup"><span data-stu-id="982d0-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="982d0-144">Поэтому только классы могут быть созданы как объекты.</span><span class="sxs-lookup"><span data-stu-id="982d0-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="982d0-145">Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="982d0-146">Правила</span><span class="sxs-lookup"><span data-stu-id="982d0-146">Rules</span></span>  
  
-   <span data-ttu-id="982d0-147">**Модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="982d0-147">**Modifiers.**</span></span> <span data-ttu-id="982d0-148">Все элементы модуля являются неявно [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="982d0-149">Нельзя использовать `Shared` ключевого слова при объявлении члена и невозможно изменить состояние любого члена общего доступа.</span><span class="sxs-lookup"><span data-stu-id="982d0-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="982d0-150">**Наследование.**</span><span class="sxs-lookup"><span data-stu-id="982d0-150">**Inheritance.**</span></span> <span data-ttu-id="982d0-151">Модуль не может наследовать от типа, отличного от <xref:System.Object>, из всех модулей, которые наследуют.</span><span class="sxs-lookup"><span data-stu-id="982d0-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="982d0-152">В частности один модуль не может наследовать от другого.</span><span class="sxs-lookup"><span data-stu-id="982d0-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="982d0-153">Нельзя использовать [инструкцию наследует](../../../visual-basic/language-reference/statements/inherits-statement.md) в определение модуля, даже для указания <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="982d0-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="982d0-154">**Свойство по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="982d0-154">**Default Property.**</span></span> <span data-ttu-id="982d0-155">В модуле нельзя определять свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="982d0-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="982d0-156">Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="982d0-157">Поведение</span><span class="sxs-lookup"><span data-stu-id="982d0-157">Behavior</span></span>  
  
-   <span data-ttu-id="982d0-158">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="982d0-158">**Access Level.**</span></span> <span data-ttu-id="982d0-159">Внутри модуля можно объявить каждый член со своим собственным уровнем доступа.</span><span class="sxs-lookup"><span data-stu-id="982d0-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="982d0-160">Элементы модуля по умолчанию [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ к, за исключением переменных и констант, который по умолчанию для [закрытый](../../../visual-basic/language-reference/modifiers/private.md) доступа.</span><span class="sxs-lookup"><span data-stu-id="982d0-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="982d0-161">Если модуль более ограниченный доступ, чем один из его членов, уровень доступа указанный модуль имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="982d0-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="982d0-162">**Область действия.**</span><span class="sxs-lookup"><span data-stu-id="982d0-162">**Scope.**</span></span> <span data-ttu-id="982d0-163">Модуль — область действия пространства имен.</span><span class="sxs-lookup"><span data-stu-id="982d0-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="982d0-164">Область для каждого элемента модуля является весь модуль.</span><span class="sxs-lookup"><span data-stu-id="982d0-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="982d0-165">Обратите внимание, что все элементы претерпевают *введите рекламной акции*, что приводит к повышению до пространства имен, содержащего модуль их области.</span><span class="sxs-lookup"><span data-stu-id="982d0-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="982d0-166">Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="982d0-167">**Квалификация.**</span><span class="sxs-lookup"><span data-stu-id="982d0-167">**Qualification.**</span></span> <span data-ttu-id="982d0-168">В проекте может быть несколько модулей, и можно объявить члены с тем же именем в два или несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="982d0-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="982d0-169">Тем не менее если ссылка находится за пределами этого модуля необходимо предварять любая ссылка на элемент с именем соответствующего модуля.</span><span class="sxs-lookup"><span data-stu-id="982d0-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="982d0-170">Дополнительные сведения см. в разделе [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="982d0-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="982d0-171">Пример</span><span class="sxs-lookup"><span data-stu-id="982d0-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="982d0-172">См. также</span><span class="sxs-lookup"><span data-stu-id="982d0-172">See Also</span></span>  
 [<span data-ttu-id="982d0-173">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="982d0-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="982d0-174">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="982d0-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="982d0-175">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="982d0-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="982d0-176">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="982d0-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="982d0-177">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="982d0-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="982d0-178">Повышение типа</span><span class="sxs-lookup"><span data-stu-id="982d0-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
