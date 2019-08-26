---
title: '#Справочник по C#. #pragma checksum'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 4103b6262fc5085c1204f423a36c9c5c2053b497
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605650"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="b9746-102">#pragma checksum (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b9746-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="b9746-103">Создает контрольные суммы для исходных файлов, чтобы помочь с отладкой страниц ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b9746-103">Generates checksums for source files to aid with debugging ASP.NET pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9746-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9746-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9746-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9746-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="b9746-106">Имя файла, который требует отслеживания изменений или обновлений.</span><span class="sxs-lookup"><span data-stu-id="b9746-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="b9746-107">Глобальный уникальный идентификатор (GUID) для хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="b9746-107">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="b9746-108">Строка шестнадцатеричных цифр, представляющая байты контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="b9746-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="b9746-109">Должно быть четным числом шестнадцатеричных цифр.</span><span class="sxs-lookup"><span data-stu-id="b9746-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="b9746-110">Нечетное число цифр вызовет предупреждение во время компиляции, и директива будет пропущена.</span><span class="sxs-lookup"><span data-stu-id="b9746-110">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9746-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9746-111">Remarks</span></span>  
 <span data-ttu-id="b9746-112">Отладчик Visual Studio использует контрольную сумму, чтобы подтвердить нахождение правильного источника.</span><span class="sxs-lookup"><span data-stu-id="b9746-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="b9746-113">Компилятор вычисляет контрольную сумму для исходного файла, а затем передает результат в файл базы данных (PDB) программы.</span><span class="sxs-lookup"><span data-stu-id="b9746-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="b9746-114">Отладчик затем использует PDB-файл для сравнения с контрольной суммой, вычисленной им для исходного файла.</span><span class="sxs-lookup"><span data-stu-id="b9746-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="b9746-115">Это решение не работает для проектов ASP.NET, так как рассчитанная контрольная сумма относится к созданному исходному файлу, а не файлу ASPX.</span><span class="sxs-lookup"><span data-stu-id="b9746-115">This solution does not work for ASP.NET projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="b9746-116">Чтобы решить эту проблему, `#pragma checksum` предоставляет поддержку контрольных сумм для страниц ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b9746-116">To address this problem, `#pragma checksum` provides checksum support for ASP.NET pages.</span></span>  
  
 <span data-ttu-id="b9746-117">При создании проекта ASP.NET в Visual C# созданный исходный файл содержит контрольную сумму для ASPX-файла, из которого создается источник.</span><span class="sxs-lookup"><span data-stu-id="b9746-117">When you create an ASP.NET project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="b9746-118">Затем компилятор записывает эти данные в PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="b9746-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="b9746-119">Если компилятор не обнаруживает директиву `#pragma checksum` в файле, он вычисляет контрольную сумму и записывает значение в PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="b9746-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9746-120">Пример</span><span class="sxs-lookup"><span data-stu-id="b9746-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9746-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b9746-121">See also</span></span>

- [<span data-ttu-id="b9746-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b9746-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b9746-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b9746-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b9746-124">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="b9746-124">C# Preprocessor Directives</span></span>](./index.md)
