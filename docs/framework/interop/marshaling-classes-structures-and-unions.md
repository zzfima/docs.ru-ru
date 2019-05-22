---
title: Маршалинг классов, структур и объединений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2411b69dac6ef8945336a4c4e014cbf6687f702a
ms.sourcegitcommit: 56ac30a336668124cb7d95d8ace16bd985875147
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "65469729"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="6202f-102">Маршалинг классов, структур и объединений</span><span class="sxs-lookup"><span data-stu-id="6202f-102">Marshaling Classes, Structures, and Unions</span></span>
<span data-ttu-id="6202f-103">Классы и структуры в .NET Framework похожи.</span><span class="sxs-lookup"><span data-stu-id="6202f-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="6202f-104">И те и другие могут иметь поля, свойства и события.</span><span class="sxs-lookup"><span data-stu-id="6202f-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="6202f-105">Они также могут иметь статические и нестатические методы.</span><span class="sxs-lookup"><span data-stu-id="6202f-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="6202f-106">Примечательным отличием является то, что структуры являются типами значений, а классы — ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="6202f-106">One notable difference is that structures are value types and classes are reference types.</span></span>  
  
 <span data-ttu-id="6202f-107">В таблице ниже представлены варианты маршалинга классов, структур и объединений, описывается их применение и приводятся ссылки на соответствующие примеры вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="6202f-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>  
  
