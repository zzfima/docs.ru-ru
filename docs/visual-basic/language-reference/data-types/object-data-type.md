---
title: Object Data Type
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 847f2b50296ad1a1ba6f0009d1d6afced27f9abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-data-type"></a><span data-ttu-id="5b907-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="5b907-102">Object Data Type</span></span>
<span data-ttu-id="5b907-103">Содержит адреса, которые ссылаются на объекты.</span><span class="sxs-lookup"><span data-stu-id="5b907-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="5b907-104">Можно назначить любой ссылочный тип (строка, массив, класс или интерфейс) `Object` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b907-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="5b907-105">`Object` Переменная также может ссылаться на данные любого типа значения (числовые, `Boolean`, `Char`, `Date`, структуры или перечисления).</span><span class="sxs-lookup"><span data-stu-id="5b907-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b907-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b907-106">Remarks</span></span>  
 <span data-ttu-id="5b907-107">`Object` Тип данных может указывать на данные любого типа данных, включая любое приложение распознает экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="5b907-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="5b907-108">Используйте `Object` при во время компиляции неизвестно, какой тип данных переменной может указывать на.</span><span class="sxs-lookup"><span data-stu-id="5b907-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="5b907-109">Значение по умолчанию `Object` — `Nothing` (ссылка null).</span><span class="sxs-lookup"><span data-stu-id="5b907-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="5b907-110">Типы данных</span><span class="sxs-lookup"><span data-stu-id="5b907-110">Data Types</span></span>  
 <span data-ttu-id="5b907-111">Можно назначить переменную, константу или выражение любого типа данных для `Object` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b907-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="5b907-112">Определяет тип данных `Object` в настоящее время ссылается переменная, можно использовать <xref:System.Type.GetTypeCode%2A> метод <xref:System.Type?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="5b907-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="5b907-113">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5b907-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="5b907-114">`Object` Тип данных является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="5b907-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="5b907-115">Однако Visual Basic обрабатывает `Object` переменной как тип значения, если она ссылается на данные типа значения.</span><span class="sxs-lookup"><span data-stu-id="5b907-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="5b907-116">Хранилище</span><span class="sxs-lookup"><span data-stu-id="5b907-116">Storage</span></span>  
 <span data-ttu-id="5b907-117">Любой тип данных, которые он ссылается, `Object` сам, а — указатель на значение переменной не содержит значение данных.</span><span class="sxs-lookup"><span data-stu-id="5b907-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="5b907-118">Она всегда занимает четыре байта в памяти компьютера, но это не относится к хранилища для данных, представляющих значение переменной.</span><span class="sxs-lookup"><span data-stu-id="5b907-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="5b907-119">Поскольку код использует указатель для поиска данных `Object` переменной типа обрабатываются немного медленнее получить доступ к более явно типизированных переменных.</span><span class="sxs-lookup"><span data-stu-id="5b907-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="5b907-120">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="5b907-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="5b907-121">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="5b907-121">**Interop Considerations.**</span></span> <span data-ttu-id="5b907-122">Если выполняется взаимодействие с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, имейте в виду, в других средах типы указателя несовместимы с Visual Basic `Object` типа.</span><span class="sxs-lookup"><span data-stu-id="5b907-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="5b907-123">**Производительность.**</span><span class="sxs-lookup"><span data-stu-id="5b907-123">**Performance.**</span></span> <span data-ttu-id="5b907-124">Переменная объявляется с `Object` обладает достаточной гибкостью для содержат ссылку на объект любого типа.</span><span class="sxs-lookup"><span data-stu-id="5b907-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="5b907-125">Тем не менее, при вызове метода или свойства для такой переменной всегда вызывается *позднего связывания* (во время выполнения).</span><span class="sxs-lookup"><span data-stu-id="5b907-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="5b907-126">Чтобы принудительно *раннее связывание* (во время компиляции) и более высокую производительность, объявите переменную с определенное имя класса или привести его к определенному типу данных.</span><span class="sxs-lookup"><span data-stu-id="5b907-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="5b907-127">При объявлении переменной объекта, попробуйте использовать определенный тип класса, например <xref:System.OperatingSystem>, вместо обобщенный `Object` типа.</span><span class="sxs-lookup"><span data-stu-id="5b907-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="5b907-128">Также следует использовать наиболее определенный класс доступен, например <xref:System.Windows.Forms.TextBox> вместо <xref:System.Windows.Forms.Control>таким образом, чтобы получить доступ к его свойствам и методам.</span><span class="sxs-lookup"><span data-stu-id="5b907-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="5b907-129">Обычно можно использовать **классы** списка в **обозревателя объектов** для поиска имен доступных классов.</span><span class="sxs-lookup"><span data-stu-id="5b907-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="5b907-130">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="5b907-130">**Widening.**</span></span> <span data-ttu-id="5b907-131">Все типы данных и все ссылочные типы расширяются до `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="5b907-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="5b907-132">Это означает, что любой тип можно преобразовать `Object` без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="5b907-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="5b907-133">Тем не менее при преобразовании между типами значений и `Object`, Visual Basic выполняет операции *упаковка-преобразование* и *распаковки*, убедитесь в выполнении медленнее.</span><span class="sxs-lookup"><span data-stu-id="5b907-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="5b907-134">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="5b907-134">**Type Characters.**</span></span> <span data-ttu-id="5b907-135">`Object`не имеет знак типа литерала или знак типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="5b907-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="5b907-136">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="5b907-136">**Framework Type.**</span></span> <span data-ttu-id="5b907-137">Соответствующий тип в .NET Framework — <xref:System.Object?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="5b907-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b907-138">Пример</span><span class="sxs-lookup"><span data-stu-id="5b907-138">Example</span></span>  
 <span data-ttu-id="5b907-139">В следующем примере демонстрируется `Object` переменную, указывающую на экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="5b907-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b907-140">См. также</span><span class="sxs-lookup"><span data-stu-id="5b907-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="5b907-141">Типы данных</span><span class="sxs-lookup"><span data-stu-id="5b907-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="5b907-142">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="5b907-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="5b907-143">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="5b907-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="5b907-144">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="5b907-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="5b907-145">Практическое руководство. Определение наличия связи между двумя объектами</span><span class="sxs-lookup"><span data-stu-id="5b907-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="5b907-146">Практическое руководство. Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="5b907-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
