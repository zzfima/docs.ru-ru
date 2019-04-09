---
title: Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 1981e293d634af451a7084ac519a97f1ad5b5fd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076524"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="f99ec-102">Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления</span><span class="sxs-lookup"><span data-stu-id="f99ec-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="f99ec-103">В этом разделе показано, как использовать [генератор модели EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) средство для проверки файлов модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="f99ec-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="f99ec-104">Дополнительные сведения см. в разделе [модели EDM](../../../../../docs/framework/data/adonet/entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="f99ec-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="f99ec-105">Проверка модели School при помощи программы EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="f99ec-105">To validate the School model using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="f99ec-106">Создайте базу данных School.</span><span class="sxs-lookup"><span data-stu-id="f99ec-106">Create the School database.</span></span> <span data-ttu-id="f99ec-107">Дополнительные сведения см. в разделе [Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f99ec-107">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="f99ec-108">Сформируйте модель School.</span><span class="sxs-lookup"><span data-stu-id="f99ec-108">Generate the School model.</span></span> <span data-ttu-id="f99ec-109">Дополнительные сведения см. в разделе [Как Использование EdmGen.exe для создания файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="f99ec-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="f99ec-110">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f99ec-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f99ec-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f99ec-111">See also</span></span>

- [<span data-ttu-id="f99ec-112">Практическое руководство. вручную настроить проект Entity Framework</span><span class="sxs-lookup"><span data-stu-id="f99ec-112">How to: Manually Configure an Entity Framework Project</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [<span data-ttu-id="f99ec-113">Средства работы с моделью EDM ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f99ec-113">ADO.NET Entity Data Model Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [<span data-ttu-id="f99ec-114">Практическое руководство. предварительно создать представления для повышения производительности запросов</span><span class="sxs-lookup"><span data-stu-id="f99ec-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [<span data-ttu-id="f99ec-115">Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня</span><span class="sxs-lookup"><span data-stu-id="f99ec-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
