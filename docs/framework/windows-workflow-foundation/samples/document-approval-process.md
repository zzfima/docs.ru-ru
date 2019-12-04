---
title: Процесс утверждения документа
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: cee43aff991f9482de7b3172174eb0e786ec1fe6
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710847"
---
# <a name="document-approval-process"></a><span data-ttu-id="0b822-102">Процесс утверждения документа</span><span class="sxs-lookup"><span data-stu-id="0b822-102">Document Approval Process</span></span>

<span data-ttu-id="0b822-103">В этом примере демонстрируется использование многих функций Windows Workflow Foundation (WF) и Windows Communication Foundation (WCF) вместе.</span><span class="sxs-lookup"><span data-stu-id="0b822-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="0b822-104">Вместе они реализуют сценарий утверждения документов.</span><span class="sxs-lookup"><span data-stu-id="0b822-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="0b822-105">Клиентское приложение может представлять документы на утверждение и утверждать документы.</span><span class="sxs-lookup"><span data-stu-id="0b822-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="0b822-106">Диспетчер утверждений облегчает взаимодействие между клиентами и обеспечивает соблюдение порядка утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="0b822-107">Утверждение - это рабочий процесс, который может выполняться несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="0b822-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="0b822-108">Поддерживается единичное утверждение, утверждение кворумом (частью группы утверждающих) и составное утверждение, состоящее из утверждения кворумом и следующего за ним единичного утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b822-109">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b822-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0b822-110">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0b822-110">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="0b822-111">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="0b822-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0b822-112">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0b822-112">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`

## <a name="sample-details"></a><span data-ttu-id="0b822-113">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="0b822-113">Sample Details</span></span>

<span data-ttu-id="0b822-114">На следующем рисунке показан рабочий процесс утверждения документов.</span><span class="sxs-lookup"><span data-stu-id="0b822-114">The following graphic demonstrates the document approval process workflow:</span></span>

![Рабочий процесс утверждения документов](./media/document-approval-process/document-approval-process.jpg)

<span data-ttu-id="0b822-116">С точки зрения клиента процесс утверждения документа протекает следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0b822-116">From the client's perspective, the approval process functions as follows:</span></span>

1. <span data-ttu-id="0b822-117">Клиент отправляет заявку на участие в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-117">A client subscribes to be a user in the approval process system.</span></span>

2. <span data-ttu-id="0b822-118">Клиент WCF отправляет в службу WCF, размещенную в приложении диспетчера утверждений.</span><span class="sxs-lookup"><span data-stu-id="0b822-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>

3. <span data-ttu-id="0b822-119">Клиенту возвращается индивидуальный пользовательский идентификатор.</span><span class="sxs-lookup"><span data-stu-id="0b822-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="0b822-120">Теперь клиент может участвовать в процессе утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-120">The client can now participate in approval processes.</span></span>

4. <span data-ttu-id="0b822-121">Присоединившись к системе, клиент может отправить документ на единичное утверждение, утверждение кворумом и составное утверждение.</span><span class="sxs-lookup"><span data-stu-id="0b822-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>

5. <span data-ttu-id="0b822-122">По нажатию кнопки в клиентском интерфейсе запускается экземпляр рабочего процесса, размещенного в клиентском узле службы рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="0b822-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>

6. <span data-ttu-id="0b822-123">Рабочий процесс отправляет запрос на утверждение приложению диспетчера утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-123">The workflow sends an approval request to the approval manager application.</span></span>

7. <span data-ttu-id="0b822-124">Диспетчер рабочего процесса запускает на своем сайте рабочий процесс, представляющий процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>

8. <span data-ttu-id="0b822-125">По завершении рабочего процесса утверждения диспетчер возвращает клиенту результаты.</span><span class="sxs-lookup"><span data-stu-id="0b822-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>

9. <span data-ttu-id="0b822-126">Результаты отображаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="0b822-126">The client displays the results.</span></span>

10. <span data-ttu-id="0b822-127">Клиент может получить запрос на утверждение и в любой момент ответить на него.</span><span class="sxs-lookup"><span data-stu-id="0b822-127">A client may receive an approval request and respond to the request at any point in time.</span></span>

11. <span data-ttu-id="0b822-128">Служба WCF, размещенная на клиенте, может получить запрос на утверждение от приложения диспетчера утверждений.</span><span class="sxs-lookup"><span data-stu-id="0b822-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>

12. <span data-ttu-id="0b822-129">Данные о документе представляются на обозрение в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0b822-129">The document information is presented on the client for review.</span></span>

13. <span data-ttu-id="0b822-130">Пользователь может утвердить или отклонить документ.</span><span class="sxs-lookup"><span data-stu-id="0b822-130">The user can approve or reject the document.</span></span>

14. <span data-ttu-id="0b822-131">Клиент WCF используется для отправки ответа об утверждении обратно в приложение диспетчера утверждений.</span><span class="sxs-lookup"><span data-stu-id="0b822-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>

<span data-ttu-id="0b822-132">С точки зрения диспетчера утверждений процесс утверждения протекает следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0b822-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>

1. <span data-ttu-id="0b822-133">Клиент отправляет заявку на участие в системе утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-133">A client requests to participate to the approval process system.</span></span>

2. <span data-ttu-id="0b822-134">Служба WCF в диспетчере утверждений получает запрос, который будет входить в систему процесса утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>

3. <span data-ttu-id="0b822-135">Для клиента создается индивидуальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="0b822-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="0b822-136">Пользовательские данные сохраняются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0b822-136">The user information is stored in a database.</span></span>

4. <span data-ttu-id="0b822-137">Пользователю возвращается индивидуальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="0b822-137">The unique ID is sent back to the user.</span></span>

5. <span data-ttu-id="0b822-138">Получение запроса на утверждение.</span><span class="sxs-lookup"><span data-stu-id="0b822-138">An approval request is receive.</span></span> <span data-ttu-id="0b822-139">Диспетчер запускает процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-139">The approval manager executes an approval process.</span></span>

6. <span data-ttu-id="0b822-140">Диспетчер получает запрос на утверждение и начинает новый рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="0b822-140">An approval request is received by the approval manager, starting a new workflow.</span></span>

7. <span data-ttu-id="0b822-141">В зависимости от типа запроса (простое утверждение, утверждение кворумом или составное утверждение) запускается определенное действие.</span><span class="sxs-lookup"><span data-stu-id="0b822-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>

8. <span data-ttu-id="0b822-142">Действия по отправке и получению с корреляцией используются для отправки запроса на утверждение клиенту на рассмотрения и для получения ответа.</span><span class="sxs-lookup"><span data-stu-id="0b822-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>

9. <span data-ttu-id="0b822-143">Результат рабочего процесса утверждения отправляется клиенту.</span><span class="sxs-lookup"><span data-stu-id="0b822-143">The result of the approval process workflow is sent to the client.</span></span>

## <a name="using-the-sample"></a><span data-ttu-id="0b822-144">Использование образца</span><span class="sxs-lookup"><span data-stu-id="0b822-144">Using the Sample</span></span>

##### <a name="to-set-up-the-database"></a><span data-ttu-id="0b822-145">Настройка базы данных</span><span class="sxs-lookup"><span data-stu-id="0b822-145">To set up the database</span></span>

1. <span data-ttu-id="0b822-146">В командной строке Visual Studio 2010, открытой с правами администратора, перейдите в эту папку Документаппровалпроцесс и запустите Setup. cmd.</span><span class="sxs-lookup"><span data-stu-id="0b822-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>

##### <a name="to-set-up-the-application"></a><span data-ttu-id="0b822-147">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="0b822-147">To set up the application</span></span>

1. <span data-ttu-id="0b822-148">С помощью Visual Studio 2010 откройте файл решения Документаппровалпроцесс. sln.</span><span class="sxs-lookup"><span data-stu-id="0b822-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>

2. <span data-ttu-id="0b822-149">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="0b822-149">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="0b822-150">Чтобы запустить решение, запустите приложение "Диспетчер утверждений", щелкнув правой кнопкой мыши проект Аппровалманажер в **Обозреватель решений** и выбрав **Отладка**->**запустить** новый экземпляр из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="0b822-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>

    <span data-ttu-id="0b822-151">Подождите, пока от диспетчера не придет сообщение о готовности.</span><span class="sxs-lookup"><span data-stu-id="0b822-151">Wait for the manager’s output to let you know that it is ready.</span></span>

##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="0b822-152">Выполнение сценария одиночного утверждения</span><span class="sxs-lookup"><span data-stu-id="0b822-152">To run the single approval scenario</span></span>

1. <span data-ttu-id="0b822-153">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="0b822-153">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="0b822-154">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="0b822-154">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="0b822-155">Перейдите в папку ApprovalClient\Bin\Debug и запустите два экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="0b822-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="0b822-156">Нажмите кнопку **обнаружить**, дождитесь включения кнопки **Подписка** .</span><span class="sxs-lookup"><span data-stu-id="0b822-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="0b822-157">Введите любое имя пользователя и щелкните **подписываться**.</span><span class="sxs-lookup"><span data-stu-id="0b822-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="0b822-158">Для первого клиента используйте `UserType1`, а для второго - `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="0b822-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>

