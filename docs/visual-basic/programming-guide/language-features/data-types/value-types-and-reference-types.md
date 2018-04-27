---
title: Value Types and Reference Types
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cbab25e4af6b96ae22fe18d0b8a8fdbc7a7c7a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="df0bd-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="df0bd-102">Value Types and Reference Types</span></span>
<span data-ttu-id="df0bd-103">В Visual Basic типы данных реализуются на основе их классификации.</span><span class="sxs-lookup"><span data-stu-id="df0bd-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="df0bd-104">Типы данных Visual Basic могут классифицироваться в соответствии с переменной определенного типа, хранит ли собственные данные или указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="df0bd-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="df0bd-105">Если она хранит свои собственные данные *тип значения*; если он содержит указатель на данные в другом месте в памяти, это *ссылочному типу*.</span><span class="sxs-lookup"><span data-stu-id="df0bd-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="df0bd-106">Типы значений</span><span class="sxs-lookup"><span data-stu-id="df0bd-106">Value Types</span></span>  
 <span data-ttu-id="df0bd-107">Тип данных является *тип значения* , если он содержит данные в пределах своей собственной памяти.</span><span class="sxs-lookup"><span data-stu-id="df0bd-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="df0bd-108">Следующие типы значений:</span><span class="sxs-lookup"><span data-stu-id="df0bd-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="df0bd-109">Все числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="df0bd-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="df0bd-110">`Boolean`, `Char` и `Date`</span><span class="sxs-lookup"><span data-stu-id="df0bd-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="df0bd-111">Все структуры, даже если их члены являются ссылочными типами</span><span class="sxs-lookup"><span data-stu-id="df0bd-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="df0bd-112">Перечисления, поскольку их базовый тип всегда является `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, или `ULong`</span><span class="sxs-lookup"><span data-stu-id="df0bd-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="df0bd-113">Каждая структура является типом значения, даже если он содержит члены ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="df0bd-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="df0bd-114">По этой причине значение типы, такие как `Char` и `Integer` реализуются структуры .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df0bd-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="df0bd-115">Можно объявить тип значения с помощью зарезервированного ключевого слова, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="df0bd-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="df0bd-116">Можно также использовать `New` ключевое слово для инициализации типа значений.</span><span class="sxs-lookup"><span data-stu-id="df0bd-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="df0bd-117">Это особенно полезно в том случае, если тип имеет конструктор, который принимает параметры.</span><span class="sxs-lookup"><span data-stu-id="df0bd-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="df0bd-118">Примером этого является <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> конструктор, который создает новый `Decimal` значение из предоставленных частей.</span><span class="sxs-lookup"><span data-stu-id="df0bd-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="df0bd-119">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="df0bd-119">Reference Types</span></span>  
 <span data-ttu-id="df0bd-120">Объект *ссылочному типу* содержит указатель на другую область памяти, содержащую данные.</span><span class="sxs-lookup"><span data-stu-id="df0bd-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="df0bd-121">Ссылочные типы включают следующие:</span><span class="sxs-lookup"><span data-stu-id="df0bd-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="df0bd-122">Все массивы, даже если их элементы являются типами значений</span><span class="sxs-lookup"><span data-stu-id="df0bd-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="df0bd-123">Типы классов, таких как <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="df0bd-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="df0bd-124">Делегаты</span><span class="sxs-lookup"><span data-stu-id="df0bd-124">Delegates</span></span>  
  
 <span data-ttu-id="df0bd-125">Класс является *ссылочному типу*.</span><span class="sxs-lookup"><span data-stu-id="df0bd-125">A class is a *reference type*.</span></span> <span data-ttu-id="df0bd-126">По этой причине ссылочные типы, такие как `Object` и `String` поддерживаемых [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] классы.</span><span class="sxs-lookup"><span data-stu-id="df0bd-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="df0bd-127">Обратите внимание, что каждый массив является ссылочным типом, даже если его члены являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="df0bd-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="df0bd-128">Поскольку каждый ссылочный тип представляет собой соответствующий класс .NET Framework, необходимо использовать [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово для его инициализации.</span><span class="sxs-lookup"><span data-stu-id="df0bd-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="df0bd-129">Следующий оператор инициализирует массив.</span><span class="sxs-lookup"><span data-stu-id="df0bd-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="df0bd-130">Элементы, которые не являются типами</span><span class="sxs-lookup"><span data-stu-id="df0bd-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="df0bd-131">Следующие элементы программирования не квалифицируются как типы, так как нельзя указывать ни один из них как тип данных для объявленного элемента:</span><span class="sxs-lookup"><span data-stu-id="df0bd-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="df0bd-132">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="df0bd-132">Namespaces</span></span>  
  
-   <span data-ttu-id="df0bd-133">Модули</span><span class="sxs-lookup"><span data-stu-id="df0bd-133">Modules</span></span>  
  
-   <span data-ttu-id="df0bd-134">События</span><span class="sxs-lookup"><span data-stu-id="df0bd-134">Events</span></span>  
  
-   <span data-ttu-id="df0bd-135">Свойства и процедуры</span><span class="sxs-lookup"><span data-stu-id="df0bd-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="df0bd-136">Переменные, константы и поля</span><span class="sxs-lookup"><span data-stu-id="df0bd-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="df0bd-137">Работа с типом данных объекта</span><span class="sxs-lookup"><span data-stu-id="df0bd-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="df0bd-138">Можно назначить ссылочным типом или типом значения переменной `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="df0bd-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="df0bd-139">`Object` Переменная всегда содержит указатель на данные, а не сами данные.</span><span class="sxs-lookup"><span data-stu-id="df0bd-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="df0bd-140">Однако если присвоить тип значения для `Object` переменной, он ведет себя как если бы она содержала свои собственные данные.</span><span class="sxs-lookup"><span data-stu-id="df0bd-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="df0bd-141">Дополнительные сведения см. в разделе [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="df0bd-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="df0bd-142">Можно выяснить, следует ли `Object` переменная используется в качестве ссылочным типом или типом значения, передайте ее в <xref:Microsoft.VisualBasic.Information.IsReference%2A> метод в <xref:Microsoft.VisualBasic.Information> класс <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="df0bd-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="df0bd-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Возвращает `True` Если содержимое `Object` переменная представляет ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="df0bd-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0bd-144">См. также</span><span class="sxs-lookup"><span data-stu-id="df0bd-144">See Also</span></span>  
 [<span data-ttu-id="df0bd-145">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="df0bd-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="df0bd-146">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df0bd-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="df0bd-147">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="df0bd-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="df0bd-148">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="df0bd-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="df0bd-149">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="df0bd-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="df0bd-150">Типы данных</span><span class="sxs-lookup"><span data-stu-id="df0bd-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
