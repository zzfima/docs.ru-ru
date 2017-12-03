---
title: "Инструкции по размещению в службах IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7dd9d70a3b93faf721b5ac3bbd5f1114bf5c1461
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="cf908-102">Инструкции по размещению в службах IIS</span><span class="sxs-lookup"><span data-stu-id="cf908-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="cf908-103">Для выполнения примеров, размещаемых в службах IIS, следует убедиться, что службы IIS правильно установлены и запущены.</span><span class="sxs-lookup"><span data-stu-id="cf908-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="cf908-104">Установка служб IIS версии 7.5 в Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="cf908-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="cf908-105">Из **диспетчера сервера**выберите **ролей.**</span><span class="sxs-lookup"><span data-stu-id="cf908-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="cf908-106">В разделе **Сводка по ролям**, нажмите кнопку **Добавить роли**.</span><span class="sxs-lookup"><span data-stu-id="cf908-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="cf908-107">Нажмите кнопку **Далее** для отображения **Выбор ролей сервера** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="cf908-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="cf908-108">Выберите **сервера приложений** из **ролей** , а затем нажмите **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для Роль сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="cf908-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="cf908-109">Выберите **веб-сервер (IIS)** флажок.</span><span class="sxs-lookup"><span data-stu-id="cf908-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="cf908-110">Если будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить необходимые компоненты**.</span><span class="sxs-lookup"><span data-stu-id="cf908-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="cf908-111">Нажмите кнопку **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для роли веб-сервер (IIS).</span><span class="sxs-lookup"><span data-stu-id="cf908-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="cf908-112">Разверните **средства управления**, а затем разверните **совместимость управления IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cf908-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="cf908-113">Выберите **IIS 6 сценариев средства**.</span><span class="sxs-lookup"><span data-stu-id="cf908-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="cf908-114">Если будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить требуемые службы роли**.</span><span class="sxs-lookup"><span data-stu-id="cf908-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="cf908-115">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf908-115">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cf908-116">Если элементы выбраны правильно, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="cf908-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="cf908-117">По завершении установки нажмите кнопку **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cf908-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="cf908-118">Установка служб IIS версии 7.5 в Windows 7</span><span class="sxs-lookup"><span data-stu-id="cf908-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1.  <span data-ttu-id="cf908-119">Нажмите кнопку **запустить**, а затем нажмите кнопку **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="cf908-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="cf908-120">Откройте **программы** группы.</span><span class="sxs-lookup"><span data-stu-id="cf908-120">Open the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="cf908-121">В разделе **программы и компоненты**, нажмите кнопку **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="cf908-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="cf908-122">**Контроль учетных записей пользователей** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="cf908-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="cf908-123">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="cf908-123">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="cf908-124">**Компоненты Windows** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="cf908-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="cf908-125">Разверните элемент **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="cf908-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="cf908-126">Разверните элемент **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="cf908-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="cf908-127">Разверните элемент **компоненты разработки приложений**.</span><span class="sxs-lookup"><span data-stu-id="cf908-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="cf908-128">Убедитесь, что выбраны следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="cf908-128">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="cf908-129">**Расширяемость .NET**</span><span class="sxs-lookup"><span data-stu-id="cf908-129">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="cf908-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="cf908-130">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="cf908-131">**Расширения ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cf908-131">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="cf908-132">**Фильтры ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cf908-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="cf908-133">В элементе **World Wide Web Services**, разверните **основные возможности Http**.</span><span class="sxs-lookup"><span data-stu-id="cf908-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="cf908-134">Убедитесь, что **статического содержимого** выбран.</span><span class="sxs-lookup"><span data-stu-id="cf908-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="cf908-135">В элементе **World Wide Web Services**, разверните **безопасности**.</span><span class="sxs-lookup"><span data-stu-id="cf908-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="cf908-136">Убедитесь, что **проверки подлинности Windows** выбран.</span><span class="sxs-lookup"><span data-stu-id="cf908-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="cf908-137">В разделе **Internet Information Services** каталога, разверните элемент **веб-средства управления**и выберите **консоль управления IIS**.</span><span class="sxs-lookup"><span data-stu-id="cf908-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="cf908-138">Разверните элемент **совместимость управления IIS 6**, а затем выберите **сценариев IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cf908-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="cf908-139">В разделе **Internet Information Services** каталога, разверните элемент **Microsoft .NET Framework 3.5.1**, а затем выберите **активация Windows Communication Foundation Http**.</span><span class="sxs-lookup"><span data-stu-id="cf908-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="cf908-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cf908-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="cf908-141">Установка служб IIS версии 7.0 в Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="cf908-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="cf908-142">Из **диспетчера сервера**выберите **ролей**.</span><span class="sxs-lookup"><span data-stu-id="cf908-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="cf908-143">В разделе **Сводка по ролям**, нажмите кнопку **Добавить роли**.</span><span class="sxs-lookup"><span data-stu-id="cf908-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="cf908-144">Нажмите кнопку **Далее** для отображения **Выбор ролей сервера** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="cf908-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="cf908-145">Выберите **сервера приложений** из **ролей** , а затем нажмите **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для Роль сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="cf908-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="cf908-146">Выберите **веб-сервер (IIS)** флажок.</span><span class="sxs-lookup"><span data-stu-id="cf908-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="cf908-147">Если будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить необходимые компоненты**.</span><span class="sxs-lookup"><span data-stu-id="cf908-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="cf908-148">Нажмите кнопку **Далее** дважды, чтобы отобразить **Выбор служб ролей** диалоговое окно для роли веб-сервер (IIS).</span><span class="sxs-lookup"><span data-stu-id="cf908-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="cf908-149">Разверните **средства управления**, а затем разверните **совместимость управления IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cf908-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="cf908-150">Выберите **IIS 6 сценариев средства**.</span><span class="sxs-lookup"><span data-stu-id="cf908-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="cf908-151">Если будет предложено установить дополнительные службы ролей и компоненты, нажмите кнопку **добавить требуемые службы роли**.</span><span class="sxs-lookup"><span data-stu-id="cf908-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="cf908-152">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf908-152">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cf908-153">Если элементы выбраны правильно, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="cf908-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="cf908-154">По завершении установки нажмите кнопку **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cf908-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="cf908-155">Установка служб IIS версии 7.0 в Windows Vista</span><span class="sxs-lookup"><span data-stu-id="cf908-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1.  <span data-ttu-id="cf908-156">Нажмите кнопку Пуск, а затем щелкните «Панель управления».</span><span class="sxs-lookup"><span data-stu-id="cf908-156">Click Start, and then click Control Panel.</span></span>  
  
