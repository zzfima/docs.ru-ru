---
title: Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: b85bacff093c268cd35dca2ede36e6ceb74ca4d1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251408"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="2546e-102">Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня</span><span class="sxs-lookup"><span data-stu-id="2546e-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="2546e-103">В этом разделе показано, как использовать средство [генератора EDM (EdmGen. exe)](edm-generator-edmgen-exe.md) для создания кода уровня объекта на основе CSDL-файла.</span><span class="sxs-lookup"><span data-stu-id="2546e-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="2546e-104">Создание кода уровня объекта для модели School в проекте Visual Basic с помощью EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="2546e-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="2546e-105">Создайте базу данных School.</span><span class="sxs-lookup"><span data-stu-id="2546e-105">Create the School database.</span></span> <span data-ttu-id="2546e-106">Дополнительные сведения см. [в разделе Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2546e-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="2546e-107">Создайте модель School или получите файл School.csdl.</span><span class="sxs-lookup"><span data-stu-id="2546e-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="2546e-108">Дополнительные сведения см. в разделе [Практическое руководство. Используйте EdmGen. exe для создания файлов](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2546e-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="2546e-109">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="2546e-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="2546e-110">Создание кода уровня объектов для модели School в проекте С# с помощью программы EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="2546e-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="2546e-111">Создайте базу данных School.</span><span class="sxs-lookup"><span data-stu-id="2546e-111">Create the School database.</span></span> <span data-ttu-id="2546e-112">Дополнительные сведения см. [в разделе Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2546e-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="2546e-113">Создайте модель School или получите файл School.csdl.</span><span class="sxs-lookup"><span data-stu-id="2546e-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="2546e-114">Дополнительные сведения см. в разделе [Практическое руководство. Используйте EdmGen. exe для создания файлов](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2546e-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="2546e-115">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="2546e-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2546e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2546e-116">See also</span></span>

- [<span data-ttu-id="2546e-117">Моделирование и сопоставление</span><span class="sxs-lookup"><span data-stu-id="2546e-117">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- <span data-ttu-id="2546e-118">[Практическое руководство. Настройка проекта Entity Framework вручную](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2546e-118">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="2546e-119">[Средства работы с моделью EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2546e-119">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="2546e-120">[Практическое руководство. Предварительное создание представлений для повышения производительности запросов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2546e-120">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="2546e-121">Практическое руководство. Использование программы EdmGen. exe для создания файлов модели и сопоставления</span><span class="sxs-lookup"><span data-stu-id="2546e-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
