---
title: Практическое руководство. Включение сохраняемости для рабочих процессов и служб рабочих процессов
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 6a2a8d73298e14f92f376b97b9637db91532e937
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340156"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="c6f32-102">Практическое руководство. Включение сохраняемости для рабочих процессов и служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c6f32-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>
<span data-ttu-id="c6f32-103">В этом разделе описывается процесс включения сохраняемости для рабочих процессов и служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="c6f32-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>  
  
## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="c6f32-104">Включение сохраняемости для рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c6f32-104">Enable Persistence for Workflows</span></span>  
 <span data-ttu-id="c6f32-105">Можно связать хранилище экземпляров с **WorkflowApplication** с помощью <xref:System.Activities.WorkflowApplication.InstanceStore%2A> свойство <xref:System.Activities.WorkflowApplication> класса.</span><span class="sxs-lookup"><span data-stu-id="c6f32-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="c6f32-106">Метод <xref:System.Activities.WorkflowApplication.Persist%2A> сохраняет рабочий процесс в хранилище экземпляров, связанном с приложением.</span><span class="sxs-lookup"><span data-stu-id="c6f32-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="c6f32-107">Метод <xref:System.Activities.WorkflowApplication.Unload%2A> сохраняет рабочий процесс в хранилище экземпляров, а затем выгружает экземпляр из памяти.</span><span class="sxs-lookup"><span data-stu-id="c6f32-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="c6f32-108">**Нагрузки** метод загружает рабочий процесс в память с помощью рабочего процесса данные, хранящиеся в хранилище сохраняемости экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c6f32-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>  
  
 <span data-ttu-id="c6f32-109">**Persist** метод выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c6f32-109">The **Persist** method performs the following steps:</span></span>  
  
1. <span data-ttu-id="c6f32-110">Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.</span><span class="sxs-lookup"><span data-stu-id="c6f32-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2. <span data-ttu-id="c6f32-111">Сохраняет рабочий процесс в хранилище сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="c6f32-111">Persists or saves the workflow into the persistence store.</span></span>  
  
3. <span data-ttu-id="c6f32-112">Возобновляет работу планировщика рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="c6f32-112">Resumes the workflow scheduler.</span></span>  
  
 <span data-ttu-id="c6f32-113">**Unload** метод выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c6f32-113">The **Unload** method performs the following steps:</span></span>  
  
1. <span data-ttu-id="c6f32-114">Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.</span><span class="sxs-lookup"><span data-stu-id="c6f32-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2. <span data-ttu-id="c6f32-115">Сохраняет рабочий процесс в хранилище сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="c6f32-115">Persists or saves the workflow into the persistence store.</span></span>  
  
3. <span data-ttu-id="c6f32-116">Удаляет экземпляр рабочего процесса из памяти.</span><span class="sxs-lookup"><span data-stu-id="c6f32-116">Disposes the workflow instance in the memory.</span></span>  
  
 <span data-ttu-id="c6f32-117">Оба **Persist** и **Unload** методы будут блокироваться, пока рабочий процесс находится в зоне несохраняемости, пока рабочий процесс выходит из зоны несохраняемости.</span><span class="sxs-lookup"><span data-stu-id="c6f32-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="c6f32-118">Метод продолжает работу, выполняя операции сохранения или выгрузки после выхода из зоны несохраняемости.</span><span class="sxs-lookup"><span data-stu-id="c6f32-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="c6f32-119">Если зона несохраняемости не завершается до истечения времени ожидания или если процесс сохраняемости занимает слишком много времени, формируется исключение TimeoutException.</span><span class="sxs-lookup"><span data-stu-id="c6f32-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="c6f32-120">Включение сохраняемости для служб Workflow Services в коде</span><span class="sxs-lookup"><span data-stu-id="c6f32-120">Enable Persistence for Workflow Services in Code</span></span>  
 <span data-ttu-id="c6f32-121">**DurableInstancingOptions** членом <xref:System.ServiceModel.WorkflowServiceHost> класс имеет свойство с именем **InstanceStore** , можно использовать для связать хранилище экземпляров с **WorkflowServiceHost** .</span><span class="sxs-lookup"><span data-stu-id="c6f32-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 <span data-ttu-id="c6f32-122">Когда **WorkflowServiceHost** будет открыт, сохраняемость автоматически включена, если **DurableInstancingOptions.InstanceStore** не равно null.</span><span class="sxs-lookup"><span data-stu-id="c6f32-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>  
  
 <span data-ttu-id="c6f32-123">Как правило, поведение служб предоставляет конкретное хранилище экземпляров для использования с узлом службы рабочего процесса с помощью **InstanceStore** свойство.</span><span class="sxs-lookup"><span data-stu-id="c6f32-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="c6f32-124">Например, SqlWorkflowInstanceStoreBehavior создает экземпляр класса **SqlWorkflowInstanceStore**, настраивает и присваивает его **DurableInstancingOptions.InstanceStore**.</span><span class="sxs-lookup"><span data-stu-id="c6f32-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="c6f32-125">Включение сохраняемости для служб Workflow Services с помощью файла конфигурации приложения</span><span class="sxs-lookup"><span data-stu-id="c6f32-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>  
 <span data-ttu-id="c6f32-126">Сохраняемость можно включить с помощью файла конфигурации приложения, добавив следующий код в файл app.config или web.config.</span><span class="sxs-lookup"><span data-stu-id="c6f32-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