|<span data-ttu-id="6202f-108">Тип</span><span class="sxs-lookup"><span data-stu-id="6202f-108">Type</span></span>|<span data-ttu-id="6202f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6202f-109">Description</span></span>|<span data-ttu-id="6202f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="6202f-110">Sample</span></span>|  
|----------|-----------------|------------|  
|<span data-ttu-id="6202f-111">Класс по значению.</span><span class="sxs-lookup"><span data-stu-id="6202f-111">Class by value.</span></span>|<span data-ttu-id="6202f-112">Передает класс с целочисленными членами в качестве параметра In или Out (как и в случае управляемого класса).</span><span class="sxs-lookup"><span data-stu-id="6202f-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|<span data-ttu-id="6202f-113">Пример SysTime</span><span class="sxs-lookup"><span data-stu-id="6202f-113">SysTime sample</span></span>|  
|<span data-ttu-id="6202f-114">Структура по значению.</span><span class="sxs-lookup"><span data-stu-id="6202f-114">Structure by value.</span></span>|<span data-ttu-id="6202f-115">Передает структуры в качестве параметров In.</span><span class="sxs-lookup"><span data-stu-id="6202f-115">Passes structures as In parameters.</span></span>|<span data-ttu-id="6202f-116">Пример структур</span><span class="sxs-lookup"><span data-stu-id="6202f-116">Structures sample</span></span>|  
|<span data-ttu-id="6202f-117">Структура по ссылке.</span><span class="sxs-lookup"><span data-stu-id="6202f-117">Structure by reference.</span></span>|<span data-ttu-id="6202f-118">Передает структуры в качестве параметров In и Out.</span><span class="sxs-lookup"><span data-stu-id="6202f-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="6202f-119">пример OSInfo</span><span class="sxs-lookup"><span data-stu-id="6202f-119">OSInfo sample</span></span>|  
|<span data-ttu-id="6202f-120">Структура с вложенными структурами (выровненная).</span><span class="sxs-lookup"><span data-stu-id="6202f-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="6202f-121">Передает класс, представляющий структуру с вложенными структурами, в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="6202f-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="6202f-122">Структура выравнивается в одну большую структуру в управляемом прототипе.</span><span class="sxs-lookup"><span data-stu-id="6202f-122">The structure is flattened to one big structure in the managed prototype.</span></span>|<span data-ttu-id="6202f-123">пример FindFile</span><span class="sxs-lookup"><span data-stu-id="6202f-123">FindFile sample</span></span>|  
|<span data-ttu-id="6202f-124">Структура с указателем на другую структуру.</span><span class="sxs-lookup"><span data-stu-id="6202f-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="6202f-125">Передает структуру, содержащую указатель на другую структуру в качестве члена.</span><span class="sxs-lookup"><span data-stu-id="6202f-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|<span data-ttu-id="6202f-126">Пример структур</span><span class="sxs-lookup"><span data-stu-id="6202f-126">Structures Sample</span></span>|  
|<span data-ttu-id="6202f-127">Массив структур с целочисленными значениями по значению.</span><span class="sxs-lookup"><span data-stu-id="6202f-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="6202f-128">Передает массив структур, содержащих только целые числа, в виде параметра In или Out.</span><span class="sxs-lookup"><span data-stu-id="6202f-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="6202f-129">Элементы массива можно изменять.</span><span class="sxs-lookup"><span data-stu-id="6202f-129">Members of the array can be changed.</span></span>|<span data-ttu-id="6202f-130">Примеры использования массивов</span><span class="sxs-lookup"><span data-stu-id="6202f-130">Arrays Sample</span></span>|  
|<span data-ttu-id="6202f-131">Массив структур с целочисленными значениями и строками по ссылке.</span><span class="sxs-lookup"><span data-stu-id="6202f-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="6202f-132">Передает массив структур, содержащих целые числа и строки, в качестве параметра Out.</span><span class="sxs-lookup"><span data-stu-id="6202f-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="6202f-133">Вызываемая функция выделяет память под массив.</span><span class="sxs-lookup"><span data-stu-id="6202f-133">The called function allocates memory for the array.</span></span>|<span data-ttu-id="6202f-134">Пример OutArrayOfStructs</span><span class="sxs-lookup"><span data-stu-id="6202f-134">OutArrayOfStructs Sample</span></span>|  
|<span data-ttu-id="6202f-135">Объединения с типами значений.</span><span class="sxs-lookup"><span data-stu-id="6202f-135">Unions with value types.</span></span>|<span data-ttu-id="6202f-136">Передает объединения с типами значений (целочисленными и двойной точности).</span><span class="sxs-lookup"><span data-stu-id="6202f-136">Passes unions with value types (integer and double).</span></span>|<span data-ttu-id="6202f-137">пример Unions</span><span class="sxs-lookup"><span data-stu-id="6202f-137">Unions sample</span></span>|  
|<span data-ttu-id="6202f-138">Объединения со смешанными типами.</span><span class="sxs-lookup"><span data-stu-id="6202f-138">Unions with mixed types.</span></span>|<span data-ttu-id="6202f-139">Передает объединения со смешанными типами (целое число и строка).</span><span class="sxs-lookup"><span data-stu-id="6202f-139">Passes unions with mixed types (integer and string).</span></span>|<span data-ttu-id="6202f-140">пример Unions</span><span class="sxs-lookup"><span data-stu-id="6202f-140">Unions sample</span></span>|  
|<span data-ttu-id="6202f-141">Значения Null в структуре.</span><span class="sxs-lookup"><span data-stu-id="6202f-141">Null values in structure.</span></span>|<span data-ttu-id="6202f-142">Передает пустую ссылку (**Nothing** в Visual Basic) вместо ссылки на тип значения.</span><span class="sxs-lookup"><span data-stu-id="6202f-142">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="6202f-143">Пример HandleRef</span><span class="sxs-lookup"><span data-stu-id="6202f-143">HandleRef sample</span></span>|  
  
## <a name="structures-sample"></a><span data-ttu-id="6202f-144">Пример структур</span><span class="sxs-lookup"><span data-stu-id="6202f-144">Structures sample</span></span>  
 <span data-ttu-id="6202f-145">В этом примере показан способ передачи структуры, указывающей на вторую структуру, передачи структуры с внедренной структурой и передачи структуры с внедренным массивом.</span><span class="sxs-lookup"><span data-stu-id="6202f-145">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
 <span data-ttu-id="6202f-146">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="6202f-146">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="6202f-147">функция **TestStructInStruct**, экспортированная из PinvokeLib.dll;</span><span class="sxs-lookup"><span data-stu-id="6202f-147">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestStructInStruct(MYPERSON2* pPerson2);  
    ```  
  
- <span data-ttu-id="6202f-148">функция **TestStructInStruct3**, экспортированная из PinvokeLib.dll;</span><span class="sxs-lookup"><span data-stu-id="6202f-148">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestStructInStruct3(MYPERSON3 person3);  
    ```  
  
