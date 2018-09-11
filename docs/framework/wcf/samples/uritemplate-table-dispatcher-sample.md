---
title: Пример диспетчера таблицы UriTemplate
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 4a4f725e88e014da241e1042c27bfee270e13268
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44337412"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="2a063-102">Пример диспетчера таблицы UriTemplate</span><span class="sxs-lookup"><span data-stu-id="2a063-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="2a063-103">Класс <xref:System.UriTemplateTable> предоставляет структуру ассоциативной таблицы, подобную словарю, для работы с набором экземпляров <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="2a063-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="2a063-104">В этом примере показан базовый механизм диспетчеризации, построенный с использованием класса `UriTemplateTable`, стандартный сценарий использования класса `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="2a063-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="2a063-105">Данный пример демонстрирует следующие ключевые понятия, связанные с классом `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="2a063-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="2a063-106">Связывание делегатов с `UriTemplates` в `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="2a063-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="2a063-107">Получение правильного делегата обработчика для заданного универсального кода ресурса (URI) с помощью метода <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a063-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
-   <span data-ttu-id="2a063-108">Вызов делегата обработчика для обработки запроса.</span><span class="sxs-lookup"><span data-stu-id="2a063-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2a063-109">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="2a063-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2a063-110">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a063-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="2a063-111">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a063-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a063-112">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2a063-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a063-113">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2a063-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a063-114">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="2a063-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a063-115">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="2a063-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="2a063-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2a063-116">See Also</span></span>  
 [<span data-ttu-id="2a063-117">Таблица UriTemplate</span><span class="sxs-lookup"><span data-stu-id="2a063-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="2a063-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="2a063-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
