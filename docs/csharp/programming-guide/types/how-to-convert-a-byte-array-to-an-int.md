---
title: Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: 4e8c232a604837d32675229f7f91b8e329ac4b5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337877"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a><span data-ttu-id="ffdbb-102">Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ffdbb-102">How to: Convert a byte Array to an int (C# Programming Guide)</span></span>
<span data-ttu-id="ffdbb-103">В этом примере демонстрируется использование класса <xref:System.BitConverter> для преобразования массива байтов в значение типа [int](../../../csharp/language-reference/keywords/int.md) и обратно в массив байтов.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-103">This example shows you how to use the <xref:System.BitConverter> class to convert an array of bytes to an [int](../../../csharp/language-reference/keywords/int.md) and back to an array of bytes.</span></span> <span data-ttu-id="ffdbb-104">Например, может потребоваться преобразование из байтов во встроенный тип данных после чтения байтов из сети.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-104">You may have to convert from bytes to a built-in data type after you read bytes off the network, for example.</span></span> <span data-ttu-id="ffdbb-105">В дополнение к методу [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)), показанному в примере, для преобразования байтов (из массива байтов) в другие встроенные типы данных можно использовать и другие методы класса <xref:System.BitConverter>, представленные в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-105">In addition to the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method in the example, the following table lists methods in the <xref:System.BitConverter> class that convert bytes (from an array of bytes) to other built-in types.</span></span>  
  
|<span data-ttu-id="ffdbb-106">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="ffdbb-106">Type returned</span></span>|<span data-ttu-id="ffdbb-107">Метод</span><span class="sxs-lookup"><span data-stu-id="ffdbb-107">Method</span></span>|  
|-------------------|------------|  
|`bool`|<span data-ttu-id="ffdbb-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span></span>|  
|`char`|<span data-ttu-id="ffdbb-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span></span>|  
|`double`|<span data-ttu-id="ffdbb-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span></span>|  
|`short`|<span data-ttu-id="ffdbb-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span></span>|  
|`int`|<span data-ttu-id="ffdbb-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span></span>|  
|`long`|<span data-ttu-id="ffdbb-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span></span>|  
|`float`|<span data-ttu-id="ffdbb-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span></span>|  
|`ushort`|<span data-ttu-id="ffdbb-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span></span>|  
|`uint`|<span data-ttu-id="ffdbb-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span></span>|  
|`ulong`|<span data-ttu-id="ffdbb-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="ffdbb-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ffdbb-118">Пример</span><span class="sxs-lookup"><span data-stu-id="ffdbb-118">Example</span></span>  
 <span data-ttu-id="ffdbb-119">Этот пример инициализирует массив байтов, обращает порядок расположения элементов в массиве, если в архитектуре компьютера используется прямой порядок байтов (т. е. первым сохраняется наименее значащий байт), и затем вызывает метод [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) для преобразования четырех байтов массива в значение типа `int`.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-119">This example initializes an array of bytes, reverses the array if the computer architecture is little-endian (that is, the least significant byte is stored first), and then calls the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method to convert four bytes in the array to an `int`.</span></span> <span data-ttu-id="ffdbb-120">Второй аргумент [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) указывает начальный индекс массива байтов.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-120">The second argument to [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifies the start index of the array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffdbb-121">Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-121">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="ffdbb-122">Пример</span><span class="sxs-lookup"><span data-stu-id="ffdbb-122">Example</span></span>  
 <span data-ttu-id="ffdbb-123">В этом примере вызывается метод <xref:System.BitConverter.GetBytes%28System.Int32%29> класса <xref:System.BitConverter> для преобразования значения `int` в массив байтов.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-123">In this example, the <xref:System.BitConverter.GetBytes%28System.Int32%29> method of the <xref:System.BitConverter> class is called to convert an `int` to an array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffdbb-124">Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.</span><span class="sxs-lookup"><span data-stu-id="ffdbb-124">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ffdbb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ffdbb-125">See Also</span></span>  
 <xref:System.BitConverter>  
 <xref:System.BitConverter.IsLittleEndian>  
 [<span data-ttu-id="ffdbb-126">Типы</span><span class="sxs-lookup"><span data-stu-id="ffdbb-126">Types</span></span>](../../../csharp/programming-guide/types/index.md)
