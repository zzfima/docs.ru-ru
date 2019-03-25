---
title: Процесс утверждения документа
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: 4451719bfb1d46a4e0e4dcde19666d1f8b2de427
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409553"
---
# <a name="document-approval-process"></a><span data-ttu-id="77c7b-102">Процесс утверждения документа</span><span class="sxs-lookup"><span data-stu-id="77c7b-102">Document Approval Process</span></span>
<span data-ttu-id="77c7b-103">В этом примере показано использование возможностей Windows Workflow Foundation (WF) и Windows Communication Foundation (WCF) друг с другом.</span><span class="sxs-lookup"><span data-stu-id="77c7b-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="77c7b-104">Вместе они реализуют сценарий утверждения документов.</span><span class="sxs-lookup"><span data-stu-id="77c7b-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="77c7b-105">Клиентское приложение может представлять документы на утверждение и утверждать документы.</span><span class="sxs-lookup"><span data-stu-id="77c7b-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="77c7b-106">Диспетчер утверждений облегчает взаимодействие между клиентами и обеспечивает соблюдение порядка утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="77c7b-107">Утверждение - это рабочий процесс, который может выполняться несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="77c7b-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="77c7b-108">Поддерживается единичное утверждение, утверждение кворумом (частью группы утверждающих) и составное утверждение, состоящее из утверждения кворумом и следующего за ним единичного утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="77c7b-109">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="77c7b-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="77c7b-110">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="77c7b-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="77c7b-111">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="77c7b-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="77c7b-112">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="77c7b-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a><span data-ttu-id="77c7b-113">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="77c7b-113">Sample Details</span></span>  
 <span data-ttu-id="77c7b-114">Приведенный ниже рисунок показывает рабочий процесс утверждения документов:</span><span class="sxs-lookup"><span data-stu-id="77c7b-114">The following graphic demonstrates the document approval process workflow:</span></span>  
  
 ![Рабочий процесс утверждения документа](./media/document-approval-process/document-approval-process.jpg)  
  
 <span data-ttu-id="77c7b-116">С точки зрения клиента процесс утверждения документа протекает следующим образом.</span><span class="sxs-lookup"><span data-stu-id="77c7b-116">From the client's perspective, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="77c7b-117">Клиент отправляет заявку на участие в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-117">A client subscribes to be a user in the approval process system.</span></span>  
  
2.  <span data-ttu-id="77c7b-118">Клиент WCF отправляет является службой WCF, размещенной на утверждение приложению диспетчера.</span><span class="sxs-lookup"><span data-stu-id="77c7b-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>  
  
3.  <span data-ttu-id="77c7b-119">Клиенту возвращается индивидуальный пользовательский идентификатор.</span><span class="sxs-lookup"><span data-stu-id="77c7b-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="77c7b-120">Теперь клиент может участвовать в процессе утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-120">The client can now participate in approval processes.</span></span>  
  
4.  <span data-ttu-id="77c7b-121">Присоединившись к системе, клиент может отправить документ на единичное утверждение, утверждение кворумом и составное утверждение.</span><span class="sxs-lookup"><span data-stu-id="77c7b-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>  
  
5.  <span data-ttu-id="77c7b-122">По нажатию кнопки в клиентском интерфейсе запускается экземпляр рабочего процесса, размещенного в клиентском узле службы рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="77c7b-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>  
  
6.  <span data-ttu-id="77c7b-123">Рабочий процесс отправляет запрос на утверждение приложению диспетчера утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-123">The workflow sends an approval request to the approval manager application.</span></span>  
  
7.  <span data-ttu-id="77c7b-124">Диспетчер рабочего процесса запускает на своем сайте рабочий процесс, представляющий процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>  
  
8.  <span data-ttu-id="77c7b-125">По завершении рабочего процесса утверждения диспетчер возвращает клиенту результаты.</span><span class="sxs-lookup"><span data-stu-id="77c7b-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>  
  
9. <span data-ttu-id="77c7b-126">Результаты отображаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="77c7b-126">The client displays the results.</span></span>  
  
10. <span data-ttu-id="77c7b-127">Клиент может получить запрос на утверждение и в любой момент ответить на него.</span><span class="sxs-lookup"><span data-stu-id="77c7b-127">A client may receive an approval request and respond to the request at any point in time.</span></span>  
  
11. <span data-ttu-id="77c7b-128">Службы WCF, размещенной на стороне клиента может получать запрос на утверждение от на утверждение приложению диспетчера.</span><span class="sxs-lookup"><span data-stu-id="77c7b-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>  
  
