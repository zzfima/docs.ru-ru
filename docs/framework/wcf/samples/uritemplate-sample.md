---
title: "Пример UriTemplate"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 729a48fe0ea34bf1630824d941341fff82ade1ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="uritemplate-sample"></a><span data-ttu-id="dda36-102">Пример UriTemplate</span><span class="sxs-lookup"><span data-stu-id="dda36-102">UriTemplate Sample</span></span>
<span data-ttu-id="dda36-103">Класс <xref:System.UriTemplate> предоставляет методы для работы с наборами кодов URI, использующих общую структуру.</span><span class="sxs-lookup"><span data-stu-id="dda36-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="dda36-104">Данный образец демонстрирует следующие ключевые понятия, связанные с `UriTemplate`.</span><span class="sxs-lookup"><span data-stu-id="dda36-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
-   <span data-ttu-id="dda36-105">Синтаксис создания шаблонов.</span><span class="sxs-lookup"><span data-stu-id="dda36-105">Syntax for creating templates.</span></span>  
  
-   <span data-ttu-id="dda36-106">Создание экземпляров кодов URI из шаблона `UriTemplate` с помощью методов <xref:System.UriTemplate.BindByName%2A> и <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="dda36-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
-   <span data-ttu-id="dda36-107">Метод <xref:System.UriTemplateTable.Match%2A>, являющийся обратной операцией для `BindByName` и `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="dda36-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dda36-108">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="dda36-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dda36-109">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dda36-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="dda36-110">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dda36-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dda36-111">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dda36-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dda36-112">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dda36-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dda36-113">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dda36-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dda36-114">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dda36-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="dda36-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dda36-115">See Also</span></span>  
 [<span data-ttu-id="dda36-116">Таблицы UriTemplate</span><span class="sxs-lookup"><span data-stu-id="dda36-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="dda36-117">Диспетчер таблицы UriTemplate</span><span class="sxs-lookup"><span data-stu-id="dda36-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
