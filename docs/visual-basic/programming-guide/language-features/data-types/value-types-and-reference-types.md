---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504879"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="d0cf7-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="d0cf7-102">Value Types and Reference Types</span></span>
<span data-ttu-id="d0cf7-103">Существуют две разновидности типов в Visual Basic: ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="d0cf7-104">В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="d0cf7-105">Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="d0cf7-106">Типы значений, каждая переменная имеет собственную копию данных, и он не поддерживается для операций над одной переменной могут затрагивать другую (за исключением в случае использования [ByRef модификатор параметров](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="d0cf7-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="d0cf7-107">Типы значений</span><span class="sxs-lookup"><span data-stu-id="d0cf7-107">Value Types</span></span>  
 <span data-ttu-id="d0cf7-108">Тип данных является *тип значения* если он содержит данные в пределах своей собственной памяти.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="d0cf7-109">Ниже приведены типы значений:</span><span class="sxs-lookup"><span data-stu-id="d0cf7-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="d0cf7-110">Все числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="d0cf7-110">All numeric data types</span></span>  
  
- <span data-ttu-id="d0cf7-111">`Boolean`, `Char`и `Date`</span><span class="sxs-lookup"><span data-stu-id="d0cf7-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="d0cf7-112">Все структуры, даже если их элементы являются ссылочными типами</span><span class="sxs-lookup"><span data-stu-id="d0cf7-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="d0cf7-113">Перечисления, поскольку их базовый тип всегда является `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, или `ULong`</span><span class="sxs-lookup"><span data-stu-id="d0cf7-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="d0cf7-114">Каждая структура является типом значения, даже если он содержит члены ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="d0cf7-115">По этой причине значение типы, такие как `Char` и `Integer` реализуются структуры .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="d0cf7-116">Можно объявить тип значения с помощью зарезервированного ключевого слова, например, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="d0cf7-117">Можно также использовать `New` ключевое слово для инициализации типа значения.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="d0cf7-118">Это особенно полезно в том случае, если тип имеет конструктор, принимающий параметры.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="d0cf7-119">Примером этого является <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> конструктор, который создает новый `Decimal` значение из предоставленных частей.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="d0cf7-120">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="d0cf7-120">Reference Types</span></span>  
 <span data-ttu-id="d0cf7-121">Объект *ссылочный тип* хранит ссылку на его данные.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="d0cf7-122">Ссылочные типы включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="d0cf7-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="d0cf7-123">Все массивы, даже в том случае, если их элементы являются типами значений</span><span class="sxs-lookup"><span data-stu-id="d0cf7-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="d0cf7-124">Типы классов, такие как <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="d0cf7-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="d0cf7-125">Делегаты</span><span class="sxs-lookup"><span data-stu-id="d0cf7-125">Delegates</span></span>  
  
 <span data-ttu-id="d0cf7-126">Класс является *ссылочный тип*.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-126">A class is a *reference type*.</span></span> <span data-ttu-id="d0cf7-127">Обратите внимание на то, что каждый массив является ссылочным типом, даже если его члены являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="d0cf7-128">Так как каждый ссылочный тип представляет собой соответствующий класс .NET Framework, необходимо использовать [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово для его инициализации.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="d0cf7-129">Следующая инструкция инициализирует массив.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="d0cf7-130">Элементы, которые не являются типами</span><span class="sxs-lookup"><span data-stu-id="d0cf7-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="d0cf7-131">Следующие элементы программирования не могут считаться типов, так как нельзя указать любой из них как тип данных для объявленного элемента:</span><span class="sxs-lookup"><span data-stu-id="d0cf7-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="d0cf7-132">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="d0cf7-132">Namespaces</span></span>  
  
- <span data-ttu-id="d0cf7-133">Модули</span><span class="sxs-lookup"><span data-stu-id="d0cf7-133">Modules</span></span>  
  
- <span data-ttu-id="d0cf7-134">События</span><span class="sxs-lookup"><span data-stu-id="d0cf7-134">Events</span></span>  
  
- <span data-ttu-id="d0cf7-135">Свойства и процедуры</span><span class="sxs-lookup"><span data-stu-id="d0cf7-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="d0cf7-136">Переменные, константы и поля</span><span class="sxs-lookup"><span data-stu-id="d0cf7-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="d0cf7-137">Работа с типом данных объекта</span><span class="sxs-lookup"><span data-stu-id="d0cf7-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="d0cf7-138">Можно назначить переменной ссылочным типом или типом значения `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="d0cf7-139">`Object` Переменная не всегда ссылается на данные, а не сами данные.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="d0cf7-140">Однако если присвоить тип значения для `Object` переменной, он действует так, будто он хранит собственные данные.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="d0cf7-141">Дополнительные сведения см. в разделе [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d0cf7-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="d0cf7-142">Вы можете выяснить, был ли `Object` переменная используется в качестве ссылочным типом или типом значения, передав его в <xref:Microsoft.VisualBasic.Information.IsReference%2A> метод в <xref:Microsoft.VisualBasic.Information> класс <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d0cf7-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Возвращает `True` Если содержание `Object` переменная представляет ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0cf7-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d0cf7-144">See also</span></span>

- [<span data-ttu-id="d0cf7-145">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="d0cf7-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="d0cf7-146">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d0cf7-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="d0cf7-147">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="d0cf7-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="d0cf7-148">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="d0cf7-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="d0cf7-149">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="d0cf7-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d0cf7-150">Типы данных</span><span class="sxs-lookup"><span data-stu-id="d0cf7-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