12. <span data-ttu-id="77c7b-129">Данные о документе представляются на обозрение в клиенте.</span><span class="sxs-lookup"><span data-stu-id="77c7b-129">The document information is presented on the client for review.</span></span>  
  
13. <span data-ttu-id="77c7b-130">Пользователь может утвердить или отклонить документ.</span><span class="sxs-lookup"><span data-stu-id="77c7b-130">The user can approve or reject the document.</span></span>  
  
14. <span data-ttu-id="77c7b-131">Клиент WCF используется для отправки ответа обратно к приложению диспетчера утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>  
  
 <span data-ttu-id="77c7b-132">С точки зрения диспетчера утверждений процесс утверждения протекает следующим образом.</span><span class="sxs-lookup"><span data-stu-id="77c7b-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="77c7b-133">Клиент отправляет заявку на участие в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-133">A client requests to participate to the approval process system.</span></span>  
  
2.  <span data-ttu-id="77c7b-134">Службы WCF диспетчера утверждений получает запрос на может входить в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>  
  
3.  <span data-ttu-id="77c7b-135">Для клиента создается индивидуальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="77c7b-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="77c7b-136">Пользовательские данные сохраняются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="77c7b-136">The user information is stored in a database.</span></span>  
  
4.  <span data-ttu-id="77c7b-137">Пользователю возвращается индивидуальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="77c7b-137">The unique ID is sent back to the user.</span></span>  
  
5.  <span data-ttu-id="77c7b-138">Получение запроса на утверждение.</span><span class="sxs-lookup"><span data-stu-id="77c7b-138">An approval request is receive.</span></span> <span data-ttu-id="77c7b-139">Диспетчер запускает процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-139">The approval manager executes an approval process.</span></span>  
  
6.  <span data-ttu-id="77c7b-140">Диспетчер получает запрос на утверждение и начинает новый рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="77c7b-140">An approval request is received by the approval manager, starting a new workflow.</span></span>  
  
7.  <span data-ttu-id="77c7b-141">В зависимости от типа запроса (простое утверждение, утверждение кворумом или составное утверждение) запускается определенное действие.</span><span class="sxs-lookup"><span data-stu-id="77c7b-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>  
  
8.  <span data-ttu-id="77c7b-142">Действия по отправке и получению с корреляцией используются для отправки запроса на утверждение клиенту на рассмотрения и для получения ответа.</span><span class="sxs-lookup"><span data-stu-id="77c7b-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>  
  
9. <span data-ttu-id="77c7b-143">Результат рабочего процесса утверждения отправляется клиенту.</span><span class="sxs-lookup"><span data-stu-id="77c7b-143">The result of the approval process workflow is sent to the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="77c7b-144">Использование образца</span><span class="sxs-lookup"><span data-stu-id="77c7b-144">Using the Sample</span></span>  
  
##### <a name="to-set-up-the-database"></a><span data-ttu-id="77c7b-145">Настройка базы данных</span><span class="sxs-lookup"><span data-stu-id="77c7b-145">To set up the database</span></span>  
  
1.  <span data-ttu-id="77c7b-146">Из командной строки Visual Studio 2010 с правами администратора перейдите к этой директорию documentapprovalprocess и запустите команду Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="77c7b-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>  
  
##### <a name="to-set-up-the-application"></a><span data-ttu-id="77c7b-147">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="77c7b-147">To set up the application</span></span>  
  
1.  <span data-ttu-id="77c7b-148">Откройте файл решения DocumentApprovalProcess.sln в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="77c7b-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>  
  
2.  <span data-ttu-id="77c7b-149">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="77c7b-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="77c7b-150">Чтобы запустить решение, запустите диспетчер утверждений, щелкните правой кнопкой мыши проект ApprovalManager в **обозревателе решений** и щелкнув **Отладка**->**запуск**  новый экземпляр из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="77c7b-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>  
  
     <span data-ttu-id="77c7b-151">Подождите, пока от диспетчера не придет сообщение о готовности.</span><span class="sxs-lookup"><span data-stu-id="77c7b-151">Wait for the manager’s output to let you know that it is ready.</span></span>  
  
##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="77c7b-152">Выполнение сценария одиночного утверждения</span><span class="sxs-lookup"><span data-stu-id="77c7b-152">To run the single approval scenario</span></span>  
  
