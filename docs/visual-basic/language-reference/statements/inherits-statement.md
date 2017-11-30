---
title: Inherits Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ae9ba54c3fd1ec3332c9f6260bc19a1293270ad8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="inherits-statement"></a><span data-ttu-id="a9844-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="a9844-102">Inherits Statement</span></span>
<span data-ttu-id="a9844-103">Вызывает текущий класс или интерфейс для наследования атрибутов, переменных, свойства, процедуры и события из другого класса или набора интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a9844-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9844-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9844-104">Syntax</span></span>  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="a9844-105">Части</span><span class="sxs-lookup"><span data-stu-id="a9844-105">Parts</span></span>  
  
|<span data-ttu-id="a9844-106">Термин</span><span class="sxs-lookup"><span data-stu-id="a9844-106">Term</span></span>|<span data-ttu-id="a9844-107">Определение</span><span class="sxs-lookup"><span data-stu-id="a9844-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="a9844-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a9844-108">Required.</span></span> <span data-ttu-id="a9844-109">Имя класса, из которого происходит данный класс.</span><span class="sxs-lookup"><span data-stu-id="a9844-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="a9844-110">-или-</span><span class="sxs-lookup"><span data-stu-id="a9844-110">-or-</span></span><br /><br /> <span data-ttu-id="a9844-111">Имена интерфейсов, из которых производится данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a9844-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="a9844-112">Используйте запятые для разделения нескольких имен.</span><span class="sxs-lookup"><span data-stu-id="a9844-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9844-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9844-113">Remarks</span></span>  
 <span data-ttu-id="a9844-114">При использовании `Inherits` инструкция должна быть первой непустой незакомментированной строкой в определении класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a9844-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="a9844-115">Он должен следовать непосредственно за `Class` или `Interface` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a9844-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="a9844-116">Можно использовать `Inherits` только в классе или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="a9844-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="a9844-117">Это означает, что контекст объявления для наследования не может быть исходный файл, пространство имен, структура, модуль, процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="a9844-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a9844-118">Правила</span><span class="sxs-lookup"><span data-stu-id="a9844-118">Rules</span></span>  
  
-   <span data-ttu-id="a9844-119">**Наследование классов.**</span><span class="sxs-lookup"><span data-stu-id="a9844-119">**Class Inheritance.**</span></span> <span data-ttu-id="a9844-120">Если класс использует `Inherits` инструкции, можно указать только один базовый класс.</span><span class="sxs-lookup"><span data-stu-id="a9844-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="a9844-121">Класс не может наследовать от вложенного в него класса.</span><span class="sxs-lookup"><span data-stu-id="a9844-121">A class cannot inherit from a class nested within it.</span></span>  
  
-   <span data-ttu-id="a9844-122">**Наследование интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="a9844-122">**Interface Inheritance.**</span></span> <span data-ttu-id="a9844-123">Если интерфейс использует `Inherits` инструкции, можно указать один или несколько базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a9844-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="a9844-124">Можно наследовать от двух интерфейсов, даже если каждый из них определяют член с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="a9844-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="a9844-125">При этом код реализации должен использовать уточнение имени, чтобы указать, какие члены, он реализует.</span><span class="sxs-lookup"><span data-stu-id="a9844-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="a9844-126">Интерфейс не может наследовать от другого интерфейса с более строгим уровнем доступа.</span><span class="sxs-lookup"><span data-stu-id="a9844-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="a9844-127">Например `Public` интерфейс не может наследовать от `Friend` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a9844-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="a9844-128">Интерфейс не может наследовать от интерфейса, вложенного в него.</span><span class="sxs-lookup"><span data-stu-id="a9844-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="a9844-129">Пример наследования класса в .NET Framework — <xref:System.ArgumentException> класс, унаследованный от класса <xref:System.SystemException> класса.</span><span class="sxs-lookup"><span data-stu-id="a9844-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="a9844-130">Это обеспечивает с <xref:System.ArgumentException> стандартные свойства и процедуры, необходимые в исключениях системы, такие как <xref:System.Exception.Message%2A> свойство и <xref:System.Exception.ToString%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a9844-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="a9844-131">Пример наследования интерфейса в .NET Framework — <xref:System.Collections.ICollection> интерфейс, который наследует от <xref:System.Collections.IEnumerable> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a9844-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="a9844-132">В результате <xref:System.Collections.ICollection> наследование определения требуется, выполняющие перебор коллекции перечислителя.</span><span class="sxs-lookup"><span data-stu-id="a9844-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9844-133">Пример</span><span class="sxs-lookup"><span data-stu-id="a9844-133">Example</span></span>  
 <span data-ttu-id="a9844-134">В следующем примере используется `Inherits` инструкцию, чтобы показать, как класс с именем `thisClass` может наследовать все члены базового класса с именем `anotherClass`.</span><span class="sxs-lookup"><span data-stu-id="a9844-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="a9844-135">Пример</span><span class="sxs-lookup"><span data-stu-id="a9844-135">Example</span></span>  
 <span data-ttu-id="a9844-136">В следующем примере показано наследование от нескольких интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a9844-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 <span data-ttu-id="a9844-137">Интерфейс, с именем `thisInterface` теперь включает все определения в <xref:System.IComparable>, <xref:System.IDisposable>, и <xref:System.IFormattable> интерфейсы наследуемые члены предоставляют соответственно для сравнения двух объектов, освобождая ресурсы выделяются и задание значения объекта как `String`.</span><span class="sxs-lookup"><span data-stu-id="a9844-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="a9844-138">Класс, реализующий `thisInterface` необходимо реализовать каждый член каждого базового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a9844-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9844-139">См. также</span><span class="sxs-lookup"><span data-stu-id="a9844-139">See Also</span></span>  
 [<span data-ttu-id="a9844-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="a9844-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [<span data-ttu-id="a9844-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="a9844-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [<span data-ttu-id="a9844-142">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="a9844-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="a9844-143">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="a9844-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="a9844-144">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a9844-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
