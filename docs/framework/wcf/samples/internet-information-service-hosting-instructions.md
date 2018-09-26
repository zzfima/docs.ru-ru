---
title: Инструкции по размещению в службах IIS
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 303fe47df987901b09cee8cc4292f12bcda2b74d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47204039"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="de444-102">Инструкции по размещению в службах IIS</span><span class="sxs-lookup"><span data-stu-id="de444-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="de444-103">Для выполнения примеров, размещаемых в службах IIS, следует убедиться, что службы IIS правильно установлены и запущены.</span><span class="sxs-lookup"><span data-stu-id="de444-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="de444-104">Установка служб IIS версии 7.5 в Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="de444-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="de444-105">Из **диспетчера серверов**выберите **ролей.**</span><span class="sxs-lookup"><span data-stu-id="de444-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="de444-106">В разделе **Сводка по ролям**, нажмите кнопку **добавления ролей**.</span><span class="sxs-lookup"><span data-stu-id="de444-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="de444-107">Нажмите кнопку **Далее** для отображения **Выбор ролей сервера** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="de444-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="de444-108">Выберите **сервера приложений** из **ролей** , а затем нажмите **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для Роль сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="de444-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="de444-109">Выберите **веб-сервер (IIS)** "флажок".</span><span class="sxs-lookup"><span data-stu-id="de444-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="de444-110">Если вам будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить необходимые компоненты**.</span><span class="sxs-lookup"><span data-stu-id="de444-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="de444-111">Нажмите кнопку **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для роли веб-сервер (IIS).</span><span class="sxs-lookup"><span data-stu-id="de444-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="de444-112">Разверните **средства управления**, а затем разверните **совместимость управления IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="de444-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="de444-113">Выберите **средств 6 работы со сценариями IIS**.</span><span class="sxs-lookup"><span data-stu-id="de444-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="de444-114">Если вам будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить требуемые службы роли**.</span><span class="sxs-lookup"><span data-stu-id="de444-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="de444-115">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="de444-115">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="de444-116">Если элементы выбраны правильно, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="de444-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="de444-117">После завершения установки нажмите кнопку **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="de444-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="de444-118">Установка служб IIS версии 7.5 в Windows 7</span><span class="sxs-lookup"><span data-stu-id="de444-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1.  <span data-ttu-id="de444-119">Нажмите кнопку **запустить**, а затем нажмите кнопку **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="de444-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="de444-120">Откройте **программы** группы.</span><span class="sxs-lookup"><span data-stu-id="de444-120">Open the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="de444-121">В разделе **программы и компоненты**, нажмите кнопку **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="de444-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="de444-122">**Контроль учетных записей пользователей** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="de444-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="de444-123">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="de444-123">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="de444-124">**Функции Windows** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="de444-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="de444-125">Разверните элемент **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="de444-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="de444-126">Разверните элемент **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="de444-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="de444-127">Разверните элемент **компоненты разработки приложений**.</span><span class="sxs-lookup"><span data-stu-id="de444-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="de444-128">Убедитесь, что выбраны следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="de444-128">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="de444-129">**Расширяемость .NET**</span><span class="sxs-lookup"><span data-stu-id="de444-129">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="de444-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="de444-130">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="de444-131">**Расширения ISAPI**</span><span class="sxs-lookup"><span data-stu-id="de444-131">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="de444-132">**Фильтры ISAPI**</span><span class="sxs-lookup"><span data-stu-id="de444-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="de444-133">В элементе **World Wide Web Services**, разверните **общие компоненты Http**.</span><span class="sxs-lookup"><span data-stu-id="de444-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="de444-134">Убедитесь, что **статическое содержимое** выбран.</span><span class="sxs-lookup"><span data-stu-id="de444-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="de444-135">В элементе **World Wide Web Services**, разверните **безопасности**.</span><span class="sxs-lookup"><span data-stu-id="de444-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="de444-136">Убедитесь, что **проверки подлинности Windows** выбран.</span><span class="sxs-lookup"><span data-stu-id="de444-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="de444-137">В разделе **Internet Information Services** directory, разверните элемент **веб-средства управления**, а затем выберите **консоль управления IIS**.</span><span class="sxs-lookup"><span data-stu-id="de444-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="de444-138">Разверните элемент **совместимость управления IIS 6**, а затем выберите **сценариев IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="de444-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="de444-139">В разделе **Internet Information Services** directory, разверните элемент **Microsoft .NET Framework 3.5.1**, а затем выберите **активация Windows Communication Foundation Http**.</span><span class="sxs-lookup"><span data-stu-id="de444-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="de444-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de444-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="de444-141">Установка служб IIS версии 7.0 в Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="de444-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="de444-142">Из **диспетчера серверов**выберите **ролей**.</span><span class="sxs-lookup"><span data-stu-id="de444-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="de444-143">В разделе **Сводка по ролям**, нажмите кнопку **добавления ролей**.</span><span class="sxs-lookup"><span data-stu-id="de444-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="de444-144">Нажмите кнопку **Далее** для отображения **Выбор ролей сервера** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="de444-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="de444-145">Выберите **сервера приложений** из **ролей** , а затем нажмите **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для Роль сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="de444-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="de444-146">Выберите **веб-сервер (IIS)** "флажок".</span><span class="sxs-lookup"><span data-stu-id="de444-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="de444-147">Если вам будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить необходимые компоненты**.</span><span class="sxs-lookup"><span data-stu-id="de444-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="de444-148">Нажмите кнопку **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для роли веб-сервер (IIS).</span><span class="sxs-lookup"><span data-stu-id="de444-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="de444-149">Разверните **средства управления**, а затем разверните **совместимость управления IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="de444-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="de444-150">Выберите **средств 6 работы со сценариями IIS**.</span><span class="sxs-lookup"><span data-stu-id="de444-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="de444-151">Если вам будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить требуемые службы роли**.</span><span class="sxs-lookup"><span data-stu-id="de444-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="de444-152">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="de444-152">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="de444-153">Если элементы выбраны правильно, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="de444-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="de444-154">После завершения установки нажмите кнопку **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="de444-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="de444-155">Установка служб IIS версии 7.0 в Windows Vista</span><span class="sxs-lookup"><span data-stu-id="de444-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1.  <span data-ttu-id="de444-156">Нажмите кнопку Пуск, а затем щелкните «Панель управления».</span><span class="sxs-lookup"><span data-stu-id="de444-156">Click Start, and then click Control Panel.</span></span>  
  
