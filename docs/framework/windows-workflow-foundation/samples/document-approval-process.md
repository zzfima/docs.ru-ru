---
title: Процесс утверждения документа
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: c28dafd3b0a1cb6dbee37fed2b3df8923ccd82c8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="document-approval-process"></a><span data-ttu-id="c8eaa-102">Процесс утверждения документа</span><span class="sxs-lookup"><span data-stu-id="c8eaa-102">Document Approval Process</span></span>
<span data-ttu-id="c8eaa-103">В этом образце демонстрируется использование многих возможностей Windows Workflow Foundation (WF) и Windows Communication Foundation (WCF) друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="c8eaa-104">Вместе они реализуют сценарий утверждения документов.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="c8eaa-105">Клиентское приложение может представлять документы на утверждение и утверждать документы.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="c8eaa-106">Диспетчер утверждений облегчает взаимодействие между клиентами и обеспечивает соблюдение порядка утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="c8eaa-107">Утверждение - это рабочий процесс, который может выполняться несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="c8eaa-108">Поддерживается единичное утверждение, утверждение кворумом (частью группы утверждающих) и составное утверждение, состоящее из утверждения кворумом и следующего за ним единичного утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c8eaa-109">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c8eaa-110">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c8eaa-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c8eaa-111">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c8eaa-112">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a><span data-ttu-id="c8eaa-113">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="c8eaa-113">Sample Details</span></span>  
 <span data-ttu-id="c8eaa-114">На следующем графике представлена схема процесса утверждения документа.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-114">The following graphic demonstrates the document approval process workflow.</span></span>  
  
 <span data-ttu-id="c8eaa-115">![Рабочий процесс утверждения документа](../../../../docs/framework/windows-workflow-foundation/samples/media/approvalprocess.jpg "ApprovalProcess")</span><span class="sxs-lookup"><span data-stu-id="c8eaa-115">![A document approval process workflow](../../../../docs/framework/windows-workflow-foundation/samples/media/approvalprocess.jpg "ApprovalProcess")</span></span>  
  
 <span data-ttu-id="c8eaa-116">С точки зрения клиента процесс утверждения документа протекает следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-116">From the client's perspective, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="c8eaa-117">Клиент отправляет заявку на участие в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-117">A client subscribes to be a user in the approval process system.</span></span>  
  
2.  <span data-ttu-id="c8eaa-118">Клиент WCF отправляет службы WCF, размещенной в диспетчере утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>  
  
3.  <span data-ttu-id="c8eaa-119">Клиенту возвращается индивидуальный пользовательский идентификатор.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="c8eaa-120">Теперь клиент может участвовать в процессе утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-120">The client can now participate in approval processes.</span></span>  
  
4.  <span data-ttu-id="c8eaa-121">Присоединившись к системе, клиент может отправить документ на единичное утверждение, утверждение кворумом и составное утверждение.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>  
  
5.  <span data-ttu-id="c8eaa-122">По нажатию кнопки в клиентском интерфейсе запускается экземпляр рабочего процесса, размещенного в клиентском узле службы рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>  
  
6.  <span data-ttu-id="c8eaa-123">Рабочий процесс отправляет запрос на утверждение приложению диспетчера утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-123">The workflow sends an approval request to the approval manager application.</span></span>  
  
7.  <span data-ttu-id="c8eaa-124">Диспетчер рабочего процесса запускает на своем сайте рабочий процесс, представляющий процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>  
  
8.  <span data-ttu-id="c8eaa-125">По завершении рабочего процесса утверждения диспетчер возвращает клиенту результаты.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>  
  
9. <span data-ttu-id="c8eaa-126">Результаты отображаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-126">The client displays the results.</span></span>  
  
10. <span data-ttu-id="c8eaa-127">Клиент может получить запрос на утверждение и в любой момент ответить на него.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-127">A client may receive an approval request and respond to the request at any point in time.</span></span>  
  
