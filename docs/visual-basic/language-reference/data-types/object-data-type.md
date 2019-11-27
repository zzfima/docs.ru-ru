---
title: Object Data Type
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
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343955"
---
# <a name="object-data-type"></a><span data-ttu-id="620cd-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="620cd-102">Object Data Type</span></span>

<span data-ttu-id="620cd-103">Содержит адреса, которые ссылаются на объекты.</span><span class="sxs-lookup"><span data-stu-id="620cd-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="620cd-104">В переменную `Object` можно назначить любой ссылочный тип (строка, массив, класс или интерфейс).</span><span class="sxs-lookup"><span data-stu-id="620cd-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="620cd-105">`Object`ая переменная может также ссылаться на данные любого типа значения (numeric, `Boolean`, `Char`, `Date`, структуры или перечисления).</span><span class="sxs-lookup"><span data-stu-id="620cd-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="620cd-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="620cd-106">Remarks</span></span>

<span data-ttu-id="620cd-107">Тип данных `Object` может указывать на данные любого типа данных, включая любой экземпляр объекта, распознаваемый приложением.</span><span class="sxs-lookup"><span data-stu-id="620cd-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="620cd-108">Используйте `Object`, если во время компиляции неизвестно, на какой тип данных может указывать переменная.</span><span class="sxs-lookup"><span data-stu-id="620cd-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="620cd-109">Значение `Object` по умолчанию — `Nothing` (пустая ссылка).</span><span class="sxs-lookup"><span data-stu-id="620cd-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="620cd-110">Типы данных</span><span class="sxs-lookup"><span data-stu-id="620cd-110">Data Types</span></span>

<span data-ttu-id="620cd-111">Переменной `Object` можно присвоить переменную, константу или выражение любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="620cd-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="620cd-112">Чтобы определить тип данных, на который в настоящее время ссылается переменная `Object`, можно использовать метод <xref:System.Type.GetTypeCode%2A> класса <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="620cd-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="620cd-113">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="620cd-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="620cd-114">Тип данных `Object` является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="620cd-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="620cd-115">Однако Visual Basic обрабатывает переменную `Object` как тип значения, если она ссылается на данные типа значения.</span><span class="sxs-lookup"><span data-stu-id="620cd-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="620cd-116">Хранилище</span><span class="sxs-lookup"><span data-stu-id="620cd-116">Storage</span></span>

<span data-ttu-id="620cd-117">Любой тип данных, на который он ссылается, `Object`ая переменная не содержит само значение данных, а указатель на это значение.</span><span class="sxs-lookup"><span data-stu-id="620cd-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="620cd-118">Он всегда использует четыре байта в памяти компьютера, но не включает хранилище для данных, представляющих значение переменной.</span><span class="sxs-lookup"><span data-stu-id="620cd-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="620cd-119">Из-за кода, использующего указатель для нахождение данных, `Object` переменные, удерживающие типы значений, немного медленнее, чем явно типизированные переменные.</span><span class="sxs-lookup"><span data-stu-id="620cd-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="620cd-120">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="620cd-120">Programming Tips</span></span>

- <span data-ttu-id="620cd-121">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="620cd-121">**Interop Considerations.**</span></span> <span data-ttu-id="620cd-122">Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что типы указателей в других средах несовместимы с типом `Object` Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="620cd-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="620cd-123">**Производительность.**</span><span class="sxs-lookup"><span data-stu-id="620cd-123">**Performance.**</span></span> <span data-ttu-id="620cd-124">Переменная, объявляемая с типом `Object`, достаточно гибка, чтобы содержать ссылку на любой объект.</span><span class="sxs-lookup"><span data-stu-id="620cd-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="620cd-125">Однако при вызове метода или свойства для такой переменной всегда вызывается *позднее связывание* (во время выполнения).</span><span class="sxs-lookup"><span data-stu-id="620cd-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="620cd-126">Чтобы принудительно выполнить *раннее связывание* (во время компиляции) и повысить производительность, объявите переменную с конкретным именем класса или приведите ее к конкретному типу данных.</span><span class="sxs-lookup"><span data-stu-id="620cd-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="620cd-127">При объявлении объектной переменной попробуйте использовать конкретный тип класса, например <xref:System.OperatingSystem>, вместо обобщенного типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="620cd-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="620cd-128">Следует также использовать наиболее конкретный доступный класс, например <xref:System.Windows.Forms.TextBox> вместо <xref:System.Windows.Forms.Control>, чтобы получить доступ к его свойствам и методам.</span><span class="sxs-lookup"><span data-stu-id="620cd-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="620cd-129">Для поиска доступных имен классов обычно можно использовать список **классы** в **обозревателе объектов** .</span><span class="sxs-lookup"><span data-stu-id="620cd-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="620cd-130">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="620cd-130">**Widening.**</span></span> <span data-ttu-id="620cd-131">Все типы данных и все ссылочные типы расширяются до `Object`ного типа данных.</span><span class="sxs-lookup"><span data-stu-id="620cd-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="620cd-132">Это означает, что можно преобразовать любой тип в `Object` без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="620cd-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="620cd-133">Однако при преобразовании типов значений и `Object`Visual Basic выполняет операции, которые называются *упаковкой-преобразованием* *и*распаковкой, что делает выполнение более медленным.</span><span class="sxs-lookup"><span data-stu-id="620cd-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="620cd-134">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="620cd-134">**Type Characters.**</span></span> <span data-ttu-id="620cd-135">`Object` не имеет символа типа литерала или символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="620cd-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="620cd-136">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="620cd-136">**Framework Type.**</span></span> <span data-ttu-id="620cd-137">Соответствующий тип в .NET Framework является классом <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="620cd-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="620cd-138">Пример</span><span class="sxs-lookup"><span data-stu-id="620cd-138">Example</span></span>

<span data-ttu-id="620cd-139">В следующем примере показана переменная `Object`, указывающая на экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="620cd-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="620cd-140">См. также</span><span class="sxs-lookup"><span data-stu-id="620cd-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="620cd-141">Типы данных</span><span class="sxs-lookup"><span data-stu-id="620cd-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="620cd-142">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="620cd-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="620cd-143">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="620cd-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="620cd-144">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="620cd-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="620cd-145">Практическое руководство. Определение наличия связи между двумя объектами</span><span class="sxs-lookup"><span data-stu-id="620cd-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="620cd-146">Практическое руководство. Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="620cd-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
