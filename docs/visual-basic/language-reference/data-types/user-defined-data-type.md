---
title: Тип данных, определенный пользователем
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 07f04fb111863ca18d4966a7f0f967f11719aeec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="user-defined-data-type"></a><span data-ttu-id="68702-102">Тип данных, определенный пользователем</span><span class="sxs-lookup"><span data-stu-id="68702-102">User-Defined Data Type</span></span>
<span data-ttu-id="68702-103">Содержит данные в формате, определяемом.</span><span class="sxs-lookup"><span data-stu-id="68702-103">Holds data in a format you define.</span></span> <span data-ttu-id="68702-104">`Structure` Инструкция определяет формат.</span><span class="sxs-lookup"><span data-stu-id="68702-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="68702-105">Предыдущие версии Visual Basic поддерживают определяемый пользователем тип (UDT).</span><span class="sxs-lookup"><span data-stu-id="68702-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="68702-106">Текущая версия расширяет в определяемом пользователем ТИПЕ *структуры*.</span><span class="sxs-lookup"><span data-stu-id="68702-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="68702-107">Структура — это объединение одного или нескольких *члены* различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="68702-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="68702-108">Visual Basic обрабатывает структуру как единый блок, хотя также можно использовать его члены по отдельности.</span><span class="sxs-lookup"><span data-stu-id="68702-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68702-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="68702-109">Remarks</span></span>  
 <span data-ttu-id="68702-110">Определять и использовать тип структуры данных, когда необходимо объединить различные типы данных в одну единицу или когда ни одна из простейших типов данных соответствует конкретным требованиям.</span><span class="sxs-lookup"><span data-stu-id="68702-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="68702-111">Значение по умолчанию типа структуры данных состоит из комбинации значений по умолчанию для каждого из его членов.</span><span class="sxs-lookup"><span data-stu-id="68702-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="68702-112">Формат объявления</span><span class="sxs-lookup"><span data-stu-id="68702-112">Declaration Format</span></span>  
 <span data-ttu-id="68702-113">Объявление структуры начинается с [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) и заканчивается `End``Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="68702-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End``Structure` statement.</span></span> <span data-ttu-id="68702-114">`Structure` Оператор содержит имя структуры, которая является также идентификатором типа данных, определение структуры.</span><span class="sxs-lookup"><span data-stu-id="68702-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="68702-115">Другие части кода можно использовать этот идентификатор для объявления переменных, параметров и функции возвращают значения типа данных этой структуры.</span><span class="sxs-lookup"><span data-stu-id="68702-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="68702-116">Объявления между `Structure` и `End``Structure` инструкции определения членов структуры.</span><span class="sxs-lookup"><span data-stu-id="68702-116">The declarations between the `Structure` and `End``Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="68702-117">Уровни доступа к членам</span><span class="sxs-lookup"><span data-stu-id="68702-117">Member Access Levels</span></span>  
 <span data-ttu-id="68702-118">Необходимо объявить каждый член с помощью [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md) или инструкцию, которая определяет уровень доступа, например [открытый](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), или [частного](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="68702-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="68702-119">Если вы используете `Dim` оператора, по умолчанию уровня доступа к открытым.</span><span class="sxs-lookup"><span data-stu-id="68702-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="68702-120">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="68702-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="68702-121">**Потребление памяти.**</span><span class="sxs-lookup"><span data-stu-id="68702-121">**Memory Consumption.**</span></span> <span data-ttu-id="68702-122">Как и все составные типы данных, нельзя вычислить безопасно общее потребление памяти структуры путем сложения выделения Номинальное дисковое его члены.</span><span class="sxs-lookup"><span data-stu-id="68702-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="68702-123">Более того нельзя безошибочно полагать, что порядок расположения элементов в памяти является таким же, как и порядок их объявления.</span><span class="sxs-lookup"><span data-stu-id="68702-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="68702-124">Если вам необходимо управлять структуры хранилища структуры, можно применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="68702-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
-   <span data-ttu-id="68702-125">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="68702-125">**Interop Considerations.**</span></span> <span data-ttu-id="68702-126">При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например автоматизации или COM-объекты, необходимо помнить, что определяемые пользователем типы в других средах не совместимы с Visual Basic типами структуры.</span><span class="sxs-lookup"><span data-stu-id="68702-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
-   <span data-ttu-id="68702-127">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="68702-127">**Widening.**</span></span> <span data-ttu-id="68702-128">Нет автоматического преобразования в или из любой тип данных структуры.</span><span class="sxs-lookup"><span data-stu-id="68702-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="68702-129">Можно определить операторы преобразования структуры с помощью [оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md), и можно объявить каждый оператор преобразования быть `Widening` или `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="68702-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
-   <span data-ttu-id="68702-130">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="68702-130">**Type Characters.**</span></span> <span data-ttu-id="68702-131">Типы данных структуры не имеют буквенного символа или знак типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="68702-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="68702-132">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="68702-132">**Framework Type.**</span></span> <span data-ttu-id="68702-133">Нет соответствующих типов в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68702-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="68702-134">Все структуры наследуют от класса .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, но не отдельные структура соответствует <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68702-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68702-135">Пример</span><span class="sxs-lookup"><span data-stu-id="68702-135">Example</span></span>  
 <span data-ttu-id="68702-136">В следующем примере демонстрируется структура объявления структуры.</span><span class="sxs-lookup"><span data-stu-id="68702-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="68702-137">См. также</span><span class="sxs-lookup"><span data-stu-id="68702-137">See Also</span></span>  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [<span data-ttu-id="68702-138">Типы данных</span><span class="sxs-lookup"><span data-stu-id="68702-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="68702-139">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="68702-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="68702-140">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="68702-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="68702-141">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="68702-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="68702-142">Расширение</span><span class="sxs-lookup"><span data-stu-id="68702-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="68702-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="68702-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="68702-144">Структуры</span><span class="sxs-lookup"><span data-stu-id="68702-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="68702-145">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="68702-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
