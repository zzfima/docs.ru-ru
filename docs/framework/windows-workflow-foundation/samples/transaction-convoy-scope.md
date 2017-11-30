---
title: "Область сопровождения транзакции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b5fc8834fb72163a615633d81232e25768683278
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="transaction-convoy-scope"></a><span data-ttu-id="1e081-102">Область сопровождения транзакции</span><span class="sxs-lookup"><span data-stu-id="1e081-102">Transaction Convoy Scope</span></span>
<span data-ttu-id="1e081-103">В этом образце демонстрируется создание шаблона обмена сообщениями Parallel Convoy совместно с <xref:System.ServiceModel.Activities.TransactedReceiveScope> для моделирования протокола, при котором несколько операций могут выполняться в любом порядке в рамках одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="1e081-103">This sample demonstrates how to create a Parallel Convoy messaging activity pattern in conjunction with a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to model a protocol where a number of operations can happen in any order all under the same transaction.</span></span> <span data-ttu-id="1e081-104">Также в этом образце показано, как класс <xref:System.ServiceModel.Activities.TransactedReceiveScope> автоматически создает новую транзакцию, если транзакция не была передана серверу, и клиент не смог воспользоваться какими-либо транзакциями.</span><span class="sxs-lookup"><span data-stu-id="1e081-104">This sample also demonstrates how a <xref:System.ServiceModel.Activities.TransactedReceiveScope> automatically creates a new transaction when one is not flowed to the server, so the client does not make use of any transactions.</span></span>  
  
 <span data-ttu-id="1e081-105">Образец включает два проекта рабочих процессов, которые представляют клиент и сервер.</span><span class="sxs-lookup"><span data-stu-id="1e081-105">The sample consists of two workflow projects that represent the client and server.</span></span> <span data-ttu-id="1e081-106">Проект клиента запускает рабочий процесс, который начинается с отправки сообщения для загрузки рабочего процесса сервера, инициализирующего корреляцию и область транзакций для оставшихся действий по отправке и получению сообщений.</span><span class="sxs-lookup"><span data-stu-id="1e081-106">The client project runs a workflow that begins by sending a message to bootstrap the server workflow, which initializes a correlation and starts a transactional scope for the remainder of the messaging activities.</span></span> <span data-ttu-id="1e081-107">Клиентское действие <xref:System.Activities.Statements.Sequence> содержит исходную пару <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.ReceiveReply> и далее - действие <xref:System.Activities.Statements.Parallel> с тремя ответвлениями.</span><span class="sxs-lookup"><span data-stu-id="1e081-107">The client <xref:System.Activities.Statements.Sequence> activity contains an initial <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> pair and then a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="1e081-108">Каждое ответвление отправляет на сервер одностороннее сообщение.</span><span class="sxs-lookup"><span data-stu-id="1e081-108">Each branch sends a one-way message to the server.</span></span> <span data-ttu-id="1e081-109">Свойство <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> действия <xref:System.Activities.Statements.Parallel> устанавливается в значение `false`, таким образом, выполняются все три ответвления.</span><span class="sxs-lookup"><span data-stu-id="1e081-109">The <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> property of the <xref:System.Activities.Statements.Parallel> activity is set to `false` so that all three branches complete.</span></span>  
  
 <span data-ttu-id="1e081-110">Серверный рабочий процесс похож на клиентский рабочий процесс, за исключением действий отправки и получения сообщений, которые направлены в сторону сервера и содержатся в действии <xref:System.ServiceModel.Activities.TransactedReceiveScope>, за счет чего вся работа выполняется в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="1e081-110">The server workflow is similar to the client workflow except the messaging activities are oriented towards the server side of the communication and they are contained within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity so that all work done executes under the same transaction.</span></span> <span data-ttu-id="1e081-111">Когда сервер получает первое сообщение, создается транзакция, которая становится внешней для области <xref:System.ServiceModel.Activities.TransactedReceiveScope>, благодаря чему любое действие в этой области может получить доступ к транзакции.</span><span class="sxs-lookup"><span data-stu-id="1e081-111">When the first message is received on the server, a transaction is created and is made ambient for the scope of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body so that any activity within this scope can access the transaction.</span></span> <span data-ttu-id="1e081-112">После этого все действия получения выполняются параллельно.</span><span class="sxs-lookup"><span data-stu-id="1e081-112">After this, all receives execute in parallel.</span></span> <span data-ttu-id="1e081-113">Все действия получения должны быть выполнены строго один раз, в соответствии с условием завершения для параллельного действия.</span><span class="sxs-lookup"><span data-stu-id="1e081-113">All receives must execute exactly once as described by the completion condition on the parallel activity.</span></span> <span data-ttu-id="1e081-114">Неявная точка сохранения существует в конце области <xref:System.ServiceModel.Activities.TransactedReceiveScope>, при этом операция сохранения также выполняется в рамках той же транзакции.</span><span class="sxs-lookup"><span data-stu-id="1e081-114">An implicit persistence point exists at the end of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body and the persistence operation is also executed under the same transaction.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1e081-115">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="1e081-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="1e081-116">Откройте файл решения ParallelConvoySample.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e081-116">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ParallelConvoySample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="1e081-117">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="1e081-117">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1e081-118">Убедитесь, что оба проекта готовы к запуску.</span><span class="sxs-lookup"><span data-stu-id="1e081-118">Ensure both projects are set to start.</span></span>  
  
    1.  <span data-ttu-id="1e081-119">В **обозревателе решений**, щелкните правой кнопкой мыши решение и выберите **назначить запускаемые проекты**.</span><span class="sxs-lookup"><span data-stu-id="1e081-119">In **Solution Explorer**, right-click the solution and select **Set Startup Projects**.</span></span>  
  
    2.  <span data-ttu-id="1e081-120">Выберите **несколько запускаемых проектов** и убедитесь, что для обоих проектов задано действие **запустить**.</span><span class="sxs-lookup"><span data-stu-id="1e081-120">Select **Multiple Startup Projects** and ensure the action for both projects is set to **Start**.</span></span>  
  
4.  <span data-ttu-id="1e081-121">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="1e081-121">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="1e081-122">Сервер отобразит сообщение `Server is running`, указывающее, что сервер готов.</span><span class="sxs-lookup"><span data-stu-id="1e081-122">The server prints `Server is running`, which indicates the server is ready.</span></span>  
  
     <span data-ttu-id="1e081-123">Нажмите любую клавишу в окне консоли клиента, чтобы запустить образец.</span><span class="sxs-lookup"><span data-stu-id="1e081-123">Press any key in the client console window to start the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e081-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1e081-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e081-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1e081-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1e081-126">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e081-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e081-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1e081-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`  
  
## <a name="see-also"></a><span data-ttu-id="1e081-128">См. также</span><span class="sxs-lookup"><span data-stu-id="1e081-128">See Also</span></span>
