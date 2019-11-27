---
title: Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 89a39e8e9cd66b1d774da70be47c7c6824cccef2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350027"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a><span data-ttu-id="c7421-102">Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7421-102">How to: Infer Property Names and Types in Anonymous Type Declarations (Visual Basic)</span></span>

<span data-ttu-id="c7421-103">Анонимные типы не предоставляют механизм для прямого указания типов данных для свойств.</span><span class="sxs-lookup"><span data-stu-id="c7421-103">Anonymous types provide no mechanism for directly specifying the data types of properties.</span></span> <span data-ttu-id="c7421-104">Типы всех свойств определяются посредством вывода.</span><span class="sxs-lookup"><span data-stu-id="c7421-104">Types of all properties are inferred.</span></span> <span data-ttu-id="c7421-105">В следующем примере типы `Name` и `Price` выводятся напрямую из значений, которые используются для их инициализации.</span><span class="sxs-lookup"><span data-stu-id="c7421-105">In the following example, the types of `Name` and `Price` are inferred directly from the values that are used to initialize them.</span></span>

[!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]

<span data-ttu-id="c7421-106">Анонимные типы также могут выводить имена и типы свойств из других источников.</span><span class="sxs-lookup"><span data-stu-id="c7421-106">Anonymous types can also infer property names and types from other sources.</span></span> <span data-ttu-id="c7421-107">В последующих разделах представлен список ситуаций, где вывод возможен, и примеры обратных ситуаций.</span><span class="sxs-lookup"><span data-stu-id="c7421-107">The sections that follow provide a list of the circumstances where inference is possible, and examples of situations where it is not.</span></span>

## <a name="successful-inference"></a><span data-ttu-id="c7421-108">Успешный вывод</span><span class="sxs-lookup"><span data-stu-id="c7421-108">Successful Inference</span></span>

#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a><span data-ttu-id="c7421-109">Анонимные типы могут выводить имена и типы свойств из следующих источников.</span><span class="sxs-lookup"><span data-stu-id="c7421-109">Anonymous types can infer property names and types from the following sources:</span></span>

- <span data-ttu-id="c7421-110">Из имен переменных.</span><span class="sxs-lookup"><span data-stu-id="c7421-110">From variable names.</span></span> <span data-ttu-id="c7421-111">Анонимный тип `anonProduct` будет иметь два свойства: `productName` и `productPrice`.</span><span class="sxs-lookup"><span data-stu-id="c7421-111">Anonymous type `anonProduct` will have two properties, `productName` and `productPrice`.</span></span> <span data-ttu-id="c7421-112">Их типами данных будут типы исходных переменных, `String` и `Double`соответственно.</span><span class="sxs-lookup"><span data-stu-id="c7421-112">Their data types will be those of the original variables, `String` and `Double`, respectively.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]

- <span data-ttu-id="c7421-113">Из имен свойств или полей других объектов.</span><span class="sxs-lookup"><span data-stu-id="c7421-113">From property or field names of other objects.</span></span> <span data-ttu-id="c7421-114">Например, рассмотрим объект `car` типа `CarClass` , включающий свойства `Name` и `ID` .</span><span class="sxs-lookup"><span data-stu-id="c7421-114">For example, consider a `car` object of a `CarClass` type that includes `Name` and `ID` properties.</span></span> <span data-ttu-id="c7421-115">Чтобы создать новый экземпляр анонимного типа `car1`со свойствами `Name` и `ID` , которые инициализируются значениями из объекта `car` , можно написать следующее.</span><span class="sxs-lookup"><span data-stu-id="c7421-115">To create a new anonymous type instance, `car1`, with `Name` and `ID` properties that are initialized with the values from the `car` object, you can write the following:</span></span>

  [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]

  <span data-ttu-id="c7421-116">Предыдущее объявление эквивалентно большей строке кода, определяющей анонимный тип `car2`.</span><span class="sxs-lookup"><span data-stu-id="c7421-116">The previous declaration is equivalent to the longer line of code that defines anonymous type `car2`.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]

- <span data-ttu-id="c7421-117">Из имен элементов XML</span><span class="sxs-lookup"><span data-stu-id="c7421-117">From XML member names.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]

  <span data-ttu-id="c7421-118">Результирующий тип для `anon` будет иметь одно свойство `Book`c типом <xref:System.Collections.IEnumerable>(XElement).</span><span class="sxs-lookup"><span data-stu-id="c7421-118">The resulting type for `anon` would have one property, `Book`, of type <xref:System.Collections.IEnumerable>(Of XElement).</span></span>

- <span data-ttu-id="c7421-119">Из функции, которая не имеет параметров, например `SomeFunction` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c7421-119">From a function that has no parameters, such as `SomeFunction` in the following example.</span></span>

  ```vb
  Dim sc As New SomeClass
  Dim anon1 = New With {Key sc.SomeFunction()}
  ```

  <span data-ttu-id="c7421-120">Переменная `anon2` в следующем коде является анонимным типом, который имеет одно свойство: знак с именем `First`.</span><span class="sxs-lookup"><span data-stu-id="c7421-120">The variable `anon2` in the following code is an anonymous type that has one property, a character named `First`.</span></span> <span data-ttu-id="c7421-121">Этот код будет отображать букву E — букву, которая возвращена функцией <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7421-121">This code will display a letter "E," the letter that is returned by function <xref:System.Linq.Enumerable.First%2A>.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]

