---
title: Действие OperationScope
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3bf92d7a726a53c5d625f31b0386e11c941cdde9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="operationscope"></a><span data-ttu-id="af5e7-102">Действие OperationScope</span><span class="sxs-lookup"><span data-stu-id="af5e7-102">OperationScope</span></span>
<span data-ttu-id="af5e7-103">В этом образце демонстрируется использование действий по обмену сообщениями <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> для представления существующего пользовательского действия в качестве операции в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="af5e7-103">This sample demonstrates how the messaging activities, <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> can be used to expose an existing custom activity as an operation in a workflow service.</span></span> <span data-ttu-id="af5e7-104">Этот пример включает новое пользовательское действие, названное `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="af5e7-104">This sample includes a new custom activity called an `OperationScope`.</span></span> <span data-ttu-id="af5e7-105">Оно предназначено для облегчения разработки службы рабочего процесса, позволяя пользователям отдельно записывать текст их операций как пользовательские действия, а затем представляя их как операции службы, использующие действие `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="af5e7-105">It is intended to ease the development of a workflow service by allowing users to author the body of their operations separately as custom activities and then easily exposing them as service operations using the `OperationScope` activity.</span></span> <span data-ttu-id="af5e7-106">Например, пользовательское действие `Add`, которое принимает два аргумента `in` и возвращает один аргумент `out`, может быть представлено как операция `Add` в рабочем процессе путем перетаскивания его в область `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="af5e7-106">For example, a custom `Add` activity that takes two `in` arguments and returns one `out` argument could be exposed as an `Add` operation on the workflow service by dropping it into an `OperationScope`.</span></span>  
  
 <span data-ttu-id="af5e7-107">Область работает, проверяя действие, предоставленное как ее текст.</span><span class="sxs-lookup"><span data-stu-id="af5e7-107">The scope works by inspecting the activity provided as its body.</span></span> <span data-ttu-id="af5e7-108">Предполагается, что непривязанные аргументы `in` являются входными данными из входящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="af5e7-108">Any unbound `in` arguments are assumed to be inputs from the incoming message.</span></span> <span data-ttu-id="af5e7-109">Предполагается, что все аргументы `out`, независимо от того, являются ли они привязанными, являются выходными данными в последующем ответном сообщении.</span><span class="sxs-lookup"><span data-stu-id="af5e7-109">All `out` arguments, regardless of whether they are bound, are assumed to be outputs in the subsequent reply message.</span></span> <span data-ttu-id="af5e7-110">Имя предоставляемой операции берется на основе отображаемого имени действия `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="af5e7-110">The exposed operation’s name is taken from the display name of the `OperationScope` activity.</span></span> <span data-ttu-id="af5e7-111">Конечным результатом является действие текста, упакованное в <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> с параметрами из сообщений, привязанных к аргументам действия.</span><span class="sxs-lookup"><span data-stu-id="af5e7-111">The end result is that the body activity is wrapped in a <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> with the parameters from the messages bound to the arguments of the activity.</span></span>  
  
 <span data-ttu-id="af5e7-112">В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP.</span><span class="sxs-lookup"><span data-stu-id="af5e7-112">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="af5e7-113">Для запуска должны быть добавлены правильные списки URL-адресов ACL.</span><span class="sxs-lookup"><span data-stu-id="af5e7-113">To run, proper URL ACLs must be added.</span></span> <span data-ttu-id="af5e7-114">Дополнительные сведения см. в разделе [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span><span class="sxs-lookup"><span data-stu-id="af5e7-114">For more information, see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="af5e7-115">Выполнив следующую команду в командной строке с повышенными привилегиями добавляет соответствующие ACL (Убедитесь, заменены домен и имя пользователя для домена %\\% UserName %).</span><span class="sxs-lookup"><span data-stu-id="af5e7-115">Executing the following command at an elevated prompt adds the appropriate ACLs (ensure that your Domain and Username are substituted for %DOMAIN%\\%UserName%).</span></span>  
  
 <span data-ttu-id="af5e7-116">**добавить urlacl url-адрес Netsh http =http://+:8000/ пользователь = % DOMAIN %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="af5e7-116">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="af5e7-117">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="af5e7-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="af5e7-118">Откройте решение OperationScope.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af5e7-118">Open the OperationScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="af5e7-119">Задайте несколько запускаемых проектов, щелкните правой кнопкой мыши решение в обозревателе решений и выбрав **назначить запускаемые проекты**.</span><span class="sxs-lookup"><span data-stu-id="af5e7-119">Set multiple start-up projects by right-clicking the solution in Solution Explorer and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="af5e7-120">Добавьте Scenario и Scenario_Client (в этом порядке) в качестве запускаемых проектов.</span><span class="sxs-lookup"><span data-stu-id="af5e7-120">Add Scenario and Scenario_Client (in that order) as multiple start-up projects.</span></span>  
  
3.  <span data-ttu-id="af5e7-121">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="af5e7-121">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="af5e7-122">Этот шаг является обязательным для просмотра рабочего процесса BankService.xaml из-за пользовательского действия `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="af5e7-122">This step is required to view the BankService.xaml workflow due to the custom activity `OperationScope`.</span></span>  
  
4.  <span data-ttu-id="af5e7-123">Нажмите CTRL+F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="af5e7-123">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="af5e7-124">На консоли Scenario_Client запрашиваются входные данные, и соответствующий вывод виден на консоли Scenario.</span><span class="sxs-lookup"><span data-stu-id="af5e7-124">The Scenario_Client console prompts you for inputs and the corresponding output is seen in the Scenario console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af5e7-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="af5e7-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="af5e7-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="af5e7-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="af5e7-127">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="af5e7-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="af5e7-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="af5e7-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`