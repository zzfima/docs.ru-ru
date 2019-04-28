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
ms.openlocfilehash: 4e0831a045da5eb5798d10aeb977981ecae20040
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61869672"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="218ed-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="218ed-102">Value Types and Reference Types</span></span>
<span data-ttu-id="218ed-103">В Visual Basic типы данных реализованы на основе их классификации.</span><span class="sxs-lookup"><span data-stu-id="218ed-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="218ed-104">Типы данных Visual Basic могут быть классифицированы в соответствии с ли переменная определенного типа хранит собственные данные или указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="218ed-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="218ed-105">Если он хранит собственные данные *тип значения*; если он содержит указатель на данные в другом месте в памяти, это *ссылочный тип*.</span><span class="sxs-lookup"><span data-stu-id="218ed-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="218ed-106">Типы значений</span><span class="sxs-lookup"><span data-stu-id="218ed-106">Value Types</span></span>  
 <span data-ttu-id="218ed-107">Тип данных является *тип значения* если он содержит данные в пределах своей собственной памяти.</span><span class="sxs-lookup"><span data-stu-id="218ed-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="218ed-108">Ниже приведены типы значений:</span><span class="sxs-lookup"><span data-stu-id="218ed-108">Value types include the following:</span></span>  
  
- <span data-ttu-id="218ed-109">Все числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="218ed-109">All numeric data types</span></span>  
  
- <span data-ttu-id="218ed-110">`Boolean`, `Char`и `Date`</span><span class="sxs-lookup"><span data-stu-id="218ed-110">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="218ed-111">Все структуры, даже если их элементы являются ссылочными типами</span><span class="sxs-lookup"><span data-stu-id="218ed-111">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="218ed-112">Перечисления, поскольку их базовый тип всегда является `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, или `ULong`</span><span class="sxs-lookup"><span data-stu-id="218ed-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="218ed-113">Каждая структура является типом значения, даже если он содержит члены ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="218ed-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="218ed-114">По этой причине значение типы, такие как `Char` и `Integer` реализуются структуры .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="218ed-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="218ed-115">Можно объявить тип значения с помощью зарезервированного ключевого слова, например, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="218ed-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="218ed-116">Можно также использовать `New` ключевое слово для инициализации типа значения.</span><span class="sxs-lookup"><span data-stu-id="218ed-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="218ed-117">Это особенно полезно в том случае, если тип имеет конструктор, принимающий параметры.</span><span class="sxs-lookup"><span data-stu-id="218ed-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="218ed-118">Примером этого является <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> конструктор, который создает новый `Decimal` значение из предоставленных частей.</span><span class="sxs-lookup"><span data-stu-id="218ed-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="218ed-119">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="218ed-119">Reference Types</span></span>  
 <span data-ttu-id="218ed-120">Объект *ссылочный тип* содержит указатель на другое расположение в памяти, которая содержит данные.</span><span class="sxs-lookup"><span data-stu-id="218ed-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="218ed-121">Ссылочные типы включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="218ed-121">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="218ed-122">Все массивы, даже в том случае, если их элементы являются типами значений</span><span class="sxs-lookup"><span data-stu-id="218ed-122">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="218ed-123">Типы классов, такие как <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="218ed-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="218ed-124">Делегаты</span><span class="sxs-lookup"><span data-stu-id="218ed-124">Delegates</span></span>  
  
 <span data-ttu-id="218ed-125">Класс является *ссылочный тип*.</span><span class="sxs-lookup"><span data-stu-id="218ed-125">A class is a *reference type*.</span></span> <span data-ttu-id="218ed-126">По этой причине ссылочные типы, такие как `Object` и `String` поддерживаются [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] классы.</span><span class="sxs-lookup"><span data-stu-id="218ed-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="218ed-127">Обратите внимание на то, что каждый массив является ссылочным типом, даже если его члены являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="218ed-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="218ed-128">Так как каждый ссылочный тип представляет собой соответствующий класс .NET Framework, необходимо использовать [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово для его инициализации.</span><span class="sxs-lookup"><span data-stu-id="218ed-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="218ed-129">Следующая инструкция инициализирует массив.</span><span class="sxs-lookup"><span data-stu-id="218ed-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="218ed-130">Элементы, которые не являются типами</span><span class="sxs-lookup"><span data-stu-id="218ed-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="218ed-131">Следующие элементы программирования не могут считаться типов, так как нельзя указать любой из них как тип данных для объявленного элемента:</span><span class="sxs-lookup"><span data-stu-id="218ed-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="218ed-132">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="218ed-132">Namespaces</span></span>  
  
- <span data-ttu-id="218ed-133">Модули</span><span class="sxs-lookup"><span data-stu-id="218ed-133">Modules</span></span>  
  
- <span data-ttu-id="218ed-134">События</span><span class="sxs-lookup"><span data-stu-id="218ed-134">Events</span></span>  
  
- <span data-ttu-id="218ed-135">Свойства и процедуры</span><span class="sxs-lookup"><span data-stu-id="218ed-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="218ed-136">Переменные, константы и поля</span><span class="sxs-lookup"><span data-stu-id="218ed-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="218ed-137">Работа с типом данных объекта</span><span class="sxs-lookup"><span data-stu-id="218ed-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="218ed-138">Можно назначить переменной ссылочным типом или типом значения `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="218ed-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="218ed-139">`Object` Переменной всегда содержит указатель на данные, никогда не сами данные.</span><span class="sxs-lookup"><span data-stu-id="218ed-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="218ed-140">Однако если присвоить тип значения для `Object` переменной, он действует так, будто он хранит собственные данные.</span><span class="sxs-lookup"><span data-stu-id="218ed-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="218ed-141">Дополнительные сведения см. в разделе [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="218ed-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="218ed-142">Вы можете выяснить, был ли `Object` переменная используется в качестве ссылочным типом или типом значения, передав его в <xref:Microsoft.VisualBasic.Information.IsReference%2A> метод в <xref:Microsoft.VisualBasic.Information> класс <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="218ed-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="218ed-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Возвращает `True` Если содержание `Object` переменная представляет ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="218ed-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218ed-144">См. также</span><span class="sxs-lookup"><span data-stu-id="218ed-144">See also</span></span>

- [<span data-ttu-id="218ed-145">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="218ed-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="218ed-146">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="218ed-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="218ed-147">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="218ed-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="218ed-148">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="218ed-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="218ed-149">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="218ed-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="218ed-150">Типы данных</span><span class="sxs-lookup"><span data-stu-id="218ed-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
