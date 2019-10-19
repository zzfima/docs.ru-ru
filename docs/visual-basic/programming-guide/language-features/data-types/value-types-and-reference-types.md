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
ms.openlocfilehash: 466bb5386235917705344d35c5141c8bf779218d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582645"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="7cad6-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="7cad6-102">Value Types and Reference Types</span></span>
<span data-ttu-id="7cad6-103">В Visual Basic есть два типа типов: ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="7cad6-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="7cad6-104">В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно.</span><span class="sxs-lookup"><span data-stu-id="7cad6-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="7cad6-105">Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="7cad6-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="7cad6-106">В случае с типами значений каждая переменная имеет собственную копию данных, и операции с одной переменной не могут влиять на другую (за исключением [модификатора ByRef в параметрах](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="7cad6-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="7cad6-107">Типы значений</span><span class="sxs-lookup"><span data-stu-id="7cad6-107">Value Types</span></span>  
 <span data-ttu-id="7cad6-108">Тип данных — это *тип значения* , если он содержит данные в пределах отдельного выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="7cad6-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="7cad6-109">К типам значений относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="7cad6-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="7cad6-110">Все числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="7cad6-110">All numeric data types</span></span>  
  
- <span data-ttu-id="7cad6-111">`Boolean`, `Char` и `Date`</span><span class="sxs-lookup"><span data-stu-id="7cad6-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="7cad6-112">Все структуры, даже если их члены являются ссылочными типами</span><span class="sxs-lookup"><span data-stu-id="7cad6-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="7cad6-113">Перечисления, так как их базовый тип всегда `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` или `ULong`</span><span class="sxs-lookup"><span data-stu-id="7cad6-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="7cad6-114">Каждая структура является типом значения, даже если она содержит члены ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="7cad6-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="7cad6-115">По этой причине типы значений, такие как `Char` и `Integer`, реализуются структурами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7cad6-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="7cad6-116">Тип значения можно объявить с помощью зарезервированного ключевого слова, например `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="7cad6-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="7cad6-117">Для инициализации типа значения можно также использовать ключевое слово `New`.</span><span class="sxs-lookup"><span data-stu-id="7cad6-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="7cad6-118">Это особенно полезно, если тип имеет конструктор, принимающий параметры.</span><span class="sxs-lookup"><span data-stu-id="7cad6-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="7cad6-119">Примером этого является конструктор <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>, который создает новое значение `Decimal` из предоставляемых частей.</span><span class="sxs-lookup"><span data-stu-id="7cad6-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="7cad6-120">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="7cad6-120">Reference Types</span></span>  
 <span data-ttu-id="7cad6-121">*Ссылочный тип* хранит ссылку на свои данные.</span><span class="sxs-lookup"><span data-stu-id="7cad6-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="7cad6-122">К ссылочным типам относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="7cad6-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="7cad6-123">Все массивы, даже если их элементы являются типами значений</span><span class="sxs-lookup"><span data-stu-id="7cad6-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="7cad6-124">Типы классов, например <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="7cad6-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="7cad6-125">Делегаты</span><span class="sxs-lookup"><span data-stu-id="7cad6-125">Delegates</span></span>  
  
 <span data-ttu-id="7cad6-126">Класс является *ссылочным типом*.</span><span class="sxs-lookup"><span data-stu-id="7cad6-126">A class is a *reference type*.</span></span> <span data-ttu-id="7cad6-127">Обратите внимание, что каждый массив является ссылочным типом, даже если его члены являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="7cad6-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="7cad6-128">Поскольку каждый ссылочный тип представляет базовый класс .NET Framework, при его инициализации необходимо использовать ключевое слово [New operator](../../../../visual-basic/language-reference/operators/new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="7cad6-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="7cad6-129">Следующая инструкция инициализирует массив.</span><span class="sxs-lookup"><span data-stu-id="7cad6-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="7cad6-130">Элементы, не являющиеся типами</span><span class="sxs-lookup"><span data-stu-id="7cad6-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="7cad6-131">Следующие элементы программирования не являются типами, так как их нельзя указать в качестве типа данных для объявленного элемента:</span><span class="sxs-lookup"><span data-stu-id="7cad6-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="7cad6-132">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="7cad6-132">Namespaces</span></span>  
  
- <span data-ttu-id="7cad6-133">Модули</span><span class="sxs-lookup"><span data-stu-id="7cad6-133">Modules</span></span>  
  
- <span data-ttu-id="7cad6-134">события</span><span class="sxs-lookup"><span data-stu-id="7cad6-134">Events</span></span>  
  
- <span data-ttu-id="7cad6-135">Свойства и процедуры</span><span class="sxs-lookup"><span data-stu-id="7cad6-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="7cad6-136">Переменные, константы и поля</span><span class="sxs-lookup"><span data-stu-id="7cad6-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="7cad6-137">Работа с типом данных Object</span><span class="sxs-lookup"><span data-stu-id="7cad6-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="7cad6-138">Переменной `Object` типа данных можно назначить либо ссылочный тип, либо тип значения.</span><span class="sxs-lookup"><span data-stu-id="7cad6-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="7cad6-139">Переменная `Object` всегда содержит ссылку на данные, а не сами данные.</span><span class="sxs-lookup"><span data-stu-id="7cad6-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="7cad6-140">Однако если присвоить тип значения переменной `Object`, она ведет себя так, как если бы она содержала собственные данные.</span><span class="sxs-lookup"><span data-stu-id="7cad6-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="7cad6-141">Дополнительные сведения см. в разделе [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="7cad6-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="7cad6-142">Определить, действует ли `Object`ая переменная как ссылочный тип или тип значения, можно, передав его методу <xref:Microsoft.VisualBasic.Information.IsReference%2A> в классе <xref:Microsoft.VisualBasic.Information> пространства имен <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7cad6-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="7cad6-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> возвращает `True`, если содержимое переменной `Object` представляет ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="7cad6-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cad6-144">См. также</span><span class="sxs-lookup"><span data-stu-id="7cad6-144">See also</span></span>

- [<span data-ttu-id="7cad6-145">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="7cad6-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="7cad6-146">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7cad6-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="7cad6-147">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="7cad6-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="7cad6-148">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="7cad6-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="7cad6-149">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="7cad6-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="7cad6-150">Типы данных</span><span class="sxs-lookup"><span data-stu-id="7cad6-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