1.  <span data-ttu-id="77c7b-153">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="77c7b-153">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="77c7b-154">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="77c7b-154">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="77c7b-155">Перейдите в папку ApprovalClient\Bin\Debug и запустите два экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="77c7b-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="77c7b-156">Нажмите кнопку **обнаружение**, подождите, пока **подписаться** кнопка включена.</span><span class="sxs-lookup"><span data-stu-id="77c7b-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="77c7b-157">Введите любое имя пользователя и нажмите кнопку **подписаться**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="77c7b-158">Для первого клиента используйте `UserType1`, а для второго - `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="77c7b-159">На клиенте `UserType1` выберите один тип подтверждения из раскрывающегося меню и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="77c7b-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="77c7b-160">Нажмите кнопку **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-160">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="77c7b-161">В клиенте `UserType2` появится документ, ожидающий утверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="77c7b-162">Выберите его и нажмите клавишу **утвердить** или **Отклонить**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="77c7b-163">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-163">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="77c7b-164">Выполнение сценария утверждения кворумом</span><span class="sxs-lookup"><span data-stu-id="77c7b-164">To run the quorum approval scenario</span></span>  
  
1.  <span data-ttu-id="77c7b-165">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="77c7b-165">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="77c7b-166">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="77c7b-166">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="77c7b-167">Перейдите в папку ApprovalClient\Bin\Debug и запустите три экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="77c7b-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="77c7b-168">Нажмите кнопку **обнаружение**, подождите, пока **подписаться** кнопка включена.</span><span class="sxs-lookup"><span data-stu-id="77c7b-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="77c7b-169">Введите любое имя пользователя и нажмите кнопку **подписаться**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="77c7b-170">Для одного клиента используйте `UserType1`, а для двух других - `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="77c7b-171">В клиенте `UserType1` выберите в раскрывающемся меню утверждение кворумом и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="77c7b-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="77c7b-172">Нажмите кнопку **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-172">Click **Request Approval**.</span></span> <span data-ttu-id="77c7b-173">В данном случае требуется, чтобы два клиента `UserType2` утвердили или отклонили документ.</span><span class="sxs-lookup"><span data-stu-id="77c7b-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="77c7b-174">Хотя ответить должны оба клиента `UserType2`, для утверждения документа достаточно, чтобы его утвердил один из них.</span><span class="sxs-lookup"><span data-stu-id="77c7b-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>  
  
7.  <span data-ttu-id="77c7b-175">На клиентах `UserType2` появится документ, ожидающий подтверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="77c7b-176">Выберите его и нажмите клавишу **утвердить** или **Отклонить**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="77c7b-177">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-177">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="77c7b-178">Выполнение сценария составного утверждения</span><span class="sxs-lookup"><span data-stu-id="77c7b-178">To run the complex approval scenario</span></span>  
  
1.  <span data-ttu-id="77c7b-179">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="77c7b-179">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="77c7b-180">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="77c7b-180">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="77c7b-181">Перейдите в папку ApprovalClient\Bin\Debug и запустите четыре экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="77c7b-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="77c7b-182">Нажмите кнопку **обнаружение**, подождите, пока **подписаться** кнопка включена.</span><span class="sxs-lookup"><span data-stu-id="77c7b-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="77c7b-183">Введите любое имя пользователя и нажмите кнопку **подписаться**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="77c7b-184">Для одного клиента используйте `UserType1`, для двух других - `UserType2`, а для последнего - `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>  
  
6.  <span data-ttu-id="77c7b-185">На клиенте `UserType1` выберите один тип подтверждения из раскрывающегося меню и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="77c7b-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="77c7b-186">Нажмите кнопку **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="77c7b-186">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="77c7b-187">На клиентах `UserType2` появится документ, ожидающий подтверждения.</span><span class="sxs-lookup"><span data-stu-id="77c7b-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="77c7b-188">Выберите его и нажмите клавишу **утвердить**, документ буден передан `UserType3` клиента.</span><span class="sxs-lookup"><span data-stu-id="77c7b-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>  
  
     <span data-ttu-id="77c7b-189">Если документ был утвержден первым кворумом `UserType2`, этот документ буден передан клиенту `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>  
  
8.  <span data-ttu-id="77c7b-190">Утвердите или отклоните документ, полученный от клиента `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="77c7b-191">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="77c7b-191">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-clean-up"></a><span data-ttu-id="77c7b-192">Очистка</span><span class="sxs-lookup"><span data-stu-id="77c7b-192">To clean up</span></span>  
  
1.  <span data-ttu-id="77c7b-193">Из командной строки Visual Studio 2010 перейдите в директорию documentapprovalprocess и запустите команду Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="77c7b-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
