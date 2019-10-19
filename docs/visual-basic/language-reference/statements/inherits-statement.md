---
title: Оператор Inherits (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: e92e12908c89bb7a0bf385a2122b0c8f1eb8a6f7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581756"
---
# <a name="inherits-statement"></a><span data-ttu-id="17c08-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="17c08-102">Inherits Statement</span></span>
<span data-ttu-id="17c08-103">Заставляет текущий класс или интерфейс наследовать атрибуты, переменные, свойства, процедуры и события из другого класса или набора интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="17c08-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17c08-104">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="17c08-105">Части</span><span class="sxs-lookup"><span data-stu-id="17c08-105">Parts</span></span>  
  
|<span data-ttu-id="17c08-106">Термин</span><span class="sxs-lookup"><span data-stu-id="17c08-106">Term</span></span>|<span data-ttu-id="17c08-107">Определение</span><span class="sxs-lookup"><span data-stu-id="17c08-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="17c08-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="17c08-108">Required.</span></span> <span data-ttu-id="17c08-109">Имя класса, от которого наследует этот класс.</span><span class="sxs-lookup"><span data-stu-id="17c08-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="17c08-110">\- или -</span><span class="sxs-lookup"><span data-stu-id="17c08-110">-or-</span></span><br /><br /> <span data-ttu-id="17c08-111">Имена интерфейсов, из которых наследуется этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="17c08-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="17c08-112">Используйте запятые для разделения нескольких имен.</span><span class="sxs-lookup"><span data-stu-id="17c08-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17c08-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="17c08-113">Remarks</span></span>  
 <span data-ttu-id="17c08-114">При использовании оператор `Inherits` должен быть первой непустой строкой, не являющейся комментарием, в определении класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17c08-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="17c08-115">Он должен следовать сразу за `Class` или инструкцией `Interface`.</span><span class="sxs-lookup"><span data-stu-id="17c08-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="17c08-116">@No__t_0 можно использовать только в классе или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="17c08-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="17c08-117">Это означает, что контекст объявления для наследования не может быть исходным файлом, пространством имен, структурой, модулем, процедурой или блоком.</span><span class="sxs-lookup"><span data-stu-id="17c08-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="17c08-118">Правила</span><span class="sxs-lookup"><span data-stu-id="17c08-118">Rules</span></span>  
  
- <span data-ttu-id="17c08-119">**Наследование класса.**</span><span class="sxs-lookup"><span data-stu-id="17c08-119">**Class Inheritance.**</span></span> <span data-ttu-id="17c08-120">Если класс использует инструкцию `Inherits`, можно указать только один базовый класс.</span><span class="sxs-lookup"><span data-stu-id="17c08-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="17c08-121">Класс не может наследовать от класса, вложенного в него.</span><span class="sxs-lookup"><span data-stu-id="17c08-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="17c08-122">**Наследование интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="17c08-122">**Interface Inheritance.**</span></span> <span data-ttu-id="17c08-123">Если интерфейс использует инструкцию `Inherits`, можно указать один или несколько базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="17c08-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="17c08-124">Можно наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="17c08-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="17c08-125">В этом случае реализующий код должен использовать уточнение имени, чтобы указать, какой член он реализует.</span><span class="sxs-lookup"><span data-stu-id="17c08-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="17c08-126">Интерфейс не может наследовать от другого интерфейса с более узким уровнем доступа.</span><span class="sxs-lookup"><span data-stu-id="17c08-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="17c08-127">Например, интерфейс `Public` не может наследовать от интерфейса `Friend`.</span><span class="sxs-lookup"><span data-stu-id="17c08-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="17c08-128">Интерфейс не может наследовать от вложенного в него интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17c08-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="17c08-129">Примером наследования класса в .NET Framework является класс <xref:System.ArgumentException>, который наследуется от класса <xref:System.SystemException>.</span><span class="sxs-lookup"><span data-stu-id="17c08-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="17c08-130">Это позволяет <xref:System.ArgumentException> все предопределенные свойства и процедуры, необходимые системным исключениям, такие как свойство <xref:System.Exception.Message%2A> и метод <xref:System.Exception.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="17c08-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="17c08-131">Примером наследования интерфейса в .NET Framework является интерфейс <xref:System.Collections.ICollection>, который наследуется от интерфейса <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="17c08-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="17c08-132">В результате <xref:System.Collections.ICollection> наследует определение перечислителя, необходимого для прохода по коллекции.</span><span class="sxs-lookup"><span data-stu-id="17c08-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17c08-133">Пример</span><span class="sxs-lookup"><span data-stu-id="17c08-133">Example</span></span>  
 <span data-ttu-id="17c08-134">В следующем примере используется оператор `Inherits`, чтобы продемонстрировать, как класс с именем `thisClass` может наследовать все члены базового класса с именем `anotherClass`.</span><span class="sxs-lookup"><span data-stu-id="17c08-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="17c08-135">Пример</span><span class="sxs-lookup"><span data-stu-id="17c08-135">Example</span></span>  
 <span data-ttu-id="17c08-136">В следующем примере показано наследование нескольких интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="17c08-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="17c08-137">Интерфейс с именем `thisInterface` теперь включает все определения в интерфейсах <xref:System.IComparable>, <xref:System.IDisposable> и <xref:System.IFormattable>. унаследованные члены предоставляют соответствующие типы для сравнения двух объектов, высвобождения выделенных ресурсов и выражения значения объект в качестве `String`.</span><span class="sxs-lookup"><span data-stu-id="17c08-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="17c08-138">Класс, реализующий `thisInterface`, должен реализовывать каждый член каждого базового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17c08-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c08-139">См. также</span><span class="sxs-lookup"><span data-stu-id="17c08-139">See also</span></span>

- [<span data-ttu-id="17c08-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="17c08-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="17c08-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="17c08-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="17c08-142">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="17c08-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="17c08-143">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="17c08-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="17c08-144">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="17c08-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
