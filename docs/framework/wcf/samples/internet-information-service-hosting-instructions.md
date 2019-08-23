---
title: Инструкции по размещению в службах IIS
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 226b47bfd90dc4cffb0a364a804016043cc25d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929114"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="43fff-102">Инструкции по размещению в службах IIS</span><span class="sxs-lookup"><span data-stu-id="43fff-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="43fff-103">Для выполнения примеров, размещаемых в службах IIS, следует убедиться, что службы IIS правильно установлены и запущены.</span><span class="sxs-lookup"><span data-stu-id="43fff-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="43fff-104">Установка служб IIS версии 7.5 в Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="43fff-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="43fff-105">В **Диспетчер сервера**выберите **роли.**</span><span class="sxs-lookup"><span data-stu-id="43fff-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="43fff-106">В разделе **Сводка по ролям**щелкните **Добавить роли**.</span><span class="sxs-lookup"><span data-stu-id="43fff-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="43fff-107">Нажмите кнопку **Далее** , чтобы открыть диалоговое окно **Выбор ролей сервера** .</span><span class="sxs-lookup"><span data-stu-id="43fff-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="43fff-108">Выберите **сервер приложений** в списке **роли** , а затем дважды нажмите кнопку **Далее** , чтобы открыть диалоговое окно **Выбор служб ролей** для роли сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="43fff-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="43fff-109">Установите флажок **веб-сервер (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="43fff-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="43fff-110">Если будет предложено установить дополнительные службы ролей и компоненты, щелкните **Добавить необходимые компоненты**.</span><span class="sxs-lookup"><span data-stu-id="43fff-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="43fff-111">Дважды нажмите кнопку **Далее** , чтобы отобразить диалоговое окно **Выбор служб ролей** для роли веб-сервера (IIS).</span><span class="sxs-lookup"><span data-stu-id="43fff-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="43fff-112">Разверните узел **средства управления**, а затем узел **Совместимость управления IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="43fff-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="43fff-113">Выберите пункт **средства работы со скриптами IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="43fff-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="43fff-114">Если будет предложено установить дополнительные службы ролей и компоненты, щелкните **Добавить необходимые службы ролей**.</span><span class="sxs-lookup"><span data-stu-id="43fff-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="43fff-115">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43fff-115">Click **Next**.</span></span>  
  
6. <span data-ttu-id="43fff-116">Если сводка выбора правильная, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="43fff-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="43fff-117">После завершения установки нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="43fff-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="43fff-118">Установка служб IIS версии 7.5 в Windows 7</span><span class="sxs-lookup"><span data-stu-id="43fff-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="43fff-119">Нажмите кнопку **Пуск**и выберите **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="43fff-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="43fff-120">Откройте группу **программы** .</span><span class="sxs-lookup"><span data-stu-id="43fff-120">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="43fff-121">В разделе **программы и компоненты**щелкните **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="43fff-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="43fff-122">Откроется диалоговое окно **контроль учетных записей пользователей** .</span><span class="sxs-lookup"><span data-stu-id="43fff-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="43fff-123">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="43fff-123">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="43fff-124">Откроется диалоговое окно **компоненты Windows** .</span><span class="sxs-lookup"><span data-stu-id="43fff-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="43fff-125">Разверните элемент с меткой **службы IIS**.</span><span class="sxs-lookup"><span data-stu-id="43fff-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="43fff-126">Разверните элемент, помеченный как **службы**Интернета.</span><span class="sxs-lookup"><span data-stu-id="43fff-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="43fff-127">Разверните элемент **Компоненты разработки приложений**.</span><span class="sxs-lookup"><span data-stu-id="43fff-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="43fff-128">Убедитесь, что выбраны следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="43fff-128">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="43fff-129">**Расширяемость .NET**</span><span class="sxs-lookup"><span data-stu-id="43fff-129">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="43fff-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="43fff-130">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="43fff-131">**Расширения ISAPI**</span><span class="sxs-lookup"><span data-stu-id="43fff-131">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="43fff-132">**Фильтры ISAPI**</span><span class="sxs-lookup"><span data-stu-id="43fff-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="43fff-133">В элементе **веб-службы в Интернете**разверните узел **Общие функции HTTP**.</span><span class="sxs-lookup"><span data-stu-id="43fff-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="43fff-134">Убедитесь, что выбрано **статическое содержимое** .</span><span class="sxs-lookup"><span data-stu-id="43fff-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="43fff-135">Под элементом **веб-службы в Интернете**разверните узел **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="43fff-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="43fff-136">Убедитесь, что выбрана **Проверка подлинности Windows** .</span><span class="sxs-lookup"><span data-stu-id="43fff-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="43fff-137">В каталоге **службы IIS** разверните элемент **средства управления веб-** узлом, а затем выберите **консоль управления IIS**.</span><span class="sxs-lookup"><span data-stu-id="43fff-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="43fff-138">Разверните элемент с меткой **Совместимость управления IIS 6**, а затем выберите пункт **средства создания скриптов IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="43fff-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="43fff-139">В каталоге **службы IIS** разверните элемент **Microsoft .NET Framework 3.5.1**, а затем выберите **Windows Communication Foundation HTTP Activation**.</span><span class="sxs-lookup"><span data-stu-id="43fff-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="43fff-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="43fff-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="43fff-141">Установка служб IIS версии 7.0 в Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="43fff-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="43fff-142">В **Диспетчер сервера**выберите **роли**.</span><span class="sxs-lookup"><span data-stu-id="43fff-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="43fff-143">В разделе **Сводка по ролям**щелкните **Добавить роли**.</span><span class="sxs-lookup"><span data-stu-id="43fff-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="43fff-144">Нажмите кнопку **Далее** , чтобы открыть диалоговое окно **Выбор ролей сервера** .</span><span class="sxs-lookup"><span data-stu-id="43fff-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="43fff-145">Выберите **сервер приложений** в списке **роли** , а затем дважды нажмите кнопку **Далее** , чтобы открыть диалоговое окно **Выбор служб ролей** для роли сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="43fff-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="43fff-146">Установите флажок **веб-сервер (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="43fff-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="43fff-147">Если будет предложено установить дополнительные службы ролей и компоненты, щелкните **Добавить необходимые компоненты**.</span><span class="sxs-lookup"><span data-stu-id="43fff-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="43fff-148">Дважды нажмите кнопку **Далее** , чтобы отобразить диалоговое окно **Выбор служб ролей** для роли веб-сервера (IIS).</span><span class="sxs-lookup"><span data-stu-id="43fff-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="43fff-149">Разверните узел **средства управления**, а затем узел **Совместимость управления IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="43fff-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="43fff-150">Выберите пункт **средства работы со скриптами IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="43fff-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="43fff-151">Если будет предложено установить дополнительные службы ролей и компоненты, щелкните **Добавить необходимые службы ролей**.</span><span class="sxs-lookup"><span data-stu-id="43fff-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="43fff-152">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43fff-152">Click **Next**.</span></span>  
  
6. <span data-ttu-id="43fff-153">Если сводка выбора правильная, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="43fff-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="43fff-154">После завершения установки нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="43fff-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="43fff-155">Установка служб IIS версии 7.0 в Windows Vista</span><span class="sxs-lookup"><span data-stu-id="43fff-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="43fff-156">Нажмите кнопку Пуск, а затем щелкните «Панель управления».</span><span class="sxs-lookup"><span data-stu-id="43fff-156">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="43fff-157">Выберите группу **программы** .</span><span class="sxs-lookup"><span data-stu-id="43fff-157">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="43fff-158">В разделе **программы и компоненты**щелкните **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="43fff-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="43fff-159">Откроется диалоговое окно **контроль учетных записей пользователей** .</span><span class="sxs-lookup"><span data-stu-id="43fff-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="43fff-160">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="43fff-160">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="43fff-161">Откроется диалоговое окно **компоненты Windows** .</span><span class="sxs-lookup"><span data-stu-id="43fff-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="43fff-162">Разверните элемент с меткой **службы IIS**.</span><span class="sxs-lookup"><span data-stu-id="43fff-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="43fff-163">Разверните элемент, помеченный как **службы**Интернета.</span><span class="sxs-lookup"><span data-stu-id="43fff-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="43fff-164">Разверните элемент **Компоненты разработки приложений**.</span><span class="sxs-lookup"><span data-stu-id="43fff-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="43fff-165">Убедитесь, что выбраны следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="43fff-165">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="43fff-166">**Расширяемость .NET**</span><span class="sxs-lookup"><span data-stu-id="43fff-166">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="43fff-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="43fff-167">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="43fff-168">**Расширения ISAPI**</span><span class="sxs-lookup"><span data-stu-id="43fff-168">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="43fff-169">**Фильтры ISAPI**</span><span class="sxs-lookup"><span data-stu-id="43fff-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="43fff-170">Разверните элемент **средства управления веб-сайтами**, а затем выберите **консоль управления IIS**.</span><span class="sxs-lookup"><span data-stu-id="43fff-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="43fff-171">В элементе **веб-службы в Интернете**разверните узел **Общие функции HTTP**.</span><span class="sxs-lookup"><span data-stu-id="43fff-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="43fff-172">Убедитесь, что выбрано **статическое содержимое** .</span><span class="sxs-lookup"><span data-stu-id="43fff-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="43fff-173">Под элементом **веб-службы в Интернете**разверните узел **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="43fff-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="43fff-174">Убедитесь, что выбрана **Проверка подлинности Windows** .</span><span class="sxs-lookup"><span data-stu-id="43fff-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="43fff-175">Разверните элемент с меткой **Совместимость управления IIS 6**, а затем выберите пункт **средства создания скриптов IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="43fff-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="43fff-176">Разверните элемент, помеченный **Microsoft .NET Framework 3,0**, а затем выберите **Windows Communication Foundation HTTP Activation**.</span><span class="sxs-lookup"><span data-stu-id="43fff-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="43fff-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="43fff-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="43fff-178">Установка служб IIS версии 6.0 в Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="43fff-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="43fff-179">В меню **Управление сервером**выберите команду **Добавить или удалить роль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43fff-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="43fff-180">Выберите **сервер приложений (IIS, ASP.NET)** в списке **роль сервера** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43fff-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="43fff-181">Установите флажок **включить ASP.NET** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43fff-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="43fff-182">Если элементы выбраны правильно, нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="43fff-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="43fff-183">Установка служб IIS версии 5.1 в Windows XP с установленными пакетами обновления 2 и 3 (SP2 и SP3)</span><span class="sxs-lookup"><span data-stu-id="43fff-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="43fff-184">На панели управления щелкните элемент **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="43fff-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="43fff-185">В диалоговом окне **Установка и удаление программ** щелкните элемент **Установка и удаление компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="43fff-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="43fff-186">В **мастере компонентов Windows**установите флажок **службы IIS (IIS)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43fff-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="43fff-187">Если появится диалоговое окно **необходимые файлы** , вставьте установочный диск операционной системы, перейдите в папку i386 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="43fff-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="43fff-188">После завершения установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="43fff-188">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="43fff-189">Закройте диалоговое окно **Установка и удаление программ** и закройте **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="43fff-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="43fff-190">Проверка установки служб IIS и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43fff-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="43fff-191">Сохраните HTML-файл, указанный в конце данного раздела, в корневом каталоге \InetPub\wwwroot и назовите его Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="43fff-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="43fff-192">Откройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="43fff-192">Open a browser window.</span></span>  
  
3. <span data-ttu-id="43fff-193">Введите `http://localhost/Default.aspx` в поле адрес и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="43fff-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="43fff-194">Должна появиться веб-страница с текстом "Здравствуй, мир!".</span><span class="sxs-lookup"><span data-stu-id="43fff-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43fff-195">Каждый раз при установке новой версии .NET Framework необходимо повторно зарегистрировать Aspnet_isapi в качестве расширения веб-службы для IIS.</span><span class="sxs-lookup"><span data-stu-id="43fff-195">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="43fff-196">Чтобы сделать это, выполните команду `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="43fff-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="43fff-197">Пример кода</span><span class="sxs-lookup"><span data-stu-id="43fff-197">Sample Code</span></span>  
  
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