6. <span data-ttu-id="0b822-159">На клиенте `UserType1` выберите один тип подтверждения из раскрывающегося меню и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="0b822-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="0b822-160">Щелкните **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="0b822-160">Click **Request Approval**.</span></span>

7. <span data-ttu-id="0b822-161">В клиенте `UserType2` появится документ, ожидающий утверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="0b822-162">Выберите его и нажмите кнопку **утвердить** или **отклонить**.</span><span class="sxs-lookup"><span data-stu-id="0b822-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="0b822-163">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="0b822-163">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="0b822-164">Выполнение сценария утверждения кворумом</span><span class="sxs-lookup"><span data-stu-id="0b822-164">To run the quorum approval scenario</span></span>

1. <span data-ttu-id="0b822-165">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="0b822-165">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="0b822-166">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="0b822-166">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="0b822-167">Перейдите в папку ApprovalClient\Bin\Debug и запустите три экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="0b822-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="0b822-168">Нажмите кнопку **обнаружить**, дождитесь включения кнопки **Подписка** .</span><span class="sxs-lookup"><span data-stu-id="0b822-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="0b822-169">Введите любое имя пользователя и щелкните **подписываться**.</span><span class="sxs-lookup"><span data-stu-id="0b822-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="0b822-170">Для одного клиента используйте `UserType1`, а для двух других - `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="0b822-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>