11. <span data-ttu-id="c8eaa-128">Служба WCF, размещенная в клиенте может получать запрос на утверждение от диспетчера утверждений.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>  
  
12. <span data-ttu-id="c8eaa-129">Данные о документе представляются на обозрение в клиенте.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-129">The document information is presented on the client for review.</span></span>  
  
13. <span data-ttu-id="c8eaa-130">Пользователь может утвердить или отклонить документ.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-130">The user can approve or reject the document.</span></span>  
  
14. <span data-ttu-id="c8eaa-131">Клиент WCF используется для отправки ответа обратно в диспетчере утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>  
  
 <span data-ttu-id="c8eaa-132">С точки зрения диспетчера утверждений процесс утверждения протекает следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="c8eaa-133">Клиент отправляет заявку на участие в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-133">A client requests to participate to the approval process system.</span></span>  
  
2.  <span data-ttu-id="c8eaa-134">Служба WCF диспетчера утверждений получает запрос на могут входить в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>  
  
3.  <span data-ttu-id="c8eaa-135">Для клиента создается индивидуальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="c8eaa-136">Пользовательские данные сохраняются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-136">The user information is stored in a database.</span></span>  
  
4.  <span data-ttu-id="c8eaa-137">Пользователю возвращается индивидуальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-137">The unique ID is sent back to the user.</span></span>  
  
5.  <span data-ttu-id="c8eaa-138">Получение запроса на утверждение.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-138">An approval request is receive.</span></span> <span data-ttu-id="c8eaa-139">Диспетчер запускает процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-139">The approval manager executes an approval process.</span></span>  
  
6.  <span data-ttu-id="c8eaa-140">Диспетчер получает запрос на утверждение и начинает новый рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-140">An approval request is received by the approval manager, starting a new workflow.</span></span>  
  
7.  <span data-ttu-id="c8eaa-141">В зависимости от типа запроса (простое утверждение, утверждение кворумом или составное утверждение) запускается определенное действие.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>  
  
8.  <span data-ttu-id="c8eaa-142">Действия по отправке и получению с корреляцией используются для отправки запроса на утверждение клиенту на рассмотрения и для получения ответа.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>  
  
9. <span data-ttu-id="c8eaa-143">Результат рабочего процесса утверждения отправляется клиенту.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-143">The result of the approval process workflow is sent to the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="c8eaa-144">Использование образца</span><span class="sxs-lookup"><span data-stu-id="c8eaa-144">Using the Sample</span></span>  
  
##### <a name="to-set-up-the-database"></a><span data-ttu-id="c8eaa-145">Настройка базы данных</span><span class="sxs-lookup"><span data-stu-id="c8eaa-145">To set up the database</span></span>  
  
1.  <span data-ttu-id="c8eaa-146">Из командной строки [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], открытой с правами администратора, перейдите в каталог DocumentApprovalProcess и запустите команду Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-146">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>  
  
##### <a name="to-set-up-the-application"></a><span data-ttu-id="c8eaa-147">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="c8eaa-147">To set up the application</span></span>  
  
1.  <span data-ttu-id="c8eaa-148">Откройте файл решения DocumentApprovalProcess.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8eaa-148">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DocumentApprovalProcess.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c8eaa-149">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c8eaa-150">Чтобы запустить решение, запустите приложение утверждающий, щелкнув правой кнопкой мыши проект ApprovalManager в **обозревателе решений** и щелкнув **отладки**->**запуск**  новый экземпляр из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>  
  
     <span data-ttu-id="c8eaa-151">Подождите, пока от диспетчера не придет сообщение о готовности.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-151">Wait for the manager’s output to let you know that it is ready.</span></span>  
  
##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="c8eaa-152">Выполнение сценария одиночного утверждения</span><span class="sxs-lookup"><span data-stu-id="c8eaa-152">To run the single approval scenario</span></span>  
  
