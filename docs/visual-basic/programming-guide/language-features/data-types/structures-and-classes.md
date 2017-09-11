---
title: "Структуры и классы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures
- classes [Visual Basic]
- structures, compared to classes
- structures, structure variables
- structure variables
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c6874192a09db9ff5f247274247630d0bfa05ea3
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="13bf8-102">Структуры и классы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13bf8-102">Structures and Classes (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="13bf8-103">унифицирован синтаксис структур и классов, в результате чего обе сущности поддерживают большинство тех же функций.</span><span class="sxs-lookup"><span data-stu-id="13bf8-103"> unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="13bf8-104">Тем не менее существуют важные различия между структурами и классами.</span><span class="sxs-lookup"><span data-stu-id="13bf8-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="13bf8-105">Классы имеют преимущество ссылочных типов — ссылки более эффективна, чем передача переменной структуры с его данными.</span><span class="sxs-lookup"><span data-stu-id="13bf8-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="13bf8-106">С другой стороны структур не требуется выделение памяти в куче глобального.</span><span class="sxs-lookup"><span data-stu-id="13bf8-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="13bf8-107">Так как не может наследовать от структуры, структуры можно использовать только для объектов, которые не обязательно должны быть расширен.</span><span class="sxs-lookup"><span data-stu-id="13bf8-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="13bf8-108">Используйте структуры, если объект, который вы хотите создать экземпляр небольшой размер и принимать во внимание характеристики производительности классов и структур.</span><span class="sxs-lookup"><span data-stu-id="13bf8-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="13bf8-109">Сходство</span><span class="sxs-lookup"><span data-stu-id="13bf8-109">Similarities</span></span>  
 <span data-ttu-id="13bf8-110">Структуры и классы схожи в следующих отношениях:</span><span class="sxs-lookup"><span data-stu-id="13bf8-110">Structures and classes are similar in the following respects:</span></span>  
  
-   <span data-ttu-id="13bf8-111">Оба *контейнер* типов, то есть содержат другие типы в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="13bf8-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
-   <span data-ttu-id="13bf8-112">Оба имеют членов, включая конструкторы, методы, свойства, поля, константы, перечисления, события и обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="13bf8-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="13bf8-113">Однако не следует путать эти члены, объявленные с *элементы* структуры.</span><span class="sxs-lookup"><span data-stu-id="13bf8-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
-   <span data-ttu-id="13bf8-114">Их элементы могут иметь индивидуальные уровни доступа.</span><span class="sxs-lookup"><span data-stu-id="13bf8-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="13bf8-115">Например, может быть объявлен один член `Public` и другим `Private`.</span><span class="sxs-lookup"><span data-stu-id="13bf8-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
-   <span data-ttu-id="13bf8-116">Они могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="13bf8-116">Both can implement interfaces.</span></span>  
  
-   <span data-ttu-id="13bf8-117">Они имеют общие конструкторы с параметрами или без параметров.</span><span class="sxs-lookup"><span data-stu-id="13bf8-117">Both can have shared constructors, with or without parameters.</span></span>  
  
-   <span data-ttu-id="13bf8-118">Они могут предоставлять *по умолчанию свойство*, если это свойство принимает хотя бы один параметр.</span><span class="sxs-lookup"><span data-stu-id="13bf8-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
-   <span data-ttu-id="13bf8-119">Они могут объявлять и создавать события и могут объявлять делегаты.</span><span class="sxs-lookup"><span data-stu-id="13bf8-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="13bf8-120">Различия</span><span class="sxs-lookup"><span data-stu-id="13bf8-120">Differences</span></span>  
 <span data-ttu-id="13bf8-121">Структуры и классы отличаются следующими особенностями:</span><span class="sxs-lookup"><span data-stu-id="13bf8-121">Structures and classes differ in the following particulars:</span></span>  
  
