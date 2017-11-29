---
title: "#<a name=\"pragma-checksum-c-reference\"></a>#pragma checksum (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#pragma checksum'
helpviewer_keywords: '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0604a559be25c300fcdc6041975306b465fc595f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="eb29f-102">#pragma checksum (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="eb29f-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="eb29f-103">Создание контрольных сумм для исходных файлов для помощи в отладке страниц [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb29f-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb29f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb29f-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb29f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb29f-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="eb29f-106">Имя файла, который требует отслеживания изменений или обновлений.</span><span class="sxs-lookup"><span data-stu-id="eb29f-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="eb29f-107">Глобальный уникальный идентификатор (GUID) для файла.</span><span class="sxs-lookup"><span data-stu-id="eb29f-107">The Globally Unique Identifier (GUID) for the file.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="eb29f-108">Строка шестнадцатеричных цифр, представляющая байты контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="eb29f-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="eb29f-109">Должно быть четным числом шестнадцатеричных цифр.</span><span class="sxs-lookup"><span data-stu-id="eb29f-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="eb29f-110">Нечетное число цифр приведет к выводу предупреждения во время компиляции, и директива будет пропущена.</span><span class="sxs-lookup"><span data-stu-id="eb29f-110">An odd number of digits results in a compile-time warning, and the directive are  ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb29f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb29f-111">Remarks</span></span>  
 <span data-ttu-id="eb29f-112">Отладчик Visual Studio использует контрольную сумму, чтобы подтвердить нахождение правильного источника.</span><span class="sxs-lookup"><span data-stu-id="eb29f-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="eb29f-113">Компилятор вычисляет контрольную сумму для исходного файла, а затем передает результат в файл базы данных (PDB) программы.</span><span class="sxs-lookup"><span data-stu-id="eb29f-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="eb29f-114">Отладчик затем использует PDB-файл для сравнения с контрольной суммой, вычисленной им для исходного файла.</span><span class="sxs-lookup"><span data-stu-id="eb29f-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="eb29f-115">Это решение не работает для проектов [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)], так как контрольная сумма вычисляется для созданного исходного файла, а не для ASPX-файла.</span><span class="sxs-lookup"><span data-stu-id="eb29f-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="eb29f-116">Чтобы решить эту проблему, `#pragma checksum` обеспечивает поддержку контрольных сумм для страниц [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb29f-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="eb29f-117">При создании проекта [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] в [!INCLUDE[csprcs](~/includes/csprcs-md.md)] созданный исходный файл содержит контрольную сумму для ASPX-файла, из которого создается источник.</span><span class="sxs-lookup"><span data-stu-id="eb29f-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in [!INCLUDE[csprcs](~/includes/csprcs-md.md)], the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="eb29f-118">Затем компилятор записывает эти данные в PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="eb29f-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="eb29f-119">Если компилятор не обнаруживает директиву `#pragma checksum` в файле, он вычисляет контрольную сумму и записывает значение в PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="eb29f-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb29f-120">Пример</span><span class="sxs-lookup"><span data-stu-id="eb29f-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb29f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="eb29f-121">See Also</span></span>  
 [<span data-ttu-id="eb29f-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="eb29f-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="eb29f-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="eb29f-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eb29f-124">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="eb29f-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
