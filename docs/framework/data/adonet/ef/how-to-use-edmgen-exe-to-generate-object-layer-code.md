---
title: "Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4abb20ca2ff26fa4e2105bae87274028592aa510
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="cda77-102">Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня</span><span class="sxs-lookup"><span data-stu-id="cda77-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="cda77-103">В этом разделе показано, как использовать [генератор модели EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) сформировать код уровня объекта на основе CSDL-файла.</span><span class="sxs-lookup"><span data-stu-id="cda77-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="cda77-104">Создание кода уровня объекта для модели School в проекте Visual Basic с помощью EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="cda77-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="cda77-105">Создайте базу данных School.</span><span class="sxs-lookup"><span data-stu-id="cda77-105">Create the School database.</span></span> <span data-ttu-id="cda77-106">Дополнительные сведения см. в разделе [Создание образца базы данных School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="cda77-106">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="cda77-107">Создайте модель School или получите файл School.csdl.</span><span class="sxs-lookup"><span data-stu-id="cda77-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="cda77-108">Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания модели и сопоставления файлов](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="cda77-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="cda77-109">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="cda77-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="cda77-110">Создание кода уровня объектов для модели School в проекте С# с помощью программы EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="cda77-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="cda77-111">Создайте базу данных School.</span><span class="sxs-lookup"><span data-stu-id="cda77-111">Create the School database.</span></span> <span data-ttu-id="cda77-112">Дополнительные сведения см. в разделе [Создание образца базы данных School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="cda77-112">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="cda77-113">Создайте модель School или получите файл School.csdl.</span><span class="sxs-lookup"><span data-stu-id="cda77-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="cda77-114">Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания модели и сопоставления файлов](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="cda77-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="cda77-115">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="cda77-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cda77-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cda77-116">See Also</span></span>  
 [<span data-ttu-id="cda77-117">Моделирование и сопоставление</span><span class="sxs-lookup"><span data-stu-id="cda77-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="cda77-118">Как: вручную настроить проект Entity Framework</span><span class="sxs-lookup"><span data-stu-id="cda77-118">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="cda77-119">Средства работы с моделью EDM ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cda77-119">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="cda77-120">Как: заранее создать представления для повышения производительности запросов</span><span class="sxs-lookup"><span data-stu-id="cda77-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="cda77-121">Как: использование EdmGen.exe для создания файлов модели и сопоставления</span><span class="sxs-lookup"><span data-stu-id="cda77-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
