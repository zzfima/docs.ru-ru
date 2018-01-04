---
title: "Создание службы долго выполняющегося рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94a62a54fb138e394d8e9fa944e49e6526ae7152
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-long-running-workflow-service"></a><span data-ttu-id="cffad-102">Создание службы долго выполняющегося рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cffad-102">Creating a Long-running Workflow Service</span></span>
<span data-ttu-id="cffad-103">В данном разделе описывается, как создать службу длительных рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="cffad-103">This topic describes how to create a long-running workflow service.</span></span> <span data-ttu-id="cffad-104">Службы длительных рабочих процессов могут работать в течение долгого времени.</span><span class="sxs-lookup"><span data-stu-id="cffad-104">Long running workflow services may run for long periods of time.</span></span> <span data-ttu-id="cffad-105">В определенные моменты рабочий процесс может переходить в состояние бездействия в ожидании дополнительных данных.</span><span class="sxs-lookup"><span data-stu-id="cffad-105">At some point the workflow may go idle waiting for some additional information.</span></span> <span data-ttu-id="cffad-106">В этом случае рабочий процесс сохраняется в базе данных SQL и удаляется из памяти.</span><span class="sxs-lookup"><span data-stu-id="cffad-106">When this occurs the workflow is persisted to a SQL database and is removed from memory.</span></span> <span data-ttu-id="cffad-107">При поступлении дополнительных данных экземпляр рабочего процесса снова загружается в память и его выполнение продолжается.</span><span class="sxs-lookup"><span data-stu-id="cffad-107">When the additional information becomes available the workflow instance is loaded back into memory and continues executing.</span></span>  <span data-ttu-id="cffad-108">В этом сценарии реализуется очень упрощенная система обработки заказов.</span><span class="sxs-lookup"><span data-stu-id="cffad-108">In this scenario you are implementing a very simplified ordering system.</span></span>  <span data-ttu-id="cffad-109">Клиент отправляет первоначальное сообщение службе рабочего процесса с указанием начать заказ.</span><span class="sxs-lookup"><span data-stu-id="cffad-109">The client sends an initial message to the workflow service to start the order.</span></span> <span data-ttu-id="cffad-110">Служба возвращает клиенту идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="cffad-110">It returns an order ID to the client.</span></span> <span data-ttu-id="cffad-111">С этого момента в ожидании нового сообщения от клиента служба рабочего процесса переходит в состояние бездействия и сохраняется в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cffad-111">At this point the workflow service is waiting for another message from the client and goes into the idle state and is persisted to a SQL Server database.</span></span>  <span data-ttu-id="cffad-112">Когда клиент отправит следующее сообщение, чтобы заказать товар, служба рабочего процесса будет снова загружена в память, после чего она завершит обработку заказа.</span><span class="sxs-lookup"><span data-stu-id="cffad-112">When the client sends the next message to order an item, the workflow service is loaded back into memory and finishes processing the order.</span></span> <span data-ttu-id="cffad-113">В приведенном образце кода служба возвращает строку, указывающую на то, что товар добавлен в заказ.</span><span class="sxs-lookup"><span data-stu-id="cffad-113">In the code sample it returns a string stating the item has been added to the order.</span></span> <span data-ttu-id="cffad-114">Этот образец кода не предполагает реализацию такого приложения в реальности, скорее это простой образец, иллюстрирующий работу служб длительных рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="cffad-114">The code sample is not meant to be a real world application of the technology, but rather a simple sample that illustrates long running workflow services.</span></span> <span data-ttu-id="cffad-115">Предполагается, что читатели этого раздела знают, как создавать проекты и решения [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cffad-115">This topic assumes you know how to create [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] projects and solutions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cffad-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cffad-116">Prerequisites</span></span>  
 <span data-ttu-id="cffad-117">Чтобы воспользоваться этим пошаговым руководством, необходимо установить следующее программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="cffad-117">You must have the following software installed to use this walkthrough:</span></span>  
  