## <a name="inference-failures"></a><span data-ttu-id="c7421-122">Неудачный вывод</span><span class="sxs-lookup"><span data-stu-id="c7421-122">Inference Failures</span></span>

#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a><span data-ttu-id="c7421-123">Вывод имени завершится сбоем во многих случаях, в том числе в следующих.</span><span class="sxs-lookup"><span data-stu-id="c7421-123">Name inference will fail in many circumstances, including the following:</span></span>

- <span data-ttu-id="c7421-124">Вывод является производным от вызова метода, конструктора или параметризованного свойства, для которого требуются аргументы.</span><span class="sxs-lookup"><span data-stu-id="c7421-124">The inference derives from the invocation of a method, a constructor, or a parameterized property that requires arguments.</span></span> <span data-ttu-id="c7421-125">Предыдущее объявление `anon1` завершается сбоем, если `someFunction` имеет один или несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="c7421-125">The previous declaration of `anon1` fails if `someFunction` has one or more arguments.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon3 = New With {Key sc.someFunction(someArg)}
  ```

  <span data-ttu-id="c7421-126">Проблема решается путем назначения новому имени свойства.</span><span class="sxs-lookup"><span data-stu-id="c7421-126">Assignment to a new property name solves the problem.</span></span>

  ```vb
  ' Valid.
  Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}
  ```

- <span data-ttu-id="c7421-127">Вывод является производным от сложного выражения.</span><span class="sxs-lookup"><span data-stu-id="c7421-127">The inference derives from a complex expression.</span></span>

  ```vb
  Dim aString As String = "Act "
  ' Not valid.
  ' Dim label = New With {Key aString & "IV"}
  ```

  <span data-ttu-id="c7421-128">Ошибку можно устранить, назначив результат выражения для имени свойства.</span><span class="sxs-lookup"><span data-stu-id="c7421-128">The error can be resolved by assigning the result of the expression to a property name.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]

- <span data-ttu-id="c7421-129">Вывод нескольких свойств создает два или более свойств с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="c7421-129">Inference for multiple properties produces two or more properties that have the same name.</span></span> <span data-ttu-id="c7421-130">Возвращаясь к объявлениям в предыдущих примерах, невозможно указывать `product.Name` и `car1.Name` в качестве свойств для одного анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="c7421-130">Referring back to declarations in earlier examples, you cannot list both `product.Name` and `car1.Name` as properties of the same anonymous type.</span></span> <span data-ttu-id="c7421-131">Это связано с тем, что выводимый идентификатор для каждого из них будет `Name`.</span><span class="sxs-lookup"><span data-stu-id="c7421-131">This is because the inferred identifier for each of these would be `Name`.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon5 = New With {Key product.Name, Key car1.Name}
  ```

  <span data-ttu-id="c7421-132">Проблему можно решить, назначив значения уникальным именам свойств.</span><span class="sxs-lookup"><span data-stu-id="c7421-132">The problem can be solved by assigning the values to distinct property names.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]

  <span data-ttu-id="c7421-133">Обратите внимание, что изменение регистра (изменение прописных букв на строчные и наоборот) не делает имя уникальным.</span><span class="sxs-lookup"><span data-stu-id="c7421-133">Note that changes in case (changes between uppercase and lowercase letters) do not make two names distinct.</span></span>

  ```vb
  Dim price = 0
  ' Not valid, because Price and price are the same name.
  ' Dim anon7 = New With {Key product.Price, Key price}
  ```

- <span data-ttu-id="c7421-134">Исходные тип и значение одного свойства зависят от другого свойства, которое еще не установлено.</span><span class="sxs-lookup"><span data-stu-id="c7421-134">The initial type and value of one property depends on another property that is not yet established.</span></span> <span data-ttu-id="c7421-135">Например, `.IDName = .LastName` не является допустимым в объявлении анонимного типа, если только `.LastName` уже не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="c7421-135">For example, `.IDName = .LastName` is not valid in an anonymous type declaration unless `.LastName` is already initialized.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}
  ```

  <span data-ttu-id="c7421-136">В этом примере проблему можно устранить, изменив порядок, в котором объявлены свойства, на обратный.</span><span class="sxs-lookup"><span data-stu-id="c7421-136">In this example, you can fix the problem by reversing the order in which the properties are declared.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]

- <span data-ttu-id="c7421-137">Имя свойства анонимного типа совпадает с именем элемента <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c7421-137">A property name of the anonymous type is the same as the name of a member of <xref:System.Object>.</span></span> <span data-ttu-id="c7421-138">Например, следующее объявление завершится сбоем, так как `Equals` — это метод <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c7421-138">For example, the following declaration fails because `Equals` is a method of <xref:System.Object>.</span></span>

  ```vb
  ' Not valid.
  ' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _
  '                       "greater than", Key .Less = "less than"}
  ```

  <span data-ttu-id="c7421-139">Проблему можно устранить, изменив имя свойства:</span><span class="sxs-lookup"><span data-stu-id="c7421-139">You can fix the problem by changing the property name:</span></span>

  [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]

## <a name="see-also"></a><span data-ttu-id="c7421-140">См. также</span><span class="sxs-lookup"><span data-stu-id="c7421-140">See also</span></span>

- [<span data-ttu-id="c7421-141">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="c7421-141">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="c7421-142">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="c7421-142">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="c7421-143">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="c7421-143">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="c7421-144">Key</span><span class="sxs-lookup"><span data-stu-id="c7421-144">Key</span></span>](../../../../visual-basic/language-reference/modifiers/key.md)