1.  <span data-ttu-id="c8eaa-153">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-153">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="c8eaa-154">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-154">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="c8eaa-155">Перейдите в папку ApprovalClient\Bin\Debug и запустите два экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="c8eaa-156">Нажмите кнопку **обнаружение**, подождите, пока **подписаться** кнопка включена.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="c8eaa-157">Введите любое имя пользователя и нажмите кнопку **подписаться**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="c8eaa-158">Для первого клиента используйте `UserType1`, а для второго - `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="c8eaa-159">На клиенте `UserType1` выберите один тип подтверждения из раскрывающегося меню и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="c8eaa-160">Нажмите кнопку **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-160">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="c8eaa-161">В клиенте `UserType2` появится документ, ожидающий утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="c8eaa-162">Выберите его и нажмите клавишу **утвердить** или **Отклонить**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="c8eaa-163">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-163">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="c8eaa-164">Выполнение сценария утверждения кворумом</span><span class="sxs-lookup"><span data-stu-id="c8eaa-164">To run the quorum approval scenario</span></span>  
  
1.  <span data-ttu-id="c8eaa-165">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-165">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="c8eaa-166">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-166">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="c8eaa-167">Перейдите в папку ApprovalClient\Bin\Debug и запустите три экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="c8eaa-168">Нажмите кнопку **обнаружение**, подождите, пока **подписаться** кнопка включена.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="c8eaa-169">Введите любое имя пользователя и нажмите кнопку **подписаться**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="c8eaa-170">Для одного клиента используйте `UserType1`, а для двух других - `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="c8eaa-171">В клиенте `UserType1` выберите в раскрывающемся меню утверждение кворумом и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="c8eaa-172">Нажмите кнопку **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-172">Click **Request Approval**.</span></span> <span data-ttu-id="c8eaa-173">В данном случае требуется, чтобы два клиента `UserType2` утвердили или отклонили документ.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="c8eaa-174">Хотя ответить должны оба клиента `UserType2`, для утверждения документа достаточно, чтобы его утвердил один из них.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>  
  
7.  <span data-ttu-id="c8eaa-175">На клиентах `UserType2` появится документ, ожидающий подтверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="c8eaa-176">Выберите его и нажмите клавишу **утвердить** или **Отклонить**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="c8eaa-177">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-177">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="c8eaa-178">Выполнение сценария составного утверждения</span><span class="sxs-lookup"><span data-stu-id="c8eaa-178">To run the complex approval scenario</span></span>  
  
1.  <span data-ttu-id="c8eaa-179">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-179">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="c8eaa-180">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-180">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="c8eaa-181">Перейдите в папку ApprovalClient\Bin\Debug и запустите четыре экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="c8eaa-182">Нажмите кнопку **обнаружение**, подождите, пока **подписаться** кнопка включена.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="c8eaa-183">Введите любое имя пользователя и нажмите кнопку **подписаться**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="c8eaa-184">Для одного клиента используйте `UserType1`, для двух других - `UserType2`, а для последнего - `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>  
  
6.  <span data-ttu-id="c8eaa-185">На клиенте `UserType1` выберите один тип подтверждения из раскрывающегося меню и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="c8eaa-186">Нажмите кнопку **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-186">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="c8eaa-187">На клиентах `UserType2` появится документ, ожидающий подтверждения.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="c8eaa-188">Выберите его и нажмите клавишу **утвердить**, документ передан `UserType3` клиента.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>  
  
     <span data-ttu-id="c8eaa-189">Если документ был утвержден первым кворумом `UserType2`, этот документ буден передан клиенту `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>  
  
8.  <span data-ttu-id="c8eaa-190">Утвердите или отклоните документ, полученный от клиента `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="c8eaa-191">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-191">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-clean-up"></a><span data-ttu-id="c8eaa-192">Очистка</span><span class="sxs-lookup"><span data-stu-id="c8eaa-192">To clean up</span></span>  
  
1.  <span data-ttu-id="c8eaa-193">В командной строке [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] перейдите в директорию DocumentApprovalProcess и запустите команду Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="c8eaa-193">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>