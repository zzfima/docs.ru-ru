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
ms.openlocfilehash: 99eeb4b619f6bb23d00f8e449de953d41843f714
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343868"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="0989b-102">Тип данных, определенный пользователем</span><span class="sxs-lookup"><span data-stu-id="0989b-102">User-Defined Data Type</span></span>

<span data-ttu-id="0989b-103">Хранит данные в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="0989b-103">Holds data in a format you define.</span></span> <span data-ttu-id="0989b-104">Оператор `Structure` определяет формат.</span><span class="sxs-lookup"><span data-stu-id="0989b-104">The `Structure` statement defines the format.</span></span>

<span data-ttu-id="0989b-105">Предыдущие версии Visual Basic поддерживают определяемый пользователем тип (UDT).</span><span class="sxs-lookup"><span data-stu-id="0989b-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="0989b-106">Текущая версия расширяет определяемый пользователем тип на *структуру*.</span><span class="sxs-lookup"><span data-stu-id="0989b-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="0989b-107">Структура — это объединение одного или нескольких *элементов* различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="0989b-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="0989b-108">Visual Basic обрабатывает структуру как единое целое, хотя вы также можете обращаться к ее членам по отдельности.</span><span class="sxs-lookup"><span data-stu-id="0989b-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>

## <a name="remarks"></a><span data-ttu-id="0989b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0989b-109">Remarks</span></span>

<span data-ttu-id="0989b-110">Определяйте и используйте тип данных Structure, если необходимо объединить различные типы данных в один блок или если ни один из простейших типов данных не подходит для ваших нужд.</span><span class="sxs-lookup"><span data-stu-id="0989b-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>

<span data-ttu-id="0989b-111">Значение по умолчанию для типа данных Structure состоит из сочетания значений по умолчанию для каждого из его элементов.</span><span class="sxs-lookup"><span data-stu-id="0989b-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>

## <a name="declaration-format"></a><span data-ttu-id="0989b-112">Формат объявления</span><span class="sxs-lookup"><span data-stu-id="0989b-112">Declaration Format</span></span>

<span data-ttu-id="0989b-113">Объявление структуры начинается с [оператора Structure](../../../visual-basic/language-reference/statements/structure-statement.md) и заканчивается оператором `End Structure`.</span><span class="sxs-lookup"><span data-stu-id="0989b-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="0989b-114">Инструкция `Structure` предоставляет имя структуры, которая также является идентификатором типа данных, определяемого структурой.</span><span class="sxs-lookup"><span data-stu-id="0989b-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="0989b-115">Другие части кода могут использовать этот идентификатор для объявления переменных, параметров и возвращаемых значений функций в качестве типа данных этой структуры.</span><span class="sxs-lookup"><span data-stu-id="0989b-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>

<span data-ttu-id="0989b-116">Объявления между операторами `Structure` и `End Structure` определяют элементы структуры.</span><span class="sxs-lookup"><span data-stu-id="0989b-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>

## <a name="member-access-levels"></a><span data-ttu-id="0989b-117">Уровни доступа к членам</span><span class="sxs-lookup"><span data-stu-id="0989b-117">Member Access Levels</span></span>

<span data-ttu-id="0989b-118">Каждый член необходимо объявить с помощью [оператора Dim](../../../visual-basic/language-reference/statements/dim-statement.md) или оператора, определяющего уровень доступа, например [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md)или [Private](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="0989b-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="0989b-119">При использовании оператора `Dim` уровень доступа по умолчанию равен public.</span><span class="sxs-lookup"><span data-stu-id="0989b-119">If you use a `Dim` statement, the access level defaults to public.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="0989b-120">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="0989b-120">Programming Tips</span></span>

- <span data-ttu-id="0989b-121">**Потребление памяти.**</span><span class="sxs-lookup"><span data-stu-id="0989b-121">**Memory Consumption.**</span></span> <span data-ttu-id="0989b-122">Как и для всех составных типов данных, вы не можете безопасно вычислить общее потребление памяти для структуры, добавив в них номинальные объемы выделяемого пространства для его членов.</span><span class="sxs-lookup"><span data-stu-id="0989b-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="0989b-123">Кроме того, нельзя безопасно предположить, что порядок хранения в памяти совпадает с порядком объявления.</span><span class="sxs-lookup"><span data-stu-id="0989b-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="0989b-124">Если необходимо управлять структурой хранилища структуры, можно применить атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> к инструкции `Structure`.</span><span class="sxs-lookup"><span data-stu-id="0989b-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>

- <span data-ttu-id="0989b-125">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="0989b-125">**Interop Considerations.**</span></span> <span data-ttu-id="0989b-126">Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что определяемые пользователем типы в других средах несовместимы с типами структуры Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0989b-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>

- <span data-ttu-id="0989b-127">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="0989b-127">**Widening.**</span></span> <span data-ttu-id="0989b-128">Автоматическое преобразование в любой тип данных структуры или из него отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0989b-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="0989b-129">Операторы преобразования в структуре можно определить с помощью оператора [оператора](../../../visual-basic/language-reference/statements/operator-statement.md), а каждый оператор преобразования можно объявить `Widening` или `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="0989b-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>

- <span data-ttu-id="0989b-130">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="0989b-130">**Type Characters.**</span></span> <span data-ttu-id="0989b-131">Типы данных структуры не имеют символа литерального типа или символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0989b-131">Structure data types have no literal type character or identifier type character.</span></span>

- <span data-ttu-id="0989b-132">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="0989b-132">**Framework Type.**</span></span> <span data-ttu-id="0989b-133">В .NET Framework нет соответствующего типа.</span><span class="sxs-lookup"><span data-stu-id="0989b-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="0989b-134">Все структуры наследуют от класса .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, но никакие отдельные структуры не соответствуют <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0989b-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="0989b-135">Пример</span><span class="sxs-lookup"><span data-stu-id="0989b-135">Example</span></span>

<span data-ttu-id="0989b-136">В следующей парадигме показана структура объявления структуры.</span><span class="sxs-lookup"><span data-stu-id="0989b-136">The following paradigm shows the outline of the declaration of a structure.</span></span>

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a><span data-ttu-id="0989b-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="0989b-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="0989b-138">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0989b-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0989b-139">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="0989b-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0989b-140">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="0989b-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0989b-141">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="0989b-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="0989b-142">Расширение</span><span class="sxs-lookup"><span data-stu-id="0989b-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="0989b-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="0989b-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="0989b-144">Структуры</span><span class="sxs-lookup"><span data-stu-id="0989b-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="0989b-145">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="0989b-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