2.  <span data-ttu-id="cf908-157">Выберите **программы** группы.</span><span class="sxs-lookup"><span data-stu-id="cf908-157">Select the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="cf908-158">В разделе **программы и компоненты**, нажмите кнопку **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="cf908-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="cf908-159">**Контроль учетных записей пользователей** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="cf908-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="cf908-160">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="cf908-160">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="cf908-161">**Компоненты Windows** отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="cf908-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="cf908-162">Разверните элемент **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="cf908-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="cf908-163">Разверните элемент **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="cf908-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="cf908-164">Разверните элемент **компоненты разработки приложений**.</span><span class="sxs-lookup"><span data-stu-id="cf908-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="cf908-165">Убедитесь, что выбраны следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="cf908-165">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="cf908-166">**Расширяемость .NET**</span><span class="sxs-lookup"><span data-stu-id="cf908-166">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="cf908-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="cf908-167">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="cf908-168">**Расширения ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cf908-168">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="cf908-169">**Фильтры ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cf908-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="cf908-170">Разверните элемент **веб-средства управления**, а затем выберите **консоль управления IIS**.</span><span class="sxs-lookup"><span data-stu-id="cf908-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="cf908-171">В элементе **World Wide Web Services**, разверните **основные возможности Http**.</span><span class="sxs-lookup"><span data-stu-id="cf908-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="cf908-172">Убедитесь, что **статического содержимого** выбран.</span><span class="sxs-lookup"><span data-stu-id="cf908-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="cf908-173">В элементе **World Wide Web Services**, разверните **безопасности**.</span><span class="sxs-lookup"><span data-stu-id="cf908-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="cf908-174">Убедитесь, что **проверки подлинности Windows** выбран.</span><span class="sxs-lookup"><span data-stu-id="cf908-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="cf908-175">Разверните элемент **совместимость управления IIS 6**, а затем выберите **сценариев IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cf908-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="cf908-176">Разверните элемент **Microsoft .NET Framework 3.0**, а затем выберите **активация Windows Communication Foundation Http**.</span><span class="sxs-lookup"><span data-stu-id="cf908-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="cf908-177">Нажмите кнопку**ОК**.</span><span class="sxs-lookup"><span data-stu-id="cf908-177">Click**OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="cf908-178">Установка служб IIS версии 6.0 в Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="cf908-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="cf908-179">Из **управление сервером**, нажмите кнопку **добавить или удалить роль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf908-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="cf908-180">Выберите **сервер приложений (IIS, ASP.NET)** из **роли сервера** , а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf908-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="cf908-181">Выберите **включить ASP.NET** флажок и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf908-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="cf908-182">Если элементы выбраны правильно, нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="cf908-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="cf908-183">Установка служб IIS версии 5.1 в Windows XP с установленными пакетами обновления 2 и 3 (SP2 и SP3)</span><span class="sxs-lookup"><span data-stu-id="cf908-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1.  <span data-ttu-id="cf908-184">В панели управления выберите **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="cf908-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="cf908-185">В **Установка и удаление программ** диалоговое окно, нажмите кнопку **компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="cf908-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="cf908-186">В **мастер компонентов Windows**выберите **Internet Information Services (IIS)** флажок и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf908-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="cf908-187">Если **файлы, необходимые** диалоговое окно, вставьте диск установки операционной системы, перейдите в папку i386 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cf908-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cf908-188">По завершении установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cf908-188">When installation completes, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="cf908-189">Закройте **Установка и удаление программ** диалоговое окно, а затем закройте **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="cf908-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="cf908-190">Проверка установки служб IIS и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf908-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1.  <span data-ttu-id="cf908-191">Сохраните HTML-файл, указанный в конце данного раздела, в корневом каталоге \InetPub\wwwroot и назовите его Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="cf908-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2.  <span data-ttu-id="cf908-192">Откройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="cf908-192">Open a browser window.</span></span>  
  
3.  <span data-ttu-id="cf908-193">Тип `http://localhost/Default.aspx` в адресной строке и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="cf908-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="cf908-194">Должна появиться веб-страница с текстом "Здравствуй, мир!".</span><span class="sxs-lookup"><span data-stu-id="cf908-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf908-195">При каждой установке новой версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] необходимо повторно регистрировать aspnet_isapi как расширение веб-службы для IIS.</span><span class="sxs-lookup"><span data-stu-id="cf908-195">Each time you install a new version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="cf908-196">Чтобы сделать это, выполните команду `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="cf908-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="cf908-197">Пример кода</span><span class="sxs-lookup"><span data-stu-id="cf908-197">Sample Code</span></span>  
  
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
