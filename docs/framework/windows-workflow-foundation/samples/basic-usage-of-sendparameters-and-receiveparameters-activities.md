---
title: "Основное использование действий SendParameters и ReceiveParameters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9c3b6f189f1a2564662af89961c9363f025ae8c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="b6574-102">Основное использование действий SendParameters и ReceiveParameters</span><span class="sxs-lookup"><span data-stu-id="b6574-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="b6574-103">В этом образце показано использование действий <xref:System.ServiceModel.Activities.SendParametersContent> и <xref:System.ServiceModel.Activities.ReceiveParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="b6574-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="b6574-104">Служба предоставляет одну операцию, которая принимает строковый аргумент и возвращает его клиенту.</span><span class="sxs-lookup"><span data-stu-id="b6574-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="b6574-105">В образце показано, как установить параметры для этих действий обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b6574-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b6574-106">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b6574-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b6574-107">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b6574-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b6574-108">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6574-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b6574-109">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b6574-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="b6574-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="b6574-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="b6574-111">Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="b6574-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="b6574-112">Сначала запустите приложение EchoWorkflowService, сформированное в [основной каталог решения]\EchoWorkflowService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="b6574-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="b6574-113">Затем запустите приложение EchoWorkflowClient, сформированное в [основной каталог решения]\EchoWorkflowClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="b6574-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="b6574-114">Клиент вызывает операцию Echo на службе и печатает результаты.</span><span class="sxs-lookup"><span data-stu-id="b6574-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="b6574-115">После завершения нажмите клавишу ВВОД, чтобы закрыть клиент и службу.</span><span class="sxs-lookup"><span data-stu-id="b6574-115">When complete, press ENTER to exit the client and then the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6574-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b6574-116">See Also</span></span>
