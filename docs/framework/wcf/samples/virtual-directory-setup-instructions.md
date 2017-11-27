---
title: "Инструкции по настройке виртуальных каталогов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
caps.latest.revision: "36"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b727f391abfeb1112de1b6cde3ceb564d3860974
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="5cbfe-102">Инструкции по настройке виртуальных каталогов</span><span class="sxs-lookup"><span data-stu-id="5cbfe-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="5cbfe-103">В примерах [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] используется общий виртуальный каталог с именем servicemodelsamples, сопоставленный с папкой %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5cbfe-104">Переменная %SystemDrive% обычно имеет значение C: или D: в зависимости от того, на каком диске установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="5cbfe-105">Можно запустить из файлов Setupvroot.bat и Cleanupvroot.bat [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) для создания виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="5cbfe-106">Если требуется создать виртуальный каталог вручную, воспользуйтесь следующими процедурами.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="5cbfe-107">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5cbfe-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="5cbfe-108">Чтобы создать виртуальный каталог в IIS 7.0 или 7.5</span><span class="sxs-lookup"><span data-stu-id="5cbfe-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="5cbfe-109">Из **запустить** меню, нажмите кнопку **запуска**, затем введите **inetmgr** чтобы открыть оснастку MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5cbfe-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="5cbfe-110">В левой области разверните узел с именем компьютера и разверните **сайтов** узла.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3.  <span data-ttu-id="5cbfe-111">Щелкните правой кнопкой мыши **веб-сайт по умолчанию**и выберите **добавить приложение** Открытие **окно добавления приложения**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4.  <span data-ttu-id="5cbfe-112">В окне введите `servicemodelsamples` как псевдоним для виртуального каталога, для которого создается.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="5cbfe-113">Создайте следующий каталог: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="5cbfe-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6.  <span data-ttu-id="5cbfe-114">Укажите путь к физическому каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="5cbfe-115">Большинство образцов WCF при построении копируют исполняемые файлы службы именно в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7.  <span data-ttu-id="5cbfe-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-116">Click **OK**.</span></span> <span data-ttu-id="5cbfe-117">Веб-приложение для образцов WCF создано.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5cbfe-118">Эта задача должна быть выполнена всего один раз, поскольку все образцы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используют одно и то же веб-приложение servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-118">This task must be performed only once, because all of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5cbfe-119">В этой документации термины `virtual directory` и `Web application` являются синонимами.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="5cbfe-120">Помимо создания виртуального каталога необходимо также задать его свойства, чтобы включить выполняемые службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cbfe-120">In addition to creating the virtual directory, you must also set its properties to enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to run.</span></span> <span data-ttu-id="5cbfe-121">Дополнительные сведения см. далее.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="5cbfe-122">Создание виртуального каталога в IIS 5.1 и 6.0</span><span class="sxs-lookup"><span data-stu-id="5cbfe-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="5cbfe-123">Откройте окно командной строки и введите `start inetmgr` чтобы открыть оснастку MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5cbfe-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="5cbfe-124">В левой области разверните узел с именем компьютера и разверните **веб-сайтов** узла.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3.  <span data-ttu-id="5cbfe-125">Щелкните правой кнопкой мыши **веб-сайт по умолчанию** и выберите **новых, виртуальный каталог** чтобы открыть мастер создания виртуальных каталогов.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4.  <span data-ttu-id="5cbfe-126">В мастере введите `servicemodelsamples` как псевдоним для виртуального каталога, для которого создается.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="5cbfe-127">Укажите путь к каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="5cbfe-128">Большинство примеров [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при построении копируют исполняемые файлы службы именно в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-128">Most of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples copy service executable files to this location when built.</span></span>  
  
6.  <span data-ttu-id="5cbfe-129">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-129">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="5cbfe-130">По умолчанию устанавливаются следующие флажки:</span><span class="sxs-lookup"><span data-stu-id="5cbfe-130">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="5cbfe-131">**Чтение**</span><span class="sxs-lookup"><span data-stu-id="5cbfe-131">**Read**</span></span>  
  
    -   <span data-ttu-id="5cbfe-132">**Запуск скриптов (например, ASP)**</span><span class="sxs-lookup"><span data-stu-id="5cbfe-132">**Run scripts (such as ASP)**</span></span>  
  
