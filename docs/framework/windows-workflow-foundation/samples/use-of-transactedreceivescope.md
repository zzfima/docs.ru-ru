---
title: "Использование TransactedReceiveScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc43f04da0404c309c727aef93b74faec5047ac6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="use-of-transactedreceivescope"></a><span data-ttu-id="1de06-102">Использование TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="1de06-102">Use of TransactedReceiveScope</span></span>
<span data-ttu-id="1de06-103">В этом образце показывается передача транзакции от клиента к серверу с использованием действия <xref:System.Activities.Statements.TransactionScope> для создания новой транзакции на клиенте и действия <xref:System.ServiceModel.Activities.TransactedReceiveScope> для получения сообщения с передаваемой транзакцией и определения времени ее существования на сервере.</span><span class="sxs-lookup"><span data-stu-id="1de06-103">This sample shows how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span> <span data-ttu-id="1de06-104">Образец состоит из двух проектов, исполняющих роли клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="1de06-104">The sample consists of two projects that fill the roles of client and server.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="1de06-105">Клиентское приложение</span><span class="sxs-lookup"><span data-stu-id="1de06-105">Client Application</span></span>  
 <span data-ttu-id="1de06-106">Клиентское приложение выполняет рабочий процесс, который выводит идентификатор распределенной транзакции, отсылает сообщение на сервер, передает транзакцию, получает ответ, снова выводит идентификатор распределенной транзакции и завершает свою работу.</span><span class="sxs-lookup"><span data-stu-id="1de06-106">The client application runs a workflow that prints the distributed transaction ID, sends a message to the server, flows the transaction, receives the reply, prints the distributed transaction ID again and completes.</span></span> <span data-ttu-id="1de06-107">При первоначальном выводе идентификатора распределенной транзакции это будет пустой идентификатор GUID, поскольку транзакция все еще является локальной.</span><span class="sxs-lookup"><span data-stu-id="1de06-107">When the distributed transaction ID is initially prints, it is an empty GUID as the transaction is still only local.</span></span>  
  
## <a name="server-application"></a><span data-ttu-id="1de06-108">Серверное приложение</span><span class="sxs-lookup"><span data-stu-id="1de06-108">Server Application</span></span>  
 <span data-ttu-id="1de06-109">Проект сервера схож, однако рабочий процесс размещен на узле <xref:System.ServiceModel.Activities.WorkflowServiceHost>, поскольку он должен прослушивать конечную точку на предмет получения сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="1de06-109">The server project is similar, however, the workflow is hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> because it must listen on an endpoint for the message from the client.</span></span> <span data-ttu-id="1de06-110">Рабочий процесс ориентирован на действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>, которое получает переданную транзакцию от клиента, выводит отправленное сообщение, выводит идентификатор распределенной транзакции и отправляет ответ клиенту.</span><span class="sxs-lookup"><span data-stu-id="1de06-110">The workflow is centered on the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, which receives the flowed transaction from the client, prints the message that was sent, prints the distributed transaction ID and sends the reply to the client.</span></span> <span data-ttu-id="1de06-111">Теперь идентификатор распределенной транзакции является не пустым идентификатором GUID; если в текст действия <xref:System.ServiceModel.Activities.TransactedReceiveScope> было добавлено поддерживающее транзакции действие, оно будет выполнено в переданной транзакции.</span><span class="sxs-lookup"><span data-stu-id="1de06-111">The distributed transaction ID is now a non-empty GUID and if a transaction-aware activity was added to the body of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, it would execute under the flowed transaction.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="1de06-112">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="1de06-112">To run the sample</span></span>  
  
1.  <span data-ttu-id="1de06-113">Откройте решение TransactedReceiveScope.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1de06-113">Open the TransactedReceiveScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1de06-114">Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="1de06-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="1de06-115">После успешного построения щелкните решение правой кнопкой мыши и выберите **назначить запускаемые проекты**.</span><span class="sxs-lookup"><span data-stu-id="1de06-115">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="1de06-116">В диалоговом окне выберите **несколько запускаемых проектов** и убедитесь, что для обоих проектов задано действие **запустить**.</span><span class="sxs-lookup"><span data-stu-id="1de06-116">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="1de06-117">Нажмите клавишу F5 или выберите **начать отладку** из **отладки** меню.</span><span class="sxs-lookup"><span data-stu-id="1de06-117">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="1de06-118">Кроме того, нажмите клавиши CTRL + F5 или выберите **Запуск без отладки** из **отладки** меню для запуска без отладки.</span><span class="sxs-lookup"><span data-stu-id="1de06-118">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1de06-119">Перед запуском клиента необходимо запустить сервер.</span><span class="sxs-lookup"><span data-stu-id="1de06-119">The server must be running prior to starting the client.</span></span> <span data-ttu-id="1de06-120">Вывод из окна консоли, в котором размещена служба, указывает, когда она начала работу.</span><span class="sxs-lookup"><span data-stu-id="1de06-120">The output from the console window hosting the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1de06-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1de06-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1de06-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1de06-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1de06-123">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1de06-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1de06-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1de06-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`