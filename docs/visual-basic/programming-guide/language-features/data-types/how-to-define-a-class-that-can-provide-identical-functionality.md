---
title: Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: d80623d9e55358d37aa45f11f1525c80a09b91a6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350043"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a><span data-ttu-id="0a9f2-102">Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a9f2-102">How to: Define a Class That Can Provide Identical Functionality on Different Data Types (Visual Basic)</span></span>
<span data-ttu-id="0a9f2-103">Можно определить класс, из которого можно создавать объекты, обеспечивающие одинаковые функциональные возможности для различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-103">You can define a class from which you can create objects that provide identical functionality on different data types.</span></span> <span data-ttu-id="0a9f2-104">Для этого укажите в определении один или несколько *параметров типа* .</span><span class="sxs-lookup"><span data-stu-id="0a9f2-104">To do this, you specify one or more *type parameters* in the definition.</span></span> <span data-ttu-id="0a9f2-105">После этого класс может служить шаблоном для объектов, которые используют различные типы данных.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-105">The class can then serve as a template for objects that use various data types.</span></span> <span data-ttu-id="0a9f2-106">Класс, определенный таким образом, называется *универсальным классом*.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-106">A class defined in this way is called a *generic class*.</span></span>  
  
 <span data-ttu-id="0a9f2-107">Преимущество определения универсального класса состоит в том, он определяется только один раз, и код может использовать его для создания многих объектов, использующих разнообразные типы данных.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-107">The advantage of defining a generic class is that you define it just once, and your code can use it to create many objects that use a wide variety of data types.</span></span> <span data-ttu-id="0a9f2-108">Это дает более высокую производительность, чем при определении класса с помощью типа `Object` .</span><span class="sxs-lookup"><span data-stu-id="0a9f2-108">This results in better performance than defining the class with the `Object` type.</span></span>  
  
 <span data-ttu-id="0a9f2-109">Помимо классов, можно определять и использовать универсальные структуры, интерфейсы, процедуры и делегаты.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-109">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
### <a name="to-define-a-class-with-a-type-parameter"></a><span data-ttu-id="0a9f2-110">Определение класса с помощью параметра типа</span><span class="sxs-lookup"><span data-stu-id="0a9f2-110">To define a class with a type parameter</span></span>  
  
1. <span data-ttu-id="0a9f2-111">Определите класс обычным способом.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-111">Define the class in the normal way.</span></span>  
  
2. <span data-ttu-id="0a9f2-112">Добавьте `(Of` *typeparameter*`)` сразу после имени класса для указания параметра типа.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-112">Add `(Of` *typeparameter*`)` immediately after the class name to specify a type parameter.</span></span>  
  
3. <span data-ttu-id="0a9f2-113">Если имеется более одного параметра типа, создайте разделенный запятыми список, заключенный в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-113">If you have more than one type parameter, make a comma-separated list inside the parentheses.</span></span> <span data-ttu-id="0a9f2-114">Не следует повторять ключевое слово `Of` .</span><span class="sxs-lookup"><span data-stu-id="0a9f2-114">Do not repeat the `Of` keyword.</span></span>  
  