8.  <span data-ttu-id="5cbfe-133">Нажмите кнопку **Далее**, а затем нажмите кнопку **Готово** для завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5cbfe-134">Эта задача должна быть выполнена всего один раз, поскольку все образцы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используют один и тот же виртуальный каталог servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-134">This task must be performed only once because all of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="5cbfe-135">Для задания дополнительных свойств виртуального каталога в IIS 7.0 или 7.5</span><span class="sxs-lookup"><span data-stu-id="5cbfe-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="5cbfe-136">Щелкните узел servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="5cbfe-137">В нижней части окна будет указано два представления.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="5cbfe-138">Выберите **Просмотр возможностей** , если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2.  <span data-ttu-id="5cbfe-139">Дважды щелкните запись для **Просмотр каталога**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3.  <span data-ttu-id="5cbfe-140">В области действий выберите **включить** параметр.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="5cbfe-141">Это позволит обращаться к каталогу каталога с помощью веб-обозревателя Internet Explorer, что упростит отладку службы.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="5cbfe-142">Наконец необходимо задать свойства безопасности папки servicemodelsamples, чтобы другие пользователи могли получать доступ к ней.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="5cbfe-143">Дополнительные сведения см. далее.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="5cbfe-144">Задание дополнительных свойств виртуального каталога в IIS 5.1 и 6.0</span><span class="sxs-lookup"><span data-stu-id="5cbfe-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="5cbfe-145">Щелкните правой кнопкой мыши папку servicemodelsamples и выберите команду **свойства**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="5cbfe-146">По умолчанию устанавливаются следующие флажки:</span><span class="sxs-lookup"><span data-stu-id="5cbfe-146">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="5cbfe-147">**Чтение**</span><span class="sxs-lookup"><span data-stu-id="5cbfe-147">**Read**</span></span>  
  
    -   <span data-ttu-id="5cbfe-148">**Запись в журнал**</span><span class="sxs-lookup"><span data-stu-id="5cbfe-148">**Log visits**</span></span>  
  
    -   <span data-ttu-id="5cbfe-149">**Индексация каталога**</span><span class="sxs-lookup"><span data-stu-id="5cbfe-149">**Index this resource**</span></span>  
  
3.  <span data-ttu-id="5cbfe-150">Выберите **просмотр каталогов** флажок.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="5cbfe-151">Это позволит обращаться к каталогу каталога с помощью веб-обозревателя Internet Explorer, что упростит отладку службы.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="5cbfe-152">Для установки свойств безопасности папки в IIS 7.0 или 7.5</span><span class="sxs-lookup"><span data-stu-id="5cbfe-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="5cbfe-153">Перейдите к каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="5cbfe-154">Щелкните правой кнопкой мыши папку servicemodelsamples и выберите **общего ресурса** или **общий доступ к**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3.  <span data-ttu-id="5cbfe-155">Щелкните стрелку вниз слева от **добавить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4.  <span data-ttu-id="5cbfe-156">Выберите **найти** входа.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-156">Select the **Find** entry.</span></span> <span data-ttu-id="5cbfe-157">**Выбор пользователей или групп** открывается окно.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-157">The **Select Users or Groups** window opens.</span></span>  
  
5.  <span data-ttu-id="5cbfe-158">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-158">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="5cbfe-159">Нажмите кнопку **расположения**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-159">Click **Locations**.</span></span> <span data-ttu-id="5cbfe-160">**Расположения** откроется.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-160">The **Locations** window is now open.</span></span>  
  
7.  <span data-ttu-id="5cbfe-161">Выберите запись, соответствующую используемому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="5cbfe-162">Важно выбрать локальный компьютер, а не запись, соответствующую всем перечисленным доменам и сетям.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="5cbfe-163">После выбора компьютера щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-163">After you have selected the computer, click **OK**.</span></span>  
  
8.  <span data-ttu-id="5cbfe-164">Нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-164">Click **Find Now**.</span></span> <span data-ttu-id="5cbfe-165">В результатах поиска появятся объекты, связанные с локальным компьютером.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="5cbfe-166">Найти **IIS_IUSRS** входа в **имя (относительное отличительное имя)** столбца.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="5cbfe-167">Выберите эту запись и нажмите кнопку **ОК** закрыть Поиск окна результатов.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="5cbfe-168">Нажмите кнопку **ОК** закрыть **Выбор пользователей или групп** окна.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="5cbfe-169">Нажмите кнопку **общего ресурса** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="5cbfe-170">После завершения изменений для включения совместного использования, нажмите кнопку **сделать** закрыть **общий доступ к файлам** окна.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="5cbfe-171">Задание свойств безопасности папки в IIS 5.1 и 6.0</span><span class="sxs-lookup"><span data-stu-id="5cbfe-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="5cbfe-172">Перейдите к каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="5cbfe-173">Щелкните правой кнопкой мыши **servicemodelsamples** папку и нажмите кнопку **общий доступ и безопасность.**</span><span class="sxs-lookup"><span data-stu-id="5cbfe-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3.  <span data-ttu-id="5cbfe-174">Перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="5cbfe-174">Click the **Security** tab.</span></span>  
  
