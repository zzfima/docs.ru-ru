---
title: Кэширование канала и операция Send
ms.date: 03/30/2017
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
ms.openlocfilehash: 619088def1f5e443a31244516655d75d1e25c9cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503819"
---
# <a name="channel-caching-with-send"></a><span data-ttu-id="6a5a8-102">Кэширование канала и операция Send</span><span class="sxs-lookup"><span data-stu-id="6a5a8-102">Channel Caching with Send</span></span>
<span data-ttu-id="6a5a8-103">Объект <xref:System.ServiceModel.Activities.SendMessageChannelCache> позволяет пользователям использовать различные уровни кэширования канала для действий <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.SendParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> enables users to have different levels of channel caching with <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.SendParametersContent> activities.</span></span> <span data-ttu-id="6a5a8-104">Кэширование на уровне экземпляра включено по умолчанию. Данный образец иллюстрирует перечисленные далее возможности.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-104">Instance-level caching is enabled by default and this sample demonstrates the following features:</span></span>  
  
1.  <span data-ttu-id="6a5a8-105">Совместное использование <xref:System.ServiceModel.Activities.SendMessageChannelCache> в домене приложений.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-105">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> across an application domain.</span></span>  
  
2.  <span data-ttu-id="6a5a8-106">Отключение кэширования канала.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-106">Disable channel caching.</span></span>  
  
3.  <span data-ttu-id="6a5a8-107">Совместное использование <xref:System.ServiceModel.Activities.SendMessageChannelCache> экземплярами рабочих процессов на узле <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-107">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> among workflow instances in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6a5a8-108">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="6a5a8-108">Demonstrates</span></span>  
 <span data-ttu-id="6a5a8-109">Расширение <xref:System.ServiceModel.Activities.SendMessageChannelCache>, действия <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> и <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache> extension, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6a5a8-110">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="6a5a8-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6a5a8-111">Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="6a5a8-112">Запустите приложение EchoWorkflowService, созданное в папке «\EchoWorkflowService\bin\debug».</span><span class="sxs-lookup"><span data-stu-id="6a5a8-112">Run the EchoWorkflowService application generated in \EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="6a5a8-113">Запустите приложение EchoWorkflowClient, созданное в папке «.\EchoWorkflowClient\bin\debug».</span><span class="sxs-lookup"><span data-stu-id="6a5a8-113">Run the EchoWorkflowClient application generated in .\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="6a5a8-114">Клиент вызывает операцию Echo применительно к службе и печатает результаты.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-114">The client calls the Echo operation on the service and prints the results.</span></span> <span data-ttu-id="6a5a8-115">После того как результаты распечатаны, нажмите клавишу ВВОД, чтобы закрыть клиент и службу.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-115">When the results have been printed, press ENTER to exit the client and the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a5a8-116">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6a5a8-117">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6a5a8-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6a5a8-118">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6a5a8-119">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6a5a8-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