4. <span data-ttu-id="0a9f2-115">Если код выполняет с параметром типа какие-либо операции, отличные от простого присваивания, следует записать данный параметр типа с условием `As` для добавления одного или нескольких *ограничений*.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-115">If your code performs operations on a type parameter other than simple assignment, follow that type parameter with an `As` clause to add one or more *constraints*.</span></span> <span data-ttu-id="0a9f2-116">Ограничение гарантирует, что тип, указанный для данного параметра типа, удовлетворяет определенным требованиям:</span><span class="sxs-lookup"><span data-stu-id="0a9f2-116">A constraint guarantees that the type supplied for that type parameter satisfies a requirement such as the following:</span></span>  
  
    - <span data-ttu-id="0a9f2-117">Поддерживает операции, например `>`, которые выполняются кодом.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-117">Supports an operation, such as `>`, that your code performs</span></span>  
  
    - <span data-ttu-id="0a9f2-118">Поддерживает элементы, например методы, к которым обращается код.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-118">Supports a member, such as a method, that your code accesses</span></span>  
  
    - <span data-ttu-id="0a9f2-119">Предоставляет конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-119">Exposes a parameterless constructor</span></span>  
  
     <span data-ttu-id="0a9f2-120">Если не указаны никакие ограничения, код сможет использовать только операции и элементы, поддерживаемые [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="0a9f2-120">If you do not specify any constraints, the only operations and members your code can use are those supported by the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="0a9f2-121">Дополнительные сведения см. в разделе [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="0a9f2-121">For more information, see [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
5. <span data-ttu-id="0a9f2-122">Определите все элементы класса, объявляемые с помощью указанного типа, и объявите их `As` `typeparameter`.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-122">Identify every class member that is to be declared with a supplied type, and declare it `As` `typeparameter`.</span></span> <span data-ttu-id="0a9f2-123">Это относится к внутреннему хранилищу, параметрам процедур и возвращаемым значениям.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-123">This applies to internal storage, procedure parameters, and return values.</span></span>  
  
6. <span data-ttu-id="0a9f2-124">Убедитесь, что код использует только операции и методы, поддерживаемые типом данных, который может быть предоставлен для `itemType`.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-124">Be sure your code uses only operations and methods that are supported by any data type it can supply to `itemType`.</span></span>  
  
     <span data-ttu-id="0a9f2-125">В следующем примере определяется класс, управляющий простым списком.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-125">The following example defines a class that manages a very simple list.</span></span> <span data-ttu-id="0a9f2-126">Он хранит список во внутреннем массиве `items`, и использующий код может объявить тип данных элементов списка.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-126">It holds the list in the internal array `items`, and the using code can declare the data type of the list elements.</span></span> <span data-ttu-id="0a9f2-127">A parameterized constructor allows the using code to set the upper bound of `items`, and the parameterless constructor sets this to 9 (for a total of 10 items).</span><span class="sxs-lookup"><span data-stu-id="0a9f2-127">A parameterized constructor allows the using code to set the upper bound of `items`, and the parameterless constructor sets this to 9 (for a total of 10 items).</span></span>  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     <span data-ttu-id="0a9f2-128">Можно объявить один класс из `simpleList` для хранения списка значений `Integer` , другой класс — для хранения списка значений `String` и еще один — для хранения значений `Date` .</span><span class="sxs-lookup"><span data-stu-id="0a9f2-128">You can declare a class from `simpleList` to hold a list of `Integer` values, another class to hold a list of `String` values, and another to hold `Date` values.</span></span> <span data-ttu-id="0a9f2-129">Кроме типа данных элементов списка, объекты, созданные из всех этих классов, ведут себя одинаково.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-129">Except for the data type of the list members, objects created from all these classes behave identically.</span></span>  
  
     <span data-ttu-id="0a9f2-130">Аргумент типа, который использующий код указывает для `itemType` , может быть встроенным типом, например `Boolean` или `Double`, структурой, перечислением или любым типом класса, включая определяемый приложением.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-130">The type argument that the using code supplies to `itemType` can be an intrinsic type such as `Boolean` or `Double`, a structure, an enumeration, or any type of class, including one that your application defines.</span></span>  
  
     <span data-ttu-id="0a9f2-131">Можно протестировать класс `simpleList` с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="0a9f2-131">You can test the class `simpleList` with the following code.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="0a9f2-132">См. также</span><span class="sxs-lookup"><span data-stu-id="0a9f2-132">See also</span></span>

- [<span data-ttu-id="0a9f2-133">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0a9f2-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="0a9f2-134">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a9f2-134">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0a9f2-135">Независимость от языка и независимые от языка компоненты</span><span class="sxs-lookup"><span data-stu-id="0a9f2-135">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="0a9f2-136">Of</span><span class="sxs-lookup"><span data-stu-id="0a9f2-136">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="0a9f2-137">Список типов</span><span class="sxs-lookup"><span data-stu-id="0a9f2-137">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="0a9f2-138">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="0a9f2-138">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="0a9f2-139">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="0a9f2-139">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