1.  <span data-ttu-id="cffad-118">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="cffad-118">Microsoft SQL Server 2008</span></span>  
  
2.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
3.  <span data-ttu-id="cffad-119">Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cffad-119">Microsoft  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span></span>  
  
4.  <span data-ttu-id="cffad-120">Требуются знания служб WCF, среды [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и навыки создания проектов и решений.</span><span class="sxs-lookup"><span data-stu-id="cffad-120">You are familiar with WCF and [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and know how to create projects/solutions.</span></span>  
  
### <a name="to-setup-the-sql-database"></a><span data-ttu-id="cffad-121">Настройка базы данных SQL</span><span class="sxs-lookup"><span data-stu-id="cffad-121">To Setup the SQL Database</span></span>  
  
1.  <span data-ttu-id="cffad-122">Для сохранения экземпляров служб рабочих процессов требуется установленный Microsoft SQL Server, на котором необходимо настроить базу данных для хранения выгруженных из памяти экземпляров рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="cffad-122">In order for workflow service instances to be persisted you must have Microsoft SQL Server installed and you must configure a database to store the persisted workflow instances.</span></span> <span data-ttu-id="cffad-123">Запустите Microsoft SQL Management Studio, нажав **запустить** кнопку выбора **все программы**, **Microsoft SQL Server 2008**, и **Microsoft SQL Среда Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="cffad-123">Run Microsoft SQL Management Studio by clicking the **Start** button, selecting **All Programs**, **Microsoft SQL Server 2008**, and **Microsoft SQL Management Studio**.</span></span>  
  
2.  <span data-ttu-id="cffad-124">Нажмите кнопку **Connect** кнопку, чтобы войти в экземпляр SQL Server</span><span class="sxs-lookup"><span data-stu-id="cffad-124">Click the **Connect** button to log on to the SQL Server instance</span></span>  
  
3.  <span data-ttu-id="cffad-125">Щелкните правой кнопкой мыши **баз данных** в древовидном представлении и выберите **новую базу данных...**</span><span class="sxs-lookup"><span data-stu-id="cffad-125">Right click **Databases** in the tree view and select **New Database..**</span></span> <span data-ttu-id="cffad-126">Чтобы создать новую базу данных с именем `SQLPersistenceStore`.</span><span class="sxs-lookup"><span data-stu-id="cffad-126">to create a new database called `SQLPersistenceStore`.</span></span>  
  
4.  <span data-ttu-id="cffad-127">Выполните в базе данных SQLPersistenceStore файл скрипта SqlWorkflowInstanceStoreSchema.sql, расположенный в каталоге C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en, чтобы настроить требуемые схемы базы данных.</span><span class="sxs-lookup"><span data-stu-id="cffad-127">Run the SqlWorkflowInstanceStoreSchema.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database schemas.</span></span>  
  
5.  <span data-ttu-id="cffad-128">Выполните в базе данных SQLPersistenceStore файл скрипта SqlWorkflowInstanceStoreLogic.sql, расположенный в каталоге C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en, чтобы настроить требуемую логику базы данных.</span><span class="sxs-lookup"><span data-stu-id="cffad-128">Run the SqlWorkflowInstanceStoreLogic.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database logic.</span></span>  
  
### <a name="to-create-the-web-hosted-workflow-service"></a><span data-ttu-id="cffad-129">Создание размещенной на веб-узле службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cffad-129">To Create the Web Hosted Workflow Service</span></span>  
  
1.  <span data-ttu-id="cffad-130">Создайте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] пустое решение и присвойте ему имя `OrderProcessing`.</span><span class="sxs-lookup"><span data-stu-id="cffad-130">Create an empty [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] solution, name it `OrderProcessing`.</span></span>  
  
2.  <span data-ttu-id="cffad-131">Добавьте в решение новый проект приложения службы рабочего процесса [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с именем `OrderService`.</span><span class="sxs-lookup"><span data-stu-id="cffad-131">Add a new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Workflow Service Application project called `OrderService` to the solution.</span></span>  
  
3.  <span data-ttu-id="cffad-132">В диалоговом окне свойств проекта выберите **Web** вкладки.</span><span class="sxs-lookup"><span data-stu-id="cffad-132">In the project properties dialog, select the **Web** tab.</span></span>  
  
    1.  <span data-ttu-id="cffad-133">В разделе **действие при запуске** выберите **определенную страницу** и укажите `Service1.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="cffad-133">Under **Start Action** select **Specific Page** and specify `Service1.xamlx`.</span></span>  
  
         <span data-ttu-id="cffad-134">![Веб-свойства проекта службы рабочего процесса](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")</span><span class="sxs-lookup"><span data-stu-id="cffad-134">![Workflow Service Project Web Properties](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")</span></span>  
  
    2.  <span data-ttu-id="cffad-135">В разделе **серверы** выберите **использовать локальный веб-сервер IIS**.</span><span class="sxs-lookup"><span data-stu-id="cffad-135">Under **Servers** select **Use Local IIS Web server**.</span></span>  
  
         <span data-ttu-id="cffad-136">![Параметры локального веб-сервера](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")</span><span class="sxs-lookup"><span data-stu-id="cffad-136">![Local Web Server Settings](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")</span></span>  
  
        > [!WARNING]
        >  <span data-ttu-id="cffad-137">Чтобы установить этот параметр, необходимо запустить среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] в режиме администратора.</span><span class="sxs-lookup"><span data-stu-id="cffad-137">You must run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] in administrator mode to make this setting.</span></span>  
  
         <span data-ttu-id="cffad-138">Эти шаги необходимы, чтобы настроить размещение проекта службы рабочего процесса в IIS.</span><span class="sxs-lookup"><span data-stu-id="cffad-138">These two steps configure the workflow service project to be hosted by IIS.</span></span>  
  
4.  <span data-ttu-id="cffad-139">Откройте `Service1.xamlx` если он не открыт и удалите существующие **ReceiveRequest** и **SendResponse** действия.</span><span class="sxs-lookup"><span data-stu-id="cffad-139">Open `Service1.xamlx` if it is not open already and delete the existing **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
5.  <span data-ttu-id="cffad-140">Выберите **последовательная служба** действие и нажмите кнопку **переменных** ссылку и добавьте переменные, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-140">Select the **Sequential Service** activity and click the **Variables** link and add the variables shown in the following illustration.</span></span> <span data-ttu-id="cffad-141">Эти переменные будут в дальнейшем использоваться в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cffad-141">Doing this adds some variables that will be used later on in the workflow service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cffad-142">Если в раскрывающемся списке тип переменной отсутствует тип CorrelationHandle, выберите **поиск типов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="cffad-142">If CorrelationHandle is not in the Variable Type drop-down, select **Browse for types** from the drop-down.</span></span> <span data-ttu-id="cffad-143">Введите CorrelationHandle в **имя типа** , выберите CorrelationHandle из списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cffad-143">Type CorrelationHandle in the **Type name** box, select CorrelationHandle from the listbox and click **OK**.</span></span>  
  
     <span data-ttu-id="cffad-144">![Добавление переменных](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")</span><span class="sxs-lookup"><span data-stu-id="cffad-144">![Add Variables](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")</span></span>  
  
6.  <span data-ttu-id="cffad-145">Перетаскивание **ReceiveAndSendReply** шаблон действия в **последовательная служба** действия.</span><span class="sxs-lookup"><span data-stu-id="cffad-145">Drag and drop a **ReceiveAndSendReply** activity template into the **Sequential Service** activity.</span></span> <span data-ttu-id="cffad-146">Этот набор действий будет получать сообщение от клиента и возвращать ему ответ.</span><span class="sxs-lookup"><span data-stu-id="cffad-146">This set of activities will receive a message from a client and send a reply back.</span></span>  
  
    1.  <span data-ttu-id="cffad-147">Выберите **Receive** и задайте свойства, отмеченные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-147">Select the **Receive** activity and set the properties highlighted in the following illustration.</span></span>  
  
         <span data-ttu-id="cffad-148">![Задание свойств действия Receive](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")</span><span class="sxs-lookup"><span data-stu-id="cffad-148">![Set Receive Activity Properties](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")</span></span>  
  
         <span data-ttu-id="cffad-149">Свойство DisplayName задает имя, отображаемое для действия «Receive» в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="cffad-149">The DisplayName property sets the name displayed for the Receive activity in the designer.</span></span> <span data-ttu-id="cffad-150">Свойства ServiceContractName и OperationName задают имя контракта службы и операции, которые реализуются действием Receive.</span><span class="sxs-lookup"><span data-stu-id="cffad-150">The ServiceContractName and OperationName properties specify the name of the service contract and operation that are implemented by the Receive activity.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="cffad-151">Использование контрактов в рабочем процессе служб см. в разделе [использование контрактов в рабочем процессе](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="cffad-151"> how contracts are used in Workflow services see [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  
  
    2.  <span data-ttu-id="cffad-152">Нажмите кнопку **определить...**  ссылку в **ReceiveStartOrder** действия и задайте свойства, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-152">Click the **Define...** link in the **ReceiveStartOrder** activity and set the properties shown in the following illustration.</span></span>  <span data-ttu-id="cffad-153">Обратите внимание, что **параметры** переключателя, параметр с именем `p_customerName` привязан к `customerName` переменной.</span><span class="sxs-lookup"><span data-stu-id="cffad-153">Notice that the **Parameters** radio button is selected, a parameter named `p_customerName` is bound to the `customerName` variable.</span></span> <span data-ttu-id="cffad-154">Это настраивает **Receive** действия на получение данных и привязку этих данных для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="cffad-154">This configures the **Receive** activity to receive some data and bind that data to local variables.</span></span>  
  
         <span data-ttu-id="cffad-155">![Задание данных, получаемых действием Receive](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")</span><span class="sxs-lookup"><span data-stu-id="cffad-155">![Setting the data received by the Receive activity](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")</span></span>  
  
    3.  <span data-ttu-id="cffad-156">Выберите **SendReplyToReceive** и задайте свойство, отмеченное на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-156">Select The **SendReplyToReceive** activity and set the highlighted property shown in the following illustration.</span></span>  
  
         <span data-ttu-id="cffad-157">![Задание свойств действия SendReply](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")</span><span class="sxs-lookup"><span data-stu-id="cffad-157">![Setting the properties of the SendReply activity](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")</span></span>  
  
    4.  <span data-ttu-id="cffad-158">Нажмите кнопку **определить...**  ссылку в **SendReplyToStartOrder** действия и задайте свойства, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-158">Click the **Define...** link in the **SendReplyToStartOrder** activity and set the properties shown in the following illustration.</span></span> <span data-ttu-id="cffad-159">Обратите внимание, что **параметры** переключателя, а параметр `p_orderId` привязан к `orderId` переменной.</span><span class="sxs-lookup"><span data-stu-id="cffad-159">Notice that the **Parameters** radio button is selected; a parameter named `p_orderId` is bound to the `orderId` variable.</span></span> <span data-ttu-id="cffad-160">Этот параметр указывает, что действие SendReplyToStartOrder возвратит вызывающему объекту значение типа String.</span><span class="sxs-lookup"><span data-stu-id="cffad-160">This setting specifies that the SendReplyToStartOrder activity will return a value of type string to the caller.</span></span>  
  
         <span data-ttu-id="cffad-161">![Настройка данных содержимого действия SendReply](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")</span><span class="sxs-lookup"><span data-stu-id="cffad-161">![Configuring the SendReply activity content data](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")</span></span>  
  
    5.  <span data-ttu-id="cffad-162">Перетаскивание действия Assign между **Receive** и **SendReply** действия и задайте свойства, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="cffad-162">Drag and drop an Assign activity in between the **Receive** and **SendReply** activities and set the properties as shown in the following illustration:</span></span>  
  
         <span data-ttu-id="cffad-163">![Добавление действия assign](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")</span><span class="sxs-lookup"><span data-stu-id="cffad-163">![Adding an assign activity](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")</span></span>  
  
         <span data-ttu-id="cffad-164">При этом будет создан новый идентификатор заказа, а его значение будет помещено в переменную orderId.</span><span class="sxs-lookup"><span data-stu-id="cffad-164">This creates a new order ID and places the value in the orderId variable.</span></span>  
  
    6.  <span data-ttu-id="cffad-165">Выберите **ReplyToStartOrder** действия.</span><span class="sxs-lookup"><span data-stu-id="cffad-165">Select the **ReplyToStartOrder** activity.</span></span> <span data-ttu-id="cffad-166">В окне свойств нажмите кнопку с многоточием для **CorrelationInitializers**.</span><span class="sxs-lookup"><span data-stu-id="cffad-166">In the properties window click the ellipsis button for **CorrelationInitializers**.</span></span> <span data-ttu-id="cffad-167">Выберите **добавить инициализатор** , введите `orderIdHandle` в текстовом поле инициализатор, выберите инициализатор корреляции запросов для типа Correlation, а в раскрывающемся списке «запросы XPATH» выберите p_orderId.</span><span class="sxs-lookup"><span data-stu-id="cffad-167">Select the **Add initializer** link, enter `orderIdHandle` in the Initializer text box, select Query correlation initializer for the Correlation type, and select p_orderId under the XPATH Queries dropdown box.</span></span> <span data-ttu-id="cffad-168">Эти параметры показаны на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-168">These settings are shown in the following illustration.</span></span> <span data-ttu-id="cffad-169">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cffad-169">Click **OK**.</span></span>  <span data-ttu-id="cffad-170">При этом будет инициализирована новая корреляция между клиентом и этим экземпляром службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cffad-170">This initializes a correlation between the client and this instance of the workflow service.</span></span> <span data-ttu-id="cffad-171">При получении сообщения с этим идентификатором заказа оно будет направлено этому экземпляру службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cffad-171">When a message containing this order ID is received it is routed to this instance of the workflow service.</span></span>  
  
         <span data-ttu-id="cffad-172">![Добавление инициализатора корреляции](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")</span><span class="sxs-lookup"><span data-stu-id="cffad-172">![Adding a correlation initializer](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")</span></span>  
  
7.  <span data-ttu-id="cffad-173">Перетаскивание другой **ReceiveAndSendReply** действие в конец рабочего процесса (за пределами **последовательности** содержащей первые **Receive** и  **SendReply** действий).</span><span class="sxs-lookup"><span data-stu-id="cffad-173">Drag and drop another **ReceiveAndSendReply** activity to the end of the workflow (outside the **Sequence** containing the first **Receive** and **SendReply** activities).</span></span> <span data-ttu-id="cffad-174">Оно получит второе сообщение от клиента и ответит на него.</span><span class="sxs-lookup"><span data-stu-id="cffad-174">This will receive the second message sent by the client and respond to it.</span></span>  
  
    1.  <span data-ttu-id="cffad-175">Выберите **последовательности** , содержащий только что добавленном **Receive** и **SendReply** действия и нажмите кнопку **переменных** кнопки.</span><span class="sxs-lookup"><span data-stu-id="cffad-175">Select the **Sequence** that contains the newly added **Receive** and **SendReply** activities and click the **Variables** button.</span></span> <span data-ttu-id="cffad-176">Добавьте переменную, отмеченную на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-176">Add the variable highlighted in the following illustration:</span></span>  
  
         <span data-ttu-id="cffad-177">![Добавление новых переменных](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")</span><span class="sxs-lookup"><span data-stu-id="cffad-177">![Adding new variables](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")</span></span>  
  
    2.  <span data-ttu-id="cffad-178">Выберите **Receive** действия и задайте свойства, показанные на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="cffad-178">Select the **Receive** activity and set the properties shown in the following illustration:</span></span>  
  
         <span data-ttu-id="cffad-179">![Задание свойств действия receive](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")</span><span class="sxs-lookup"><span data-stu-id="cffad-179">![Set the Receive acitivity properties](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")</span></span>  
  
    3.  <span data-ttu-id="cffad-180">Нажмите кнопку **определить...**  ссылку в **ReceiveAddItem** действия и добавьте параметры, показанные на следующем рисунке: Это настраивает действия receive и принимать два параметра, идентификатор заказа и идентификатора заказываемого товара.</span><span class="sxs-lookup"><span data-stu-id="cffad-180">Click the **Define...** link in the **ReceiveAddItem** activity and add the parameters shown in the following illustration:This configures the receive activity to accept two parameters, the order ID and the ID of the item being ordered.</span></span>  
  
         <span data-ttu-id="cffad-181">![Указание параметров для второго получения](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")</span><span class="sxs-lookup"><span data-stu-id="cffad-181">![Specifying parameters for the second receive](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")</span></span>  
  
    4.  <span data-ttu-id="cffad-182">Нажмите кнопку **CorrelateOn** кнопку с многоточием и ввести `orderIdHandle`.</span><span class="sxs-lookup"><span data-stu-id="cffad-182">Click the **CorrelateOn** ellipsis button and enter `orderIdHandle`.</span></span> <span data-ttu-id="cffad-183">В разделе **запросы XPath**, щелкните стрелку раскрывающегося списка и выберите `p_orderId`.</span><span class="sxs-lookup"><span data-stu-id="cffad-183">Under **XPath Queries**, click the drop down arrow and select `p_orderId`.</span></span> <span data-ttu-id="cffad-184">При этом будет настроена корреляция второго действия Receive.</span><span class="sxs-lookup"><span data-stu-id="cffad-184">This configures the correlation on the second receive activity.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="cffad-185">корреляции см. в разделе [корреляции](../../../../docs/framework/wcf/feature-details/correlation.md).</span><span class="sxs-lookup"><span data-stu-id="cffad-185"> correlation see [Correlation](../../../../docs/framework/wcf/feature-details/correlation.md).</span></span>  
  
         <span data-ttu-id="cffad-186">![Задание свойства CorrelatesOn](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")</span><span class="sxs-lookup"><span data-stu-id="cffad-186">![Setting the CorrelatesOn property](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")</span></span>  
  
    5.  <span data-ttu-id="cffad-187">Перетаскивание **Если** действие сразу же после **ReceiveAddItem** действия.</span><span class="sxs-lookup"><span data-stu-id="cffad-187">Drag and drop an **If** activity immediately after the **ReceiveAddItem** activity.</span></span> <span data-ttu-id="cffad-188">Это действие работает аналогично инструкции IF.</span><span class="sxs-lookup"><span data-stu-id="cffad-188">This activity acts just like an if statement.</span></span>  
  
        1.  <span data-ttu-id="cffad-189">Задать **условие** свойства`itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span><span class="sxs-lookup"><span data-stu-id="cffad-189">Set the **Condition** property to `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span></span>  
  
        2.  <span data-ttu-id="cffad-190">Перетаскивание **назначить** действие в **затем** раздела, а второе-в **Else** разделе Задание свойств **назначить** действия, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-190">Drag and drop an **Assign** activity in to the **Then** section and another into the **Else** section set the properties of the **Assign** activities as shown in the following illustration.</span></span>  
  
             <span data-ttu-id="cffad-191">![Присваивание результата вызова службы](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")</span><span class="sxs-lookup"><span data-stu-id="cffad-191">![Assigning the result of the service call](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")</span></span>  
  
             <span data-ttu-id="cffad-192">Если условие равно `true` **затем** будет выполнен раздел.</span><span class="sxs-lookup"><span data-stu-id="cffad-192">If the condition is `true` the **Then** section will be executed.</span></span> <span data-ttu-id="cffad-193">Если условие равно `false` **Else** выполняется раздел.</span><span class="sxs-lookup"><span data-stu-id="cffad-193">If the condition is `false` the **Else** section is executed.</span></span>  
  
        3.  <span data-ttu-id="cffad-194">Выберите **SendReplyToReceive** и задайте **DisplayName** свойства, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-194">Select the **SendReplyToReceive** activity and set the **DisplayName** property shown in the following illustration.</span></span>  
  
             <span data-ttu-id="cffad-195">![Задание свойств действия SendReply](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")</span><span class="sxs-lookup"><span data-stu-id="cffad-195">![Setting the SendReply activity properties](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")</span></span>  
  
        4.  <span data-ttu-id="cffad-196">Нажмите кнопку **определить...**  ссылку в **SetReplyToAddItem** действия и настройте его так, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cffad-196">Click the **Define ...** link in the **SetReplyToAddItem** activity and configure it as shown in the following illustration.</span></span> <span data-ttu-id="cffad-197">Это настраивает **SendReplyToAddItem** действие будет возвращать значение в `orderResult` переменной.</span><span class="sxs-lookup"><span data-stu-id="cffad-197">This configures the **SendReplyToAddItem** activity to return the value in the `orderResult` variable.</span></span>  
  
             <span data-ttu-id="cffad-198">![Задание привязки данных для действия SendReply](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")</span><span class="sxs-lookup"><span data-stu-id="cffad-198">![Setting the data binding for the SendReply activit](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")</span></span>  
  
8.  <span data-ttu-id="cffad-199">Откройте файл web.config и добавьте следующие элементы в \<поведение > раздел, чтобы включить сохранение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cffad-199">Open the web.config file and add the following elements in the \<behavior> section to enable workflow persistence.</span></span>  
  
    ```xml  
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />  
              <workflowIdle timeToUnload="0"/>  
    ```  
  
    > [!WARNING]
    >  <span data-ttu-id="cffad-200">В приведенном выше фрагменте кода необходимо заменить имя узла и экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cffad-200">Make sure to replace your host and SQL server instance name in the previous code snippet.</span></span>  
  
9. <span data-ttu-id="cffad-201">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="cffad-201">Build the solution.</span></span>  
  
### <a name="to-create-a-client-application-to-call-the-workflow-service"></a><span data-ttu-id="cffad-202">Создание клиентского приложения, вызывающего службу рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cffad-202">To Create a Client Application to Call the Workflow Service</span></span>  
  
1.  <span data-ttu-id="cffad-203">Добавьте в решение новый проект консольного приложения с именем `OrderClient`.</span><span class="sxs-lookup"><span data-stu-id="cffad-203">Add a new Console application project called `OrderClient` to the solution.</span></span>  
  
2.  <span data-ttu-id="cffad-204">Добавьте в проект `OrderClient` ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="cffad-204">Add references to the following assemblies to the `OrderClient` project</span></span>  
  
    1.  <span data-ttu-id="cffad-205">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="cffad-205">System.ServiceModel.dll</span></span>  
  
    2.  <span data-ttu-id="cffad-206">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="cffad-206">System.ServiceModel.Activities.dll</span></span>  
  
3.  <span data-ttu-id="cffad-207">Добавьте ссылку на службу рабочего процесса и укажите `OrderService` в качестве пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cffad-207">Add a service reference to the workflow service and specify `OrderService` as the namespace.</span></span>  
  
4.  <span data-ttu-id="cffad-208">В метод `Main()` клиентского проекта добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="cffad-208">In the `Main()` method of the client project add the following code:</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
       // Send initial message to start the workflow service  
       Console.WriteLine("Sending start message");  
       StartOrderClient startProxy = new StartOrderClient();  
       string orderId = startProxy.StartOrder("Kim Abercrombie");  
  
       // The workflow service is now waiting for the second message to be sent  
       Console.WriteLine("Workflow service is idle...");  
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");  
       Console.ReadLine();  
  
       // Send the second message  
       Console.WriteLine("Sending add item message");  
       AddItemClient addProxy = new AddItemClient();  
       AddItem item = new AddItem();  
       item.p_itemId = "Zune HD";  
       item.p_orderId = orderId;  
  
       string orderResult = addProxy.AddItem(item);  
       Console.WriteLine("Service returned: " + orderResult);  
    }  
    ```  
  
5.  <span data-ttu-id="cffad-209">Выполните построение решения и запустите приложение `OrderClient`.</span><span class="sxs-lookup"><span data-stu-id="cffad-209">Build the solution and run the `OrderClient` application.</span></span> <span data-ttu-id="cffad-210">Клиент выведет на экран следующий текст.</span><span class="sxs-lookup"><span data-stu-id="cffad-210">The client will display the following text:</span></span>  
  
    ```Output  
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...  
    ```  
  
6.  <span data-ttu-id="cffad-211">Чтобы проверить, сохранен в рабочем процессе, запустите SQL Server Management Studio последовательно выбрав пункты **запустить** меню, при выборе **все программы**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="cffad-211">To verify that the workflow service has been persisted, start the SQL Server Management Studio by going to the **Start** menu, Selecting **All Programs**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.</span></span>  
  
    1.  <span data-ttu-id="cffad-212">На левой панели разверните узел, **баз данных**, **SQLPersistenceStore**, **представления** и щелкните правой кнопкой мыши **System.Activities.DurableInstancing.Instances**  и выберите **выделить 1000 верхних строк**.</span><span class="sxs-lookup"><span data-stu-id="cffad-212">In the left hand pane expand, **Databases**, **SQLPersistenceStore**, **Views** and right click **System.Activities.DurableInstancing.Instances** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="cffad-213">В **результатов** панели убедитесь, вы видите в списке хотя бы один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="cffad-213">In the **Results** pane verify you see at least one instance listed.</span></span> <span data-ttu-id="cffad-214">Если во время работы возникнет исключение, в этой области могут быть указаны и другие экземпляры, оставшиеся от прошлых запусков.</span><span class="sxs-lookup"><span data-stu-id="cffad-214">There may be other instances from prior runs if an exception occurred while running.</span></span> <span data-ttu-id="cffad-215">Удалить существующие строки, щелкните правой кнопкой мыши **System.Activities.DurableInstancing.Instances** и выбрав **изменить 200 верхних строк**, нажмите клавишу **Execute** кнопки выбрать все строки в области результатов и **удалить**.</span><span class="sxs-lookup"><span data-stu-id="cffad-215">You can delete existing rows by right clicking **System.Activities.DurableInstancing.Instances** and selecting **Edit Top 200 rows**, pressing the **Execute** button, selecting all rows in the results pane and selecting **delete**.</span></span>  <span data-ttu-id="cffad-216">Чтобы проверить, что в базе данных отображается экземпляр, созданный учебным приложением, перед запуском клиента удалите все записи из представления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="cffad-216">To verify the instance displayed in the database is the instance your application created, verify the instances view is empty prior to running the client.</span></span> <span data-ttu-id="cffad-217">После запуска клиента выполните этот запрос («Выделить 1000 верхних строк») еще раз и удостоверьтесь, что новый экземпляр добавлен.</span><span class="sxs-lookup"><span data-stu-id="cffad-217">Once the client is running re-run the query (Select Top 1000 Rows) and verify a new instance has been added.</span></span>  
  
7.  <span data-ttu-id="cffad-218">Нажмите клавишу ВВОД, чтобы отправить сообщение о добавлении товара службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cffad-218">Press enter to send the add item message to the workflow service.</span></span> <span data-ttu-id="cffad-219">Клиент выведет на экран следующий текст.</span><span class="sxs-lookup"><span data-stu-id="cffad-219">The client will display the following text:</span></span>  
  
    ```Output  
    Sending add item messageService returned: Item added to orderPress any key to continue . . .  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cffad-220">См. также</span><span class="sxs-lookup"><span data-stu-id="cffad-220">See Also</span></span>  
 [<span data-ttu-id="cffad-221">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="cffad-221">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