- <span data-ttu-id="6202f-149">функция **TestArrayInStruct**, экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="6202f-149">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestArrayInStruct( MYARRAYSTRUCT* pStruct );  
    ```  
  
 <span data-ttu-id="6202f-150">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций и четырех структур: **MYPERSON**, **MYPERSON2**, **MYPERSON3** и **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="6202f-150">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="6202f-151">Эти структуры содержат следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6202f-151">These structures contain the following elements:</span></span>  
  
```  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON, *LP_MYPERSON;  
  
typedef struct _MYPERSON2  
{  
   MYPERSON* person;  
   int age;   
} MYPERSON2, *LP_MYPERSON2;  
  
typedef struct _MYPERSON3  
{  
   MYPERSON person;  
   int age;   
} MYPERSON3;  
  
typedef struct _MYARRAYSTRUCT  
{  
   bool flag;  
   int vals[ 3 ];   
} MYARRAYSTRUCT;  
```  
  
 <span data-ttu-id="6202f-152">Управляемые структуры `MyPerson`, `MyPerson2`, `MyPerson3` и `MyArrayStruct` обладают следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="6202f-152">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>  
  
- <span data-ttu-id="6202f-153">Структура `MyPerson` содержит только члены-строки.</span><span class="sxs-lookup"><span data-stu-id="6202f-153">`MyPerson` contains only string members.</span></span> <span data-ttu-id="6202f-154">Поле [CharSet](specifying-a-character-set.md) задает формат строк ANSI при передаче строки в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="6202f-154">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>  
  
- <span data-ttu-id="6202f-155">`MyPerson2` содержит указатель **IntPtr** на структуру `MyPerson`.</span><span class="sxs-lookup"><span data-stu-id="6202f-155">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="6202f-156">Тип **IntPtr** заменяет исходный указатель на неуправляемую структуру, так как приложения .NET Framework не используют указатели, если код не помечен как **небезопасный**.</span><span class="sxs-lookup"><span data-stu-id="6202f-156">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>  
  
- <span data-ttu-id="6202f-157">Структура `MyPerson3` содержит структуру `MyPerson` в качестве внедренной.</span><span class="sxs-lookup"><span data-stu-id="6202f-157">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="6202f-158">Внедренную структуру можно выровнять путем помещения ее элементов прямо в основную структуру, или ее можно оставить внедренной, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="6202f-158">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>  
  
- <span data-ttu-id="6202f-159">Структура `MyArrayStruct` содержит массив целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="6202f-159">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="6202f-160">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValArray**, которое используется для указания количества элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="6202f-160">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>  
  
 <span data-ttu-id="6202f-161">Для всех структур в этом примере применяется атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>, гарантирующий последовательное размещение элементов в памяти в порядке их появления.</span><span class="sxs-lookup"><span data-stu-id="6202f-161">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="6202f-162">Класс `LibWrap` содержит управляемые прототипы методов `TestStructInStruct`, `TestStructInStruct3` и `TestArrayInStruct`, вызываемые классом `App`.</span><span class="sxs-lookup"><span data-stu-id="6202f-162">The `LibWrap` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="6202f-163">Каждый прототип объявляет один параметр указанным ниже способом.</span><span class="sxs-lookup"><span data-stu-id="6202f-163">Each prototype declares a single parameter, as follows:</span></span>  
  
- <span data-ttu-id="6202f-164">`TestStructInStruct` объявляет в качестве своего параметра ссылку на тип `MyPerson2`.</span><span class="sxs-lookup"><span data-stu-id="6202f-164">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>  
  
- <span data-ttu-id="6202f-165">`TestStructInStruct3` в качестве своего параметра объявляет тип `MyPerson3` и передает параметр по значению.</span><span class="sxs-lookup"><span data-stu-id="6202f-165">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>  
  
- <span data-ttu-id="6202f-166">`TestArrayInStruct` объявляет в качестве своего параметра ссылку на тип `MyArrayStruct`.</span><span class="sxs-lookup"><span data-stu-id="6202f-166">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>  
  
 <span data-ttu-id="6202f-167">Структуры, выступающие в роли аргументов методов, передаются по значению, если параметр не содержит ключевого слова **ref** (**ByRef** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6202f-167">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="6202f-168">Например, метод `TestStructInStruct` передает в неуправляемый код ссылку (значение адреса) на объект типа `MyPerson2`.</span><span class="sxs-lookup"><span data-stu-id="6202f-168">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="6202f-169">Для работы со структурой, на которую указывает `MyPerson2`, в примере с помощью методов <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> создается буфер заданного размера и возвращается его адрес.</span><span class="sxs-lookup"><span data-stu-id="6202f-169">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="6202f-170">Далее в неуправляемый буфер копируется содержимое управляемой структуры.</span><span class="sxs-lookup"><span data-stu-id="6202f-170">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="6202f-171">Наконец, используются метод <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> для маршалинга данных из неуправляемого буфера в управляемый объект и метод <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> для освобождения неуправляемого блока памяти.</span><span class="sxs-lookup"><span data-stu-id="6202f-171">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="6202f-172">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="6202f-172">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
 [!code-csharp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
 [!code-vb[Conceptual.Interop.Marshaling#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]  
  
### <a name="calling-functions"></a><span data-ttu-id="6202f-173">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="6202f-173">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
 [!code-csharp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
 [!code-vb[Conceptual.Interop.Marshaling#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]  
  
## <a name="findfile-sample"></a><span data-ttu-id="6202f-174">пример FindFile</span><span class="sxs-lookup"><span data-stu-id="6202f-174">FindFile sample</span></span>  
 <span data-ttu-id="6202f-175">В этом примере показан способ передачи структуры, содержащей другую, внедренную структуру, в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="6202f-175">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="6202f-176">Также показано, как с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> объявить массив фиксированной длины внутри структуры.</span><span class="sxs-lookup"><span data-stu-id="6202f-176">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="6202f-177">В этом примере элементы внедренной структуры добавляются в родительскую структуру.</span><span class="sxs-lookup"><span data-stu-id="6202f-177">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="6202f-178">Пример внедренной структуры (не преобразованной в плоскую структуру) см. в разделе [Пример структур](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6202f-178">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>  
  
 <span data-ttu-id="6202f-179">В примере FindFile используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="6202f-179">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
- <span data-ttu-id="6202f-180">функция **FindFirstFile**, экспортированная из Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="6202f-180">**FindFirstFile** exported from Kernel32.dll.</span></span>  
  
    ```  
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);  
    ```  
  
 <span data-ttu-id="6202f-181">Исходная структура, переданная в функцию, содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6202f-181">The original structure passed to the function contains the following elements:</span></span>  
  
```  
typedef struct _WIN32_FIND_DATA   
{  
  DWORD    dwFileAttributes;   
  FILETIME ftCreationTime;   
  FILETIME ftLastAccessTime;   
  FILETIME ftLastWriteTime;   
  DWORD    nFileSizeHigh;   
  DWORD    nFileSizeLow;   
  DWORD    dwReserved0;   
  DWORD    dwReserved1;   
  TCHAR    cFileName[ MAX_PATH ];   
  TCHAR    cAlternateFileName[ 14 ];   
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;  
```  
  
 <span data-ttu-id="6202f-182">В этом примере класс `FindData` содержит члены данных, соответствующие каждому элементу исходной и внедренной структур.</span><span class="sxs-lookup"><span data-stu-id="6202f-182">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="6202f-183">Вместо двух исходных символьных буферов класс подставляет строки.</span><span class="sxs-lookup"><span data-stu-id="6202f-183">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="6202f-184">Атрибут **MarshalAsAttribute** задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValTStr**, которое используется для идентификации встроенных символьных массивов фиксированной длины в неуправляемых структурах.</span><span class="sxs-lookup"><span data-stu-id="6202f-184">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>  
  
 <span data-ttu-id="6202f-185">Класс `LibWrap` содержит управляемый прототип метода `FindFirstFile`, передающий класс `FindData` в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="6202f-185">The `LibWrap` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="6202f-186">Этот параметр должен быть объявлен с атрибутами <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>, так как классы, являющиеся ссылочными типами, по умолчанию передаются как параметры In.</span><span class="sxs-lookup"><span data-stu-id="6202f-186">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="6202f-187">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="6202f-187">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
 [!code-csharp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
 [!code-vb[Conceptual.Interop.Marshaling#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]  
  
### <a name="calling-functions"></a><span data-ttu-id="6202f-188">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="6202f-188">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
 [!code-csharp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]  
  
## <a name="unions-sample"></a><span data-ttu-id="6202f-189">пример Unions</span><span class="sxs-lookup"><span data-stu-id="6202f-189">Unions sample</span></span>  
 <span data-ttu-id="6202f-190">В этом примере показан способ передачи структур, содержащих только типы значений, а также структур, содержащих тип значения и строку, в качестве параметров в неуправляемую функцию, ожидающую объединения.</span><span class="sxs-lookup"><span data-stu-id="6202f-190">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="6202f-191">Объединение представляет собой ячейку памяти, которая может совместно использоваться двумя и более переменными.</span><span class="sxs-lookup"><span data-stu-id="6202f-191">A union represents a memory location that can be shared by two or more variables.</span></span>  
  
 <span data-ttu-id="6202f-192">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="6202f-192">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
- <span data-ttu-id="6202f-193">функция **TestUnion**, экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="6202f-193">**TestUnion** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestUnion(MYUNION u, int type);  
    ```  
  
 <span data-ttu-id="6202f-194">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию указанной выше функции и два объединения: **MYUNION** и **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="6202f-194">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="6202f-195">Объединение содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6202f-195">The unions contain the following elements:</span></span>  
  
```  
union MYUNION  
{  
    int number;  
    double d;  
}  
  
union MYUNION2  
{  
    int i;  
    char str[128];  
};  
```  
  
 <span data-ttu-id="6202f-196">В управляемом коде объединения определяются как структуры.</span><span class="sxs-lookup"><span data-stu-id="6202f-196">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="6202f-197">Структура `MyUnion` в качестве своих членов содержит два типа значений: целочисленный и число двойной точности.</span><span class="sxs-lookup"><span data-stu-id="6202f-197">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="6202f-198">Для управления точным положением каждого члена данных задается атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6202f-198">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="6202f-199">Атрибут <xref:System.Runtime.InteropServices.FieldOffsetAttribute> предоставляет физическое положение полей внутри неуправляемого представления объединения.</span><span class="sxs-lookup"><span data-stu-id="6202f-199">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="6202f-200">Обратите внимание, что значения смещения у обоих членов одинаковы, что позволяет членам определять один и тот же участок памяти.</span><span class="sxs-lookup"><span data-stu-id="6202f-200">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>  
  
 <span data-ttu-id="6202f-201">Объединения `MyUnion2_1` и `MyUnion2_2` содержат тип значения (целое число) и строку соответственно.</span><span class="sxs-lookup"><span data-stu-id="6202f-201">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="6202f-202">В управляемом коде типы значений и ссылочные типы не могут перекрываться.</span><span class="sxs-lookup"><span data-stu-id="6202f-202">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="6202f-203">Чтобы при вызове одной и той же неуправляемой функции вызывающий объект мог использовать оба типа, в этом примере применяется перегрузка метода.</span><span class="sxs-lookup"><span data-stu-id="6202f-203">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="6202f-204">Структура `MyUnion2_1` задана явным образом и имеет точное значение смещения.</span><span class="sxs-lookup"><span data-stu-id="6202f-204">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="6202f-205">Напротив, `MyUnion2_2` имеет последовательную структуру, так как структуры, заданные явным образом, нельзя использовать со ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="6202f-205">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="6202f-206">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValTStr**, которое используется для идентификации встроенных символьных массивов фиксированной длины в неуправляемом представлении объединения.</span><span class="sxs-lookup"><span data-stu-id="6202f-206">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>  
  
 <span data-ttu-id="6202f-207">Класс `LibWrap` содержит прототипы для методов `TestUnion` и `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="6202f-207">The `LibWrap` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="6202f-208">`TestUnion2` перегружается для объявления `MyUnion2_1` или `MyUnion2_2` в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="6202f-208">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="6202f-209">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="6202f-209">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
 [!code-csharp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
 [!code-vb[Conceptual.Interop.Marshaling#28](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]  
  
### <a name="calling-functions"></a><span data-ttu-id="6202f-210">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="6202f-210">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
 [!code-csharp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
 [!code-vb[Conceptual.Interop.Marshaling#29](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]  
  
## <a name="systime-sample"></a><span data-ttu-id="6202f-211">Пример SysTime</span><span class="sxs-lookup"><span data-stu-id="6202f-211">SysTime sample</span></span>  
 <span data-ttu-id="6202f-212">В этом примере показано, как передать указатель на класс в неуправляемую функцию, ожидающую указатель на структуру.</span><span class="sxs-lookup"><span data-stu-id="6202f-212">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>  
  
 <span data-ttu-id="6202f-213">В примере используется следующая неуправляемая функция, показанная с исходным объявлением:</span><span class="sxs-lookup"><span data-stu-id="6202f-213">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
- <span data-ttu-id="6202f-214">функция **GetSystemTime**, экспортированная из Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="6202f-214">**GetSystemTime** exported from Kernel32.dll.</span></span>  
  
    ```  
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);  
    ```  
  
 <span data-ttu-id="6202f-215">Исходная структура, переданная в функцию, содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6202f-215">The original structure passed to the function contains the following elements:</span></span>  
  
```  
typedef struct _SYSTEMTIME {   
    WORD wYear;   
    WORD wMonth;   
    WORD wDayOfWeek;   
    WORD wDay;   
    WORD wHour;   
    WORD wMinute;   
    WORD wSecond;   
    WORD wMilliseconds;   
} SYSTEMTIME, *PSYSTEMTIME;  
```  
  
 <span data-ttu-id="6202f-216">В этом примере класс `SystemTime` содержит элементы исходной структуры, представленные в виде членов класса.</span><span class="sxs-lookup"><span data-stu-id="6202f-216">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="6202f-217">Чтобы гарантировать последовательное размещение членов в памяти в порядке их появления, применяется атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="6202f-217">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="6202f-218">Класс `LibWrap` содержит управляемый прототип метода `GetSystemTime`, который по умолчанию передает класс `SystemTime` в качестве параметра In или Out.</span><span class="sxs-lookup"><span data-stu-id="6202f-218">The `LibWrap` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="6202f-219">Этот параметр должен быть объявлен с атрибутами <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>, так как классы, являющиеся ссылочными типами, по умолчанию передаются как параметры In.</span><span class="sxs-lookup"><span data-stu-id="6202f-219">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="6202f-220">Чтобы вызывающий объект получал результаты, необходимо явным образом применить [атрибуты направления](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6202f-220">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="6202f-221">Класс `App` создает экземпляр класса `SystemTime` и осуществляет доступ к его полям данных.</span><span class="sxs-lookup"><span data-stu-id="6202f-221">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>  
  
### <a name="code-samples"></a><span data-ttu-id="6202f-222">Примеры кода</span><span class="sxs-lookup"><span data-stu-id="6202f-222">Code Samples</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
 [!code-csharp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
 [!code-vb[Conceptual.Interop.Marshaling#25](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]  
  
## <a name="outarrayofstructs-sample"></a><span data-ttu-id="6202f-223">Пример OutArrayOfStructs </span><span class="sxs-lookup"><span data-stu-id="6202f-223">OutArrayOfStructs sample</span></span>  
 <span data-ttu-id="6202f-224">В этом примере показано, как передать в неуправляемую функцию массив структур, содержащий целочисленные значения и строки, в виде параметров Out.</span><span class="sxs-lookup"><span data-stu-id="6202f-224">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>  
  
 <span data-ttu-id="6202f-225">В этом примере демонстрируется, как вызывать собственную функцию с помощью класса <xref:System.Runtime.InteropServices.Marshal> и небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="6202f-225">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>  
  
 <span data-ttu-id="6202f-226">В примере используются функции-оболочки и вызовы неуправляемого кода, определенные в библиотеке [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) и содержащиеся в исходных файлах.</span><span class="sxs-lookup"><span data-stu-id="6202f-226">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="6202f-227">В нем используется функция `TestOutArrayOfStructs` и структура `MYSTRSTRUCT2`.</span><span class="sxs-lookup"><span data-stu-id="6202f-227">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="6202f-228">Структура содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6202f-228">The structure contains the following elements:</span></span>  
  
```  
typedef struct _MYSTRSTRUCT2  
{  
   char* buffer;  
   UINT size;   
} MYSTRSTRUCT2;  
```  
  
 <span data-ttu-id="6202f-229">Класс `MyStruct` содержит строковый объект из символов ANSI.</span><span class="sxs-lookup"><span data-stu-id="6202f-229">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="6202f-230">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> определяет формат ANSI.</span><span class="sxs-lookup"><span data-stu-id="6202f-230">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="6202f-231">`MyUnsafeStruct` — это структура, содержащая тип <xref:System.IntPtr> вместо строки.</span><span class="sxs-lookup"><span data-stu-id="6202f-231">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>  
  
 <span data-ttu-id="6202f-232">Класс `LibWrap` содержит перегруженный метод прототипа `TestOutArrayOfStructs`.</span><span class="sxs-lookup"><span data-stu-id="6202f-232">The `LibWrap` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="6202f-233">Если в качестве параметра метод объявляет указатель, класс должен быть помечен зарезервированным словом `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="6202f-233">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="6202f-234">Так как Visual Basic не может использовать небезопасный код, перегруженный метод, модификатор unsafe и структуры `MyUnsafeStruct` не нужны.</span><span class="sxs-lookup"><span data-stu-id="6202f-234">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>  
  
 <span data-ttu-id="6202f-235">Класс `App` реализует метод `UsingMarshaling`, который выполняет все задачи, необходимые для передачи массива.</span><span class="sxs-lookup"><span data-stu-id="6202f-235">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="6202f-236">Чтобы указать, что данные передаются от вызываемого объекта к вызывающему, массив помечается зарезервированным словом `out` (`ByRef` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6202f-236">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="6202f-237">Реализация использует следующие методы класса <xref:System.Runtime.InteropServices.Marshal>:</span><span class="sxs-lookup"><span data-stu-id="6202f-237">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>  
  
- <span data-ttu-id="6202f-238">метод <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> для маршалинга данных из неуправляемого буфера в управляемый объект;</span><span class="sxs-lookup"><span data-stu-id="6202f-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>  
  
- <span data-ttu-id="6202f-239">метод <xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> для освобождения памяти, зарезервированной для строк структуры;</span><span class="sxs-lookup"><span data-stu-id="6202f-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>  
  
- <span data-ttu-id="6202f-240">метод <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> для освобождения памяти, зарезервированной для массива.</span><span class="sxs-lookup"><span data-stu-id="6202f-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>  
  
 <span data-ttu-id="6202f-241">Как упоминалось ранее, C# допускает небезопасный код, который Visual Basic не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="6202f-241">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="6202f-242">В примере кода C# `UsingUnsafePointer` является альтернативной реализацией метода, в которой для обратной передачи массива, содержащего структуру `MyUnsafeStruct`, вместо класса <xref:System.Runtime.InteropServices.Marshal> используются указатели.</span><span class="sxs-lookup"><span data-stu-id="6202f-242">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="6202f-243">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="6202f-243">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
 [!code-csharp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
 [!code-vb[Conceptual.Interop.Marshaling#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]  
  
### <a name="calling-functions"></a><span data-ttu-id="6202f-244">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="6202f-244">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
 [!code-csharp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
 [!code-vb[Conceptual.Interop.Marshaling#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="6202f-245">См. также</span><span class="sxs-lookup"><span data-stu-id="6202f-245">See also</span></span>

- [<span data-ttu-id="6202f-246">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="6202f-246">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="6202f-247">Mаршалинг строк</span><span class="sxs-lookup"><span data-stu-id="6202f-247">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="6202f-248">Маршалинг различных типов массивов</span><span class="sxs-lookup"><span data-stu-id="6202f-248">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)
