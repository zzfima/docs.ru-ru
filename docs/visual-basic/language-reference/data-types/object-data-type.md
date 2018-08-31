---
title: Тип данных объекта (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 94d3ddcf71194eb69a2d26bcdf549aaf693e46e6
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255710"
---
# <a name="object-data-type"></a><span data-ttu-id="179ff-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="179ff-102">Object Data Type</span></span>
<span data-ttu-id="179ff-103">Содержит адреса, которые ссылаются на объекты.</span><span class="sxs-lookup"><span data-stu-id="179ff-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="179ff-104">Можно назначить любой ссылочный тип (строка, массив, класс или интерфейс) `Object` переменной.</span><span class="sxs-lookup"><span data-stu-id="179ff-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="179ff-105">`Object` Переменная также может ссылаться на данные любого типа значения (числовые, `Boolean`, `Char`, `Date`, структуры или перечисления).</span><span class="sxs-lookup"><span data-stu-id="179ff-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="179ff-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="179ff-106">Remarks</span></span>  
 <span data-ttu-id="179ff-107">`Object` Тип данных может указывать на данные любого типа данных, включая любой экземпляр объекта, ваше приложение распознавало.</span><span class="sxs-lookup"><span data-stu-id="179ff-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="179ff-108">Используйте `Object` при во время компиляции неизвестно, какой тип данных переменной может указывать на.</span><span class="sxs-lookup"><span data-stu-id="179ff-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="179ff-109">Значение по умолчанию `Object` является `Nothing` (ссылкой на null).</span><span class="sxs-lookup"><span data-stu-id="179ff-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="179ff-110">Типы данных</span><span class="sxs-lookup"><span data-stu-id="179ff-110">Data Types</span></span>  
 <span data-ttu-id="179ff-111">Можно назначить переменную, константу или выражение любого типа данных для `Object` переменной.</span><span class="sxs-lookup"><span data-stu-id="179ff-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="179ff-112">Чтобы определить тип данных `Object` в настоящее время ссылается переменная, можно использовать <xref:System.Type.GetTypeCode%2A> метод <xref:System.Type?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="179ff-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="179ff-113">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="179ff-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="179ff-114">`Object` Тип данных является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="179ff-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="179ff-115">Тем не менее, Visual Basic обрабатывает `Object` переменной как тип значения, если она ссылается на данные типа значения.</span><span class="sxs-lookup"><span data-stu-id="179ff-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="179ff-116">Хранилище</span><span class="sxs-lookup"><span data-stu-id="179ff-116">Storage</span></span>  
 <span data-ttu-id="179ff-117">Любой тип данных, которые он ссылается, `Object` отдельно, однако вместо указатель на значение переменной не содержит значения данных.</span><span class="sxs-lookup"><span data-stu-id="179ff-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="179ff-118">В ней всегда используется четыре байта в памяти компьютера, но это не относится к хранилище для данных, представляющих значение переменной.</span><span class="sxs-lookup"><span data-stu-id="179ff-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="179ff-119">Поскольку код использует указатель для поиска данных `Object` переменных типа обрабатываются немного медленнее, для доступа по сравнению с явно типизированные переменные.</span><span class="sxs-lookup"><span data-stu-id="179ff-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="179ff-120">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="179ff-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="179ff-121">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="179ff-121">**Interop Considerations.**</span></span> <span data-ttu-id="179ff-122">При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, не забывайте, что в других средах типы указателей не совместимы с Visual Basic `Object` типа.</span><span class="sxs-lookup"><span data-stu-id="179ff-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="179ff-123">**Производительность.**</span><span class="sxs-lookup"><span data-stu-id="179ff-123">**Performance.**</span></span> <span data-ttu-id="179ff-124">Переменная, объявляемая с `Object` тип является достаточно гибким, чтобы содержать ссылку на любой объект.</span><span class="sxs-lookup"><span data-stu-id="179ff-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="179ff-125">Тем не менее, при вызове метода или свойства для такой переменной всегда вызывается *позднее связывание* (во время выполнения).</span><span class="sxs-lookup"><span data-stu-id="179ff-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="179ff-126">Чтобы принудительно *раннее связывание* (во время компиляции) и более высокую производительность, объявите переменную с определенное имя класса или привести к типу данных.</span><span class="sxs-lookup"><span data-stu-id="179ff-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="179ff-127">При объявлении переменной объекта, попробуйте использовать определенный тип класса, например <xref:System.OperatingSystem>, вместо универсального `Object` типа.</span><span class="sxs-lookup"><span data-stu-id="179ff-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="179ff-128">Также следует использовать наиболее конкретный класс доступен, например <xref:System.Windows.Forms.TextBox> вместо <xref:System.Windows.Forms.Control>, позволяя получать доступ к его свойствам и методам.</span><span class="sxs-lookup"><span data-stu-id="179ff-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="179ff-129">Обычно можно использовать **классы** в списке **обозреватель объектов** для поиска имен доступных классов.</span><span class="sxs-lookup"><span data-stu-id="179ff-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="179ff-130">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="179ff-130">**Widening.**</span></span> <span data-ttu-id="179ff-131">Все типы данных и все ссылочные типы расширяющего преобразования к `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="179ff-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="179ff-132">Это означает, что любой тип можно преобразовать `Object` без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="179ff-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="179ff-133">Тем не менее при преобразовании между типами значений и `Object`, Visual Basic выполняет операции *упаковки-преобразования* и *распаковки*, поэтому оказаться, что замедляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="179ff-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="179ff-134">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="179ff-134">**Type Characters.**</span></span> <span data-ttu-id="179ff-135">`Object` не имеет знак типа литерала или знак типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="179ff-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="179ff-136">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="179ff-136">**Framework Type.**</span></span> <span data-ttu-id="179ff-137">Соответствующий тип в .NET Framework — <xref:System.Object?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="179ff-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="179ff-138">Пример</span><span class="sxs-lookup"><span data-stu-id="179ff-138">Example</span></span>  
 <span data-ttu-id="179ff-139">В следующем примере показано `Object` переменной, указывающей на экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="179ff-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="179ff-140">См. также</span><span class="sxs-lookup"><span data-stu-id="179ff-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="179ff-141">Типы данных</span><span class="sxs-lookup"><span data-stu-id="179ff-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="179ff-142">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="179ff-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="179ff-143">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="179ff-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="179ff-144">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="179ff-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="179ff-145">Практическое руководство. Определение наличия связи между двумя объектами</span><span class="sxs-lookup"><span data-stu-id="179ff-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="179ff-146">Практическое руководство. Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="179ff-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
