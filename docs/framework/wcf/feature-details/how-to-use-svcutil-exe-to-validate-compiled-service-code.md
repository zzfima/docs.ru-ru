---
title: Практическое руководство. Использование программы Svcutil.exe для проверки скомпилированного кода службы
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 599f5624b7eb0c32cbcc0a78e6c7f989ce470b58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038757"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="63ad6-102">Практическое руководство. Использование программы Svcutil.exe для проверки скомпилированного кода службы</span><span class="sxs-lookup"><span data-stu-id="63ad6-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="63ad6-103">Можно использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для обнаружения ошибок в реализациях службы и конфигурациях без размещения службы.</span><span class="sxs-lookup"><span data-stu-id="63ad6-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="63ad6-104">Проверка службы</span><span class="sxs-lookup"><span data-stu-id="63ad6-104">To validate a service</span></span>  
  
1. <span data-ttu-id="63ad6-105">Скомпилируйте службу в исполняемый файл и одну или более зависимых сборок.</span><span class="sxs-lookup"><span data-stu-id="63ad6-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="63ad6-106">Откройте окно командной строки SDK.</span><span class="sxs-lookup"><span data-stu-id="63ad6-106">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="63ad6-107">Из командной строки запустите средство Svcutil.exe, используя следующий формат.</span><span class="sxs-lookup"><span data-stu-id="63ad6-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="63ad6-108">Дополнительные сведения о различных параметрах см. в разделе Validationsection службы из [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="63ad6-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="63ad6-109">Чтобы указать имя конфигурации службы для проверки, необходимо использовать параметр `/serviceName`.</span><span class="sxs-lookup"><span data-stu-id="63ad6-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="63ad6-110">Аргумент `assemblyPath` задает путь к исполняемому файлу для службы и одной или более сборок, которые содержат типы службы для проверки.</span><span class="sxs-lookup"><span data-stu-id="63ad6-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="63ad6-111">Исполняемая сборка должна содержать связанный файл конфигурации для предоставления конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="63ad6-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="63ad6-112">Для предоставления нескольких сборок можно использовать стандартные подстановочные знаки командной строки.</span><span class="sxs-lookup"><span data-stu-id="63ad6-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63ad6-113">Пример</span><span class="sxs-lookup"><span data-stu-id="63ad6-113">Example</span></span>  
 <span data-ttu-id="63ad6-114">Следующая команда проверяет службу myServiceName, реализованную в исполняемом файле myServiceHost.exe.</span><span class="sxs-lookup"><span data-stu-id="63ad6-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="63ad6-115">Автоматически загружается файл конфигурации для этой службы (myServiceHost.exe.config).</span><span class="sxs-lookup"><span data-stu-id="63ad6-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="63ad6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="63ad6-116">See also</span></span>

- [<span data-ttu-id="63ad6-117">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="63ad6-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