4.  <span data-ttu-id="5cbfe-175">При использовании IIS 6.0 в **группы или пользователи** », вкладка «Проверка ли **гостевая учетная запись Интернета** указан.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="5cbfe-176">Если эта учетная запись отсутствует, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-176">If it is not listed:</span></span>  
  
    1.  <span data-ttu-id="5cbfe-177">Нажмите кнопку **запустить** и нажмите кнопку **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="5cbfe-178">Если вы не видите **учетные записи пользователей** значок, нажмите кнопку **переключение к виду по категориям**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3.  <span data-ttu-id="5cbfe-179">Нажмите кнопку **учетные записи пользователей** значок.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-179">Click the **User Accounts** icon.</span></span>  
  
    4.  <span data-ttu-id="5cbfe-180">В разделе «или выберите значок панели управления» щелкните **учетные записи пользователей**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5.  <span data-ttu-id="5cbfe-181">В **учетные записи пользователей** диалоговое окно, нажмите кнопку **Дополнительно** вкладки.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6.  <span data-ttu-id="5cbfe-182">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-182">Click **Advanced**.</span></span>  
  
    7.  <span data-ttu-id="5cbfe-183">В **локальные пользователи и группы** диалоговое окно, щелкните, чтобы развернуть **пользователей** папки.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8.  <span data-ttu-id="5cbfe-184">В области справа дважды щелкните **гостевая учетная запись Интернета**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="5cbfe-185">В **свойства** диалоговое окно, скопируйте имя используется в качестве гостевой учетной записи Интернета.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="5cbfe-186">По умолчанию имя состоит из префикса «USR_» и имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="5cbfe-187">Закройте диалоговое окно **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="5cbfe-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="5cbfe-188">Закрыть **локальные пользователи и группы** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="5cbfe-189">Закрыть **учетные записи пользователей** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="5cbfe-190">Закройте другое **учетные записи пользователей** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="5cbfe-191">В **свойства servicemodelsamples** диалогового **безопасности** щелкните **добавить**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="5cbfe-192">Введите имя компьютера, а затем обратную косую черту, а затем вставьте имя учетной записи пользователя Интернета, например, myMachineName\\% InternetGuestAccountName %</span><span class="sxs-lookup"><span data-stu-id="5cbfe-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="5cbfe-193">Нажмите кнопку **проверить имена** Чтобы проверить добавленное имя.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="5cbfe-194">Если оно допустимо, то будет выделено подчеркиванием и прописными буквами.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5.  <span data-ttu-id="5cbfe-195">Для IIS 6.0, также убедитесь, что СЕТЕВОЙ службы указано в **имена групп или пользователей** поле.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="5cbfe-196">Если учетная запись NETWORK SERVICE отсутствует, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1.  <span data-ttu-id="5cbfe-197">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-197">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="5cbfe-198">В **Выбор пользователей или групп** диалоговое окно, введите имя компьютера, а затем обратную косую черту.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3.  <span data-ttu-id="5cbfe-199">Тип **службы** после обратной косой черты (без пробела).</span><span class="sxs-lookup"><span data-stu-id="5cbfe-199">Type **service** after the backslash (no space).</span></span>  
  
    4.  <span data-ttu-id="5cbfe-200">Нажмите кнопку **проверить имена**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-200">Click **Check names**.</span></span>  
  
    5.  <span data-ttu-id="5cbfe-201">Если найдено несколько имен, выберите **сетевая служба** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="5cbfe-202">Нажмите кнопку **ОК** закрыть **Выбор пользователей или групп** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6.  <span data-ttu-id="5cbfe-203">При использовании Windows XP SP2 и IIS 5.1, проверьте, что гостевая учетная запись Интернета и ASPNET, перечислены в **имена групп или пользователей** поле.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="5cbfe-204">Обратите внимание, что пользователь ASPNET может быть членом встроенной **пользователей** группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="5cbfe-205">Если Да, если **пользователей** группа указана в диалоговом окне, необходимо добавить его как отдельный элемент в список разрешенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="5cbfe-206">Чтобы проверить, что ASPNET входит из **пользователей** группы безопасности:</span><span class="sxs-lookup"><span data-stu-id="5cbfe-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1.  <span data-ttu-id="5cbfe-207">На **запустить** меню, нажмите кнопку **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="5cbfe-208">Нажмите кнопку **учетные записи пользователей** значок.</span><span class="sxs-lookup"><span data-stu-id="5cbfe-208">Click the **User Accounts** icon.</span></span>  
  
    3.  <span data-ttu-id="5cbfe-209">В **группы** столбца, убедитесь, что значение для **ASPNET** — «Пользователи».</span><span class="sxs-lookup"><span data-stu-id="5cbfe-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbfe-210">См. также</span><span class="sxs-lookup"><span data-stu-id="5cbfe-210">See Also</span></span>  
 [<span data-ttu-id="5cbfe-211">Инструкции по размещению IIS службы Интернета</span><span class="sxs-lookup"><span data-stu-id="5cbfe-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