-   <span data-ttu-id="13bf8-122">Структуры являются *типы значений*; классы являются *ссылочные типы*.</span><span class="sxs-lookup"><span data-stu-id="13bf8-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="13bf8-123">Переменная типа структуры содержит данные структуры, а чем содержащий ссылку на данные в виде типа класса.</span><span class="sxs-lookup"><span data-stu-id="13bf8-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
-   <span data-ttu-id="13bf8-124">Структуры используют расположение стека; классы используют память в куче.</span><span class="sxs-lookup"><span data-stu-id="13bf8-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
-   <span data-ttu-id="13bf8-125">Все элементы структуры, `Public` по умолчанию; класс переменные и константы- `Private` по умолчанию, а другие члены класса являются `Public` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="13bf8-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="13bf8-126">Такое поведение членов класса обеспечивает совместимость с системой Visual Basic 6.0, значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="13bf8-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
-   <span data-ttu-id="13bf8-127">Структуры должны иметь по крайней мере один не совместно переменную или без общего доступа элемента события; класс может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="13bf8-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
-   <span data-ttu-id="13bf8-128">Элементы структуры не могут объявляться как `Protected`; члены класса могут.</span><span class="sxs-lookup"><span data-stu-id="13bf8-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
-   <span data-ttu-id="13bf8-129">Процедура структуры может обрабатывать события только в том случае, если это [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` процедура и только с помощью параметра [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md); любая процедура класса может обработать событие, используя либо [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) ключевое слово или `AddHandler` инструкции.</span><span class="sxs-lookup"><span data-stu-id="13bf8-129">A structure procedure can handle events only if it is a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="13bf8-130">Дополнительные сведения см. в разделе [события](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="13bf8-130">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
-   <span data-ttu-id="13bf8-131">Объявления переменных структуры нельзя указать инициализаторы или исходные размеры массивов; возможность объявления переменных класса.</span><span class="sxs-lookup"><span data-stu-id="13bf8-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
-   <span data-ttu-id="13bf8-132">Структуры неявно наследуют от <xref:System.ValueType?displayProperty=fullName>класса и не может наследоваться от любого другого типа; классы могут наследовать от любых классов, отличных от <xref:System.ValueType?displayProperty=fullName>.</xref:System.ValueType?displayProperty=fullName> </xref:System.ValueType?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="13bf8-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=fullName> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=fullName>.</span></span>  
  
-   <span data-ttu-id="13bf8-133">Структуры не наследуются; классы являются.</span><span class="sxs-lookup"><span data-stu-id="13bf8-133">Structures are not inheritable; classes are.</span></span>  
  
-   <span data-ttu-id="13bf8-134">Структуры никогда не завершаются, поэтому общеязыковой среды выполнения (CLR) никогда не вызывает <xref:System.Object.Finalize%2A>метод для структур; классы завершаются сборщиком мусора (GC), который вызывает <xref:System.Object.Finalize%2A>для класса, когда обнаруживает, что не осталось активных ссылок.</xref:System.Object.Finalize%2A> </xref:System.Object.Finalize%2A></span><span class="sxs-lookup"><span data-stu-id="13bf8-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
-   <span data-ttu-id="13bf8-135">Структуры не требуется конструктор; для класса требуется.</span><span class="sxs-lookup"><span data-stu-id="13bf8-135">A structure does not require a constructor; a class does.</span></span>  
  
-   <span data-ttu-id="13bf8-136">Структуры могут иметь не общие конструкторы, только если они принимают параметры; классы могут иметь их с параметрами или без параметров.</span><span class="sxs-lookup"><span data-stu-id="13bf8-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="13bf8-137">Каждая структура имеет неявный открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="13bf8-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="13bf8-138">Этот конструктор инициализирует элементы структуры данных к значениям по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="13bf8-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="13bf8-139">Не удалось переопределить это поведение.</span><span class="sxs-lookup"><span data-stu-id="13bf8-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="13bf8-140">Экземпляры и переменные</span><span class="sxs-lookup"><span data-stu-id="13bf8-140">Instances and Variables</span></span>  
 <span data-ttu-id="13bf8-141">Поскольку структуры являются типами значений, каждая переменная структуры постоянно привязана к отдельному экземпляру структуры.</span><span class="sxs-lookup"><span data-stu-id="13bf8-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="13bf8-142">Классы являются ссылочными типами, и переменная объекта может ссылаться на различные экземпляры класса в разное время.</span><span class="sxs-lookup"><span data-stu-id="13bf8-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="13bf8-143">Это различие влияет на использование структур и классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="13bf8-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
-   <span data-ttu-id="13bf8-144">**Инициализация.**</span><span class="sxs-lookup"><span data-stu-id="13bf8-144">**Initialization.**</span></span> <span data-ttu-id="13bf8-145">Переменная структуры неявно содержит инициализацию элементов с помощью структуры конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="13bf8-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="13bf8-146">Таким образом `Dim s As struct1` эквивалентно `Dim s As struct1 = New struct1()`.</span><span class="sxs-lookup"><span data-stu-id="13bf8-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
-   <span data-ttu-id="13bf8-147">**Присваивание переменных.**</span><span class="sxs-lookup"><span data-stu-id="13bf8-147">**Assigning Variables.**</span></span> <span data-ttu-id="13bf8-148">Когда одна переменная структуры присваивается другой или экземпляр структуры передается в аргумент процедуры, текущие значения всех элементов переменной копируются в новую структуру.</span><span class="sxs-lookup"><span data-stu-id="13bf8-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="13bf8-149">Когда переменная объекта присваивается другой или передается в процедуру, копируется только указатель ссылки.</span><span class="sxs-lookup"><span data-stu-id="13bf8-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
-   <span data-ttu-id="13bf8-150">**Назначение ничего.**</span><span class="sxs-lookup"><span data-stu-id="13bf8-150">**Assigning Nothing.**</span></span> <span data-ttu-id="13bf8-151">Можно назначить значение [ничего](../../../../visual-basic/language-reference/nothing.md) в структуру переменной, но экземпляр продолжает оставаться связанным с переменной.</span><span class="sxs-lookup"><span data-stu-id="13bf8-151">You can assign the value [Nothing](../../../../visual-basic/language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="13bf8-152">Можно по-прежнему вызывать его методы и доступ к ее элементам данных, хотя элементы переменной заново инициализируются назначением.</span><span class="sxs-lookup"><span data-stu-id="13bf8-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="13bf8-153">Напротив, если задано значение переменной объекта `Nothing`, она не связана ни с каким экземпляром класса и доступ к любым элементам через переменную невозможно, пока не будет присвоен другой экземпляр.</span><span class="sxs-lookup"><span data-stu-id="13bf8-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
-   <span data-ttu-id="13bf8-154">**Несколько экземпляров.**</span><span class="sxs-lookup"><span data-stu-id="13bf8-154">**Multiple Instances.**</span></span> <span data-ttu-id="13bf8-155">Переменной объекта может иметь разные экземпляры класса назначены в различные моменты времени, и несколько переменных объекта может ссылаться на один экземпляр класса в то же время.</span><span class="sxs-lookup"><span data-stu-id="13bf8-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="13bf8-156">Изменения, внесенные в значения членов класса, влияют на эти члены при доступе через другую переменную, указывающую на тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="13bf8-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="13bf8-157">Элементы структуры изолированы в пределах своего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="13bf8-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="13bf8-158">Изменения в их значения не отражаются в любой других переменных структуры, даже в других экземплярах того же `Structure` объявления.</span><span class="sxs-lookup"><span data-stu-id="13bf8-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
-   <span data-ttu-id="13bf8-159">**Проверки на равенство.**</span><span class="sxs-lookup"><span data-stu-id="13bf8-159">**Equality.**</span></span> <span data-ttu-id="13bf8-160">Проверки равенства двух структур должна выполняться с параметром-элемент теста.</span><span class="sxs-lookup"><span data-stu-id="13bf8-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="13bf8-161">Две переменные объекта могут сравниваться с помощью <xref:System.Object.Equals%2A>метод.</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="13bf8-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="13bf8-162"><xref:System.Object.Equals%2A>Определяет, указывают ли две переменные на один экземпляр.</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="13bf8-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13bf8-163">См. также</span><span class="sxs-lookup"><span data-stu-id="13bf8-163">See Also</span></span>  
 <span data-ttu-id="13bf8-164">[Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="13bf8-164">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="13bf8-165"> [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="13bf8-165"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="13bf8-166"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="13bf8-166"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="13bf8-167"> [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="13bf8-167"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="13bf8-168"> [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="13bf8-168"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="13bf8-169"> [Структуры и другие элементы программирования](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span><span class="sxs-lookup"><span data-stu-id="13bf8-169"> [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span></span>  
<span data-ttu-id="13bf8-170"> [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="13bf8-170"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>