2.  <span data-ttu-id="de444-157">Выберите **программы** группы.</span><span class="sxs-lookup"><span data-stu-id="de444-157">Select the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="de444-158">В разделе **программы и компоненты**, нажмите кнопку **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="de444-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="de444-159">**Контроль учетных записей пользователей** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="de444-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="de444-160">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="de444-160">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="de444-161">**Функции Windows** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="de444-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="de444-162">Разверните элемент **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="de444-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="de444-163">Разверните элемент **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="de444-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="de444-164">Разверните элемент **компоненты разработки приложений**.</span><span class="sxs-lookup"><span data-stu-id="de444-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="de444-165">Убедитесь, что выбраны следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="de444-165">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="de444-166">**Расширяемость .NET**</span><span class="sxs-lookup"><span data-stu-id="de444-166">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="de444-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="de444-167">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="de444-168">**Расширения ISAPI**</span><span class="sxs-lookup"><span data-stu-id="de444-168">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="de444-169">**Фильтры ISAPI**</span><span class="sxs-lookup"><span data-stu-id="de444-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="de444-170">Разверните элемент **веб-средства управления**, а затем выберите **консоль управления IIS**.</span><span class="sxs-lookup"><span data-stu-id="de444-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="de444-171">В элементе **World Wide Web Services**, разверните **общие компоненты Http**.</span><span class="sxs-lookup"><span data-stu-id="de444-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="de444-172">Убедитесь, что **статическое содержимое** выбран.</span><span class="sxs-lookup"><span data-stu-id="de444-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="de444-173">В элементе **World Wide Web Services**, разверните **безопасности**.</span><span class="sxs-lookup"><span data-stu-id="de444-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="de444-174">Убедитесь, что **проверки подлинности Windows** выбран.</span><span class="sxs-lookup"><span data-stu-id="de444-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="de444-175">Разверните элемент **совместимость управления IIS 6**, а затем выберите **сценариев IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="de444-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="de444-176">Разверните элемент **Microsoft .NET Framework 3.0**, а затем выберите **активация Http Windows Communication Foundation**.</span><span class="sxs-lookup"><span data-stu-id="de444-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="de444-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de444-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="de444-178">Установка служб IIS версии 6.0 в Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="de444-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="de444-179">Из **Управление данным сервером**, нажмите кнопку **добавить или удалить роль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="de444-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="de444-180">Выберите **сервер приложений (IIS, ASP.NET)** из **роли сервера** , а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="de444-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="de444-181">Выберите **включить ASP.NET** флажок и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="de444-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="de444-182">Если элементы выбраны правильно, нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="de444-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="de444-183">Установка служб IIS версии 5.1 в Windows XP с установленными пакетами обновления 2 и 3 (SP2 и SP3)</span><span class="sxs-lookup"><span data-stu-id="de444-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1.  <span data-ttu-id="de444-184">На панели управления выберите **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="de444-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="de444-185">В **Установка и удаление программ** диалоговом окне щелкните **Установка и удаление компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="de444-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="de444-186">В **мастер компонентов Windows**выберите **Internet Information Services (IIS)** флажок и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="de444-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="de444-187">Если **файлы, необходимые** диалоговое окно, вставьте диск установки операционной системы, перейдите к папке i386 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de444-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="de444-188">После завершения установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="de444-188">When installation completes, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="de444-189">Закройте **Установка и удаление программ** диалоговое окно, а затем закройте **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="de444-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="de444-190">Проверка установки служб IIS и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="de444-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1.  <span data-ttu-id="de444-191">Сохраните HTML-файл, указанный в конце данного раздела, в корневом каталоге \InetPub\wwwroot и назовите его Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="de444-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2.  <span data-ttu-id="de444-192">Откройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="de444-192">Open a browser window.</span></span>  
  
3.  <span data-ttu-id="de444-193">Тип `http://localhost/Default.aspx` в поле "адрес" и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="de444-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="de444-194">Должна появиться веб-страница с текстом "Здравствуй, мир!".</span><span class="sxs-lookup"><span data-stu-id="de444-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de444-195">При каждой установке новой версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] необходимо повторно регистрировать aspnet_isapi как расширение веб-службы для IIS.</span><span class="sxs-lookup"><span data-stu-id="de444-195">Each time you install a new version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="de444-196">Чтобы сделать это, выполните команду `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="de444-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="de444-197">Пример кода</span><span class="sxs-lookup"><span data-stu-id="de444-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