6. <span data-ttu-id="0b822-171">В клиенте `UserType1` выберите в раскрывающемся меню утверждение кворумом и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="0b822-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="0b822-172">Щелкните **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="0b822-172">Click **Request Approval**.</span></span> <span data-ttu-id="0b822-173">В данном случае требуется, чтобы два клиента `UserType2` утвердили или отклонили документ.</span><span class="sxs-lookup"><span data-stu-id="0b822-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="0b822-174">Хотя ответить должны оба клиента `UserType2`, для утверждения документа достаточно, чтобы его утвердил один из них.</span><span class="sxs-lookup"><span data-stu-id="0b822-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>

7. <span data-ttu-id="0b822-175">На клиентах `UserType2` появится документ, ожидающий подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="0b822-176">Выберите его и нажмите кнопку **утвердить** или **отклонить**.</span><span class="sxs-lookup"><span data-stu-id="0b822-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="0b822-177">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="0b822-177">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="0b822-178">Выполнение сценария составного утверждения</span><span class="sxs-lookup"><span data-stu-id="0b822-178">To run the complex approval scenario</span></span>

1. <span data-ttu-id="0b822-179">Откройте командную строку с разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="0b822-179">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="0b822-180">Перейдите в каталог, содержащий решение.</span><span class="sxs-lookup"><span data-stu-id="0b822-180">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="0b822-181">Перейдите в папку ApprovalClient\Bin\Debug и запустите четыре экземпляра ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="0b822-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="0b822-182">Нажмите кнопку **обнаружить**, дождитесь включения кнопки **Подписка** .</span><span class="sxs-lookup"><span data-stu-id="0b822-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="0b822-183">Введите любое имя пользователя и щелкните **подписываться**.</span><span class="sxs-lookup"><span data-stu-id="0b822-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="0b822-184">Для одного клиента используйте `UserType1`, для двух других - `UserType2`, а для последнего - `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="0b822-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>

6. <span data-ttu-id="0b822-185">На клиенте `UserType1` выберите один тип подтверждения из раскрывающегося меню и введите имя и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="0b822-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="0b822-186">Щелкните **запросить утверждение**.</span><span class="sxs-lookup"><span data-stu-id="0b822-186">Click **Request Approval**.</span></span>

7. <span data-ttu-id="0b822-187">На клиентах `UserType2` появится документ, ожидающий подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0b822-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="0b822-188">Выберите его и нажмите кнопку **утвердить**. документ передается клиенту `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="0b822-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>

    <span data-ttu-id="0b822-189">Если документ был утвержден первым кворумом `UserType2`, этот документ буден передан клиенту `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="0b822-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>

8. <span data-ttu-id="0b822-190">Утвердите или отклоните документ, полученный от клиента `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="0b822-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="0b822-191">Результаты должны отобразиться на клиенте `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="0b822-191">The results should show in the `UserType1` client.</span></span>

##### <a name="to-clean-up"></a><span data-ttu-id="0b822-192">Очистка</span><span class="sxs-lookup"><span data-stu-id="0b822-192">To clean up</span></span>

1. <span data-ttu-id="0b822-193">В командной строке Visual Studio 2010 перейдите в папку Документаппровалпроцесс и запустите программу Cleanup. cmd.</span><span class="sxs-lookup"><span data-stu-id="0b822-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
