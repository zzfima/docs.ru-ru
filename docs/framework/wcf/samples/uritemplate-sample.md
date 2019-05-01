---
title: Пример UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 5f8a969a9ddea633d12ebe2d922c152dbb0d7241
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007621"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="c550a-102">Пример UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c550a-102">UriTemplate Sample</span></span>
<span data-ttu-id="c550a-103">Класс <xref:System.UriTemplate> предоставляет методы для работы с наборами кодов URI, использующих общую структуру.</span><span class="sxs-lookup"><span data-stu-id="c550a-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="c550a-104">Данный образец демонстрирует следующие ключевые понятия, связанные с `UriTemplate`.</span><span class="sxs-lookup"><span data-stu-id="c550a-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
- <span data-ttu-id="c550a-105">Синтаксис создания шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c550a-105">Syntax for creating templates.</span></span>  
  
- <span data-ttu-id="c550a-106">Создание экземпляров кодов URI из шаблона `UriTemplate` с помощью методов <xref:System.UriTemplate.BindByName%2A> и <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="c550a-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
- <span data-ttu-id="c550a-107">Метод <xref:System.UriTemplateTable.Match%2A>, являющийся обратной операцией для `BindByName` и `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="c550a-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c550a-108">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="c550a-108">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c550a-109">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c550a-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="c550a-110">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c550a-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c550a-111">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c550a-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c550a-112">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c550a-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c550a-113">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="c550a-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c550a-114">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c550a-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="c550a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c550a-115">See also</span></span>

- [<span data-ttu-id="c550a-116">Таблица UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c550a-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="c550a-117">Диспетчер таблицы UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c550a-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
