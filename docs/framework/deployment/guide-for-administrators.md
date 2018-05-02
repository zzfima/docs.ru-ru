---
title: Руководство по развертыванию .NET Framework для администраторов
ms.custom: ''
ms.date: 04/10/2018
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
caps.latest.revision: 40
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 67efb04fc0d86a20fdf10c0e84bb00ae57383bb1
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="eda28-102">Руководство по развертыванию .NET Framework для администраторов</span><span class="sxs-lookup"><span data-stu-id="eda28-102">.NET Framework Deployment Guide for Administrators</span></span>
<span data-ttu-id="eda28-103">В этой статье представлено пошаговое описание развертывания администратором платформы [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и системных зависимостей в сети с помощью Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-103">This step-by-step article describes how a system administrator can deploy the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and its system dependencies across a network by using Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="eda28-104">В рамках этой статьи предполагается, что все целевые клиентские компьютеры соответствуют минимальным требованиям для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eda28-104">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="eda28-105">Список требований к программному обеспечению и оборудованию для установки [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] см. в разделе [Требования к системе](../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eda28-105">For a list of the software and hardware requirements for installing the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], see [System Requirements](../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eda28-106">Упоминаемое в этом документе программное обеспечение, в том числе [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], System Center Configuration Manager и Active Directory, используется в соответствии с условиями лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="eda28-106">The software referenced in this document, including, without limitation, the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], System Center Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="eda28-107">В приведенных здесь инструкциях предполагается, что эти условия лицензионного соглашения были прочитаны и приняты соответствующими приобретателями лицензий на программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="eda28-107">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="eda28-108">Данные инструкции не предполагают отказа от каких-либо условий этих лицензионных соглашений.</span><span class="sxs-lookup"><span data-stu-id="eda28-108">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>  
>   
>  <span data-ttu-id="eda28-109">Сведения о поддержке платформы .NET Framework см. на странице [Политика жизненного цикла поддержки платформы Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=196607) веб-сайта поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eda28-109">For information about support for the .NET Framework, see [Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/?LinkId=196607) on the Microsoft Support website.</span></span>  
  
 <span data-ttu-id="eda28-110">В этом разделе содержатся следующие подразделы.</span><span class="sxs-lookup"><span data-stu-id="eda28-110">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="eda28-111">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="eda28-111">The deployment process</span></span>](#the_deployment_process)  
 [<span data-ttu-id="eda28-112">Развертывание .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eda28-112">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)  
 [<span data-ttu-id="eda28-113">Создание коллекции</span><span class="sxs-lookup"><span data-stu-id="eda28-113">Create a collection</span></span>](#creating_a_collection)  
 [<span data-ttu-id="eda28-114">Создание пакета и программы</span><span class="sxs-lookup"><span data-stu-id="eda28-114">Create a package and program</span></span>](#creating_a_package)  
 [<span data-ttu-id="eda28-115">Выбор точки распространения</span><span class="sxs-lookup"><span data-stu-id="eda28-115">Select a distribution point</span></span>](#select_dist_point)  
 [<span data-ttu-id="eda28-116">Развертывание пакета</span><span class="sxs-lookup"><span data-stu-id="eda28-116">Deploy the package</span></span>](#deploying_package)  
[<span data-ttu-id="eda28-117">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="eda28-117">Resources</span></span>](#resources)  
[<span data-ttu-id="eda28-118">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="eda28-118">Troubleshooting</span></span>](#troubleshooting)  
  
<a name="the_deployment_process"></a>   
## <a name="the-deployment-process"></a><span data-ttu-id="eda28-119">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="eda28-119">The deployment process</span></span>  
 <span data-ttu-id="eda28-120">После создания инфраструктуры поддержки распространяемый пакет .NET Framework можно развернуть на компьютерах сети с помощью System Center 2012 Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-120">When you have the supporting infrastructure in place, you use System Center 2012 Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="eda28-121">Построение инфраструктуры включает в себя создание и определение пяти основных областей: коллекции, пакет и программа для программного обеспечения, точки распространения и развертывания.</span><span class="sxs-lookup"><span data-stu-id="eda28-121">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>  
  
-   <span data-ttu-id="eda28-122">**Коллекции** — группы ресурсов Configuration Manager, такие как пользователи, группы пользователей или компьютеры, на которых развертывается .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eda28-122">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="eda28-123">Дополнительные сведения см. в статье [Коллекции в Configuration Manager](http://technet.microsoft.com/library/gg682169.aspx) в библиотеке документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-123">For more information, see [Collections in Configuration Manager](http://technet.microsoft.com/library/gg682169.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="eda28-124">**Пакеты и программы** обычно представляют программные приложения, которые подлежат установке на клиентском компьютере. Сюда также могут относиться отдельные файлы, обновления и даже отдельные команды.</span><span class="sxs-lookup"><span data-stu-id="eda28-124">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="eda28-125">Дополнительные сведения см. в статье [Пакеты и программы в Configuration Manager](http://technet.microsoft.com/library/gg699369.aspx) в библиотеке документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-125">For more information, see [Packages and Programs in Configuration Manager](http://technet.microsoft.com/library/gg699369.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="eda28-126">**Точки распространения** — роли системы сайта Configuration Manager, где хранятся файлы, необходимые для работы программного обеспечения на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="eda28-126">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="eda28-127">Когда клиент Configuration Manager получает и обрабатывает развертывание программного обеспечения, он связывается с точкой распространения для загрузки содержимого, связанного с программным обеспечением, и запуска процесса установки.</span><span class="sxs-lookup"><span data-stu-id="eda28-127">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="eda28-128">Дополнительные сведения см. в статье [Введение в управление содержимым с помощью Configuration Manager](http://technet.microsoft.com/library/gg682083.aspx) в библиотеке документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-128">For more information, see [Introduction to content Management in Configuration Manager](http://technet.microsoft.com/library/gg682083.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="eda28-129">**Развертывания** сообщают подходящим членам целевой коллекции о необходимости установить программный пакет.</span><span class="sxs-lookup"><span data-stu-id="eda28-129">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span> <span data-ttu-id="eda28-130">Дополнительные сведения см. в статье [Развертывание приложений в Configuration Manager](http://technet.microsoft.com/library/gg682082.aspx) в библиотеке документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-130">For more information, see [How to Deploy Applications in Configuration Manager](http://technet.microsoft.com/library/gg682082.aspx) in the Configuration Manager documentation library.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eda28-131">Процедуры в этом разделе содержат обычные параметры для создания и развертывания пакета и программы и могут не охватывать все возможные настройки.</span><span class="sxs-lookup"><span data-stu-id="eda28-131">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="eda28-132">Другие варианты развертывания Configuration Manager см. в [библиотеке документации по Configuration Manager](http://technet.microsoft.com/library/gg682041.aspx).</span><span class="sxs-lookup"><span data-stu-id="eda28-132">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](http://technet.microsoft.com/library/gg682041.aspx).</span></span>  
  
<a name="deploying_in_a_test_environment"></a>   
## <a name="deploying-the-net-framework"></a><span data-ttu-id="eda28-133">Развертывание .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eda28-133">Deploying the .NET Framework</span></span>  
 <span data-ttu-id="eda28-134">Для развертывания автоматической установки платформы [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], при которой пользователи не участвуют в процессе установки, можно использовать System Center 2012 Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-134">You can use System Center 2012 Configuration Manager to deploy a silent installation of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], where the users do not interact with the installation process.</span></span> <span data-ttu-id="eda28-135">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="eda28-135">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="eda28-136">[Создайте коллекцию](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="eda28-136">[Create a collection](#creating_a_collection).</span></span>  
  
2.  <span data-ttu-id="eda28-137">[Создайте пакет и программу для распространяемого пакета .NET Framework](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="eda28-137">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>  
  
3.  <span data-ttu-id="eda28-138">[Выберите точку распространения](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="eda28-138">[Select a distribution point](#select_dist_point).</span></span>  
  
4.  <span data-ttu-id="eda28-139">[Осуществите развертывание пакета](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="eda28-139">[Deploy the package](#deploying_package).</span></span>  
  
<a name="creating_a_collection"></a>   
### <a name="create-a-collection"></a><span data-ttu-id="eda28-140">Создание коллекции</span><span class="sxs-lookup"><span data-stu-id="eda28-140">Create a collection</span></span>  
 <span data-ttu-id="eda28-141">На этом этапе необходимо выбрать компьютеры, на которых будет выполнено развертывание пакета и программы, и объединить их в коллекцию устройств.</span><span class="sxs-lookup"><span data-stu-id="eda28-141">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="eda28-142">Для создания коллекции в Configuration Manager можно использовать правила непосредственного членства (где необходимо вручную указать членов коллекции) или правила запросов (где Configuration Manager определяет членов коллекции на основе заданных критериев).</span><span class="sxs-lookup"><span data-stu-id="eda28-142">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="eda28-143">Дополнительные сведения о правилах членства, включая правила непосредственного членства и правила запросов, см. в статье [Введение в коллекции в Configuration Manager](http://technet.microsoft.com/library/gg682177.aspx) в библиотеке документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-143">For more information about membership rules, including queries and direct rules, see [Introduction to Collections in Configuration Manager](http://technet.microsoft.com/library/gg682177.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
 <span data-ttu-id="eda28-144">Создание коллекции</span><span class="sxs-lookup"><span data-stu-id="eda28-144">To create a collection:</span></span>  
  
1.  <span data-ttu-id="eda28-145">В консоли Configuration Manager выберите **Активы и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="eda28-145">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>  
  
2.  <span data-ttu-id="eda28-146">В рабочей области **Активы и соответствие** выберите **Коллекции устройств**.</span><span class="sxs-lookup"><span data-stu-id="eda28-146">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>  
  
3.  <span data-ttu-id="eda28-147">На вкладке **Главная** в группе **Создать** выберите **Создать коллекцию устройств**.</span><span class="sxs-lookup"><span data-stu-id="eda28-147">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>  
  
4.  <span data-ttu-id="eda28-148">На странице**Общие** **мастера создания коллекций устройств** введите имя коллекции.</span><span class="sxs-lookup"><span data-stu-id="eda28-148">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>  
  
5.  <span data-ttu-id="eda28-149">Выберите **Обзор**, чтобы определить ограничивающую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="eda28-149">Choose **Browse** to specify a limiting collection.</span></span>  
  
6.  <span data-ttu-id="eda28-150">На странице **Правила членства в коллекции** выберите **Добавить правило**, после чего выберите **Прямое правило**, чтобы открыть **мастер создания статических правил членства в коллекции**.</span><span class="sxs-lookup"><span data-stu-id="eda28-150">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="eda28-151">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-151">Choose **Next**.</span></span>  
  
7.  <span data-ttu-id="eda28-152">На странице **Поиск ресурсов** в списке **Класс ресурсов** выберите **Системный ресурс**.</span><span class="sxs-lookup"><span data-stu-id="eda28-152">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="eda28-153">В списке **Имя атрибута** выберите пункт **Имя**.</span><span class="sxs-lookup"><span data-stu-id="eda28-153">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="eda28-154">В поле **Значение** введите `%`%**, а затем нажмите кнопку** Далее.</span><span class="sxs-lookup"><span data-stu-id="eda28-154">In the **Value** field, enter `%`, and then choose **Next**.</span></span>  
  
8.  <span data-ttu-id="eda28-155">На странице **Выделите ресурсы** установите флажок для каждого компьютера, на котором вы хотите развернуть .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eda28-155">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="eda28-156">Нажмите кнопку **Далее**, после чего завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="eda28-156">Choose **Next**, and then complete the wizard.</span></span>  
  
9. <span data-ttu-id="eda28-157">На странице **Правила членства в коллекции** **мастера создания коллекций устройств** нажмите кнопку **Далее**, после чего завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="eda28-157">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="eda28-158">Дополнительные сведения о коллекциях см. в статье [Коллекции в Configuration Manager](http://technet.microsoft.com/library/bb693730.aspx) в библиотеке документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-158">For more information about collections, see [Collections in Configuration Manager](http://technet.microsoft.com/library/bb693730.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="creating_a_package"></a>   
### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="eda28-159">Создание пакета и программы для распространяемого пакета .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eda28-159">Create a package and program for the .NET Framework redistributable package</span></span>  
 <span data-ttu-id="eda28-160">На следующих этапах вручную создается пакет для распространяемого пакета .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eda28-160">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="eda28-161">Пакет будет содержать заданные параметры для установки платформы .NET Framework и расположение, из которого этот пакет будет распространяться на целевые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="eda28-161">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>  
  
 <span data-ttu-id="eda28-162">Создание пакета</span><span class="sxs-lookup"><span data-stu-id="eda28-162">To create a package:</span></span>  
  
1.  <span data-ttu-id="eda28-163">В консоли Configuration Manager выберите **Библиотека программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="eda28-163">In the Configuration Manager console, choose **Software Library**..</span></span>  
  
2.  <span data-ttu-id="eda28-164">В рабочей области **Библиотека программного обеспечения** разверните узел **Управление приложениями**, а затем выберите **Пакеты**.</span><span class="sxs-lookup"><span data-stu-id="eda28-164">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="eda28-165">На вкладке **Главная** в группе **Создать** выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="eda28-165">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>  
  
4.  <span data-ttu-id="eda28-166">На странице **Пакет** **мастера создания пакетов и программ** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="eda28-166">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    -   <span data-ttu-id="eda28-167">Имя: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="eda28-167">Name: `.NET Framework 4.5`</span></span>  
  
    -   <span data-ttu-id="eda28-168">Производитель: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="eda28-168">Manufacturer: `Microsoft`</span></span>  
  
    -   <span data-ttu-id="eda28-169">Язык.</span><span class="sxs-lookup"><span data-stu-id="eda28-169">Language.</span></span> `English (US)`  
  
5.  <span data-ttu-id="eda28-170">Выберите **Этот пакет содержит исходные файлы**, после чего нажмите кнопку **Обзор**, чтобы выбрать локальную или сетевую папку, в которой содержатся файлы установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eda28-170">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="eda28-171">После выбора папки нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-171">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>  
  
6.  <span data-ttu-id="eda28-172">На странице **Тип программы** мастера выберите **Стандартная программа**, после чего нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-172">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="eda28-173">На странице **Программа** **мастера создания пакетов и программ** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="eda28-173">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="eda28-174">**Имя:**  `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="eda28-174">**Name:** `.NET Framework 4.5`</span></span>  
  
    2.  <span data-ttu-id="eda28-175">**Командная строка:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (параметры командной строки описаны в таблице ниже)</span><span class="sxs-lookup"><span data-stu-id="eda28-175">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>  
  
    3.  <span data-ttu-id="eda28-176">**Выполнить:** выберите **Скрытый**.</span><span class="sxs-lookup"><span data-stu-id="eda28-176">**Run:** Choose **Hidden**.</span></span>  
  
    4.  <span data-ttu-id="eda28-177">**Требования для запуска:** выберите параметр выполнения программы независимо от того, вошел ли пользователь в систему.</span><span class="sxs-lookup"><span data-stu-id="eda28-177">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>  
  
8.  <span data-ttu-id="eda28-178">На странице **Требования** нажмите кнопку **Далее**, чтобы принять значения по умолчанию, после чего завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="eda28-178">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="eda28-179">В следующей таблице описываются параметры командной строки, указанные на шаге 7.</span><span class="sxs-lookup"><span data-stu-id="eda28-179">The following table describes the command-line options specified in step 7.</span></span>  
  
|<span data-ttu-id="eda28-180">Параметр</span><span class="sxs-lookup"><span data-stu-id="eda28-180">Option</span></span>|<span data-ttu-id="eda28-181">Описание:</span><span class="sxs-lookup"><span data-stu-id="eda28-181">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="eda28-182">**/q**</span><span class="sxs-lookup"><span data-stu-id="eda28-182">**/q**</span></span>|<span data-ttu-id="eda28-183">Включает автоматический режим.</span><span class="sxs-lookup"><span data-stu-id="eda28-183">Sets quiet mode.</span></span> <span data-ttu-id="eda28-184">Ввод данных пользователем необязателен, вывод не отображается.</span><span class="sxs-lookup"><span data-stu-id="eda28-184">No user input is required, and no output is shown.</span></span>|  
|<span data-ttu-id="eda28-185">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="eda28-185">**/norestart**</span></span>|<span data-ttu-id="eda28-186">Запрещает программе установки автоматически перезагружать компьютер.</span><span class="sxs-lookup"><span data-stu-id="eda28-186">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="eda28-187">При использовании этого параметра Configuration Manager должен обрабатывать перезагрузку компьютера.</span><span class="sxs-lookup"><span data-stu-id="eda28-187">If you use this option, Configuration Manager must handle the computer restart.</span></span>|  
|<span data-ttu-id="eda28-188">**/chainingpackage** *PackageName*</span><span class="sxs-lookup"><span data-stu-id="eda28-188">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="eda28-189">Указывает имя пакета, осуществляющего привязку.</span><span class="sxs-lookup"><span data-stu-id="eda28-189">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="eda28-190">Эта информация передается вместе с другими данными сеанса установки для тех, кто подписался на [программу улучшения качества программного обеспечения корпорации Майкрософт (CEIP)](http://go.microsoft.com/fwlink/p/?LinkId=248244).</span><span class="sxs-lookup"><span data-stu-id="eda28-190">This information is reported with other installation session information for those who have signed up for the [Microsoft Customer Experience Improvement Program (CEIP)](http://go.microsoft.com/fwlink/p/?LinkId=248244).</span></span> <span data-ttu-id="eda28-191">Если в имени пакета присутствуют пробелы, в качестве разделителей необходимо использовать двойные кавычки (например, **/chainingpackage "Chaining Product"**).</span><span class="sxs-lookup"><span data-stu-id="eda28-191">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|  
  
 <span data-ttu-id="eda28-192">На этих этапах создается пакет с именем .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="eda28-192">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="eda28-193">Программа развертывает автоматическую установку .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="eda28-193">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="eda28-194">При автоматической установке пользователи не взаимодействуют с процедурой установки, и привязываемое приложение должно захватить код возврата и обработать перезагрузку; см. раздел с описанием [получения сведений о ходе выполнения из пакета установки](http://go.microsoft.com/fwlink/?LinkId=179606).</span><span class="sxs-lookup"><span data-stu-id="eda28-194">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](http://go.microsoft.com/fwlink/?LinkId=179606).</span></span>  
 
<a name="select_dist_point"></a>   
### <a name="select-a-distribution-point"></a><span data-ttu-id="eda28-195">Выбор точки распространения</span><span class="sxs-lookup"><span data-stu-id="eda28-195">Select a distribution point</span></span>  
 <span data-ttu-id="eda28-196">Для распространения пакета и программы на клиентских компьютерах необходимо сначала назначить систему сайта в качестве точки распространения, после чего передать на нее пакет и программу.</span><span class="sxs-lookup"><span data-stu-id="eda28-196">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>  
  
 <span data-ttu-id="eda28-197">Чтобы выбрать точку распространения для пакета .NET Framework 4.5, созданную в предыдущем разделе, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eda28-197">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>  
  
1.  <span data-ttu-id="eda28-198">В консоли Configuration Manager выберите **Библиотека программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="eda28-198">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="eda28-199">В рабочей области **Библиотека программного обеспечения** разверните узел **Управление приложениями**, а затем выберите **Пакеты**.</span><span class="sxs-lookup"><span data-stu-id="eda28-199">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="eda28-200">В списке пакетов выберите пакет **.NET Framework 4.5**, созданный в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="eda28-200">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>  
  
4.  <span data-ttu-id="eda28-201">На вкладке **Главная** в группе **Развертывание** выберите **Распространение содержимого**.</span><span class="sxs-lookup"><span data-stu-id="eda28-201">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>  
  
5.  <span data-ttu-id="eda28-202">На вкладке **Общие** **мастера распространения содержимого** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-202">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>  
  
6.  <span data-ttu-id="eda28-203">На странице **Места распространения содержимого** мастера нажмите кнопку **Добавить**, после чего выберите **Точка распространения**.</span><span class="sxs-lookup"><span data-stu-id="eda28-203">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>  
  
7.  <span data-ttu-id="eda28-204">В диалоговом окне **Добавление точек распространения** выберите точки распространения, которые будут содержать пакет и программу, после чего нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eda28-204">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>  
  
8.  <span data-ttu-id="eda28-205">Завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="eda28-205">Complete the wizard.</span></span>  
  
 <span data-ttu-id="eda28-206">Теперь пакет содержит все сведения, необходимые для автоматического развертывания платформы .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="eda28-206">The package now contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="eda28-207">Перед развертыванием пакета и программы убедитесь, что она была установлена в точке распространения; см. раздел "Мониторинг содержимого" в статье [Использование и отслеживание управления содержимым в Configuration Manager](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent) в библиотеке документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eda28-207">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Monitor Content" section of [Operations and Maintenance for Content Management in Configuration Manager](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="deploying_package"></a>   
### <a name="deploy-the-package"></a><span data-ttu-id="eda28-208">Развертывание пакета</span><span class="sxs-lookup"><span data-stu-id="eda28-208">Deploy the package</span></span>  
 <span data-ttu-id="eda28-209">Чтобы выполнить развертывание пакета и программы .NET Framework 4.5, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eda28-209">To deploy the .NET Framework 4.5 package and program:</span></span>  
  
1.  <span data-ttu-id="eda28-210">В консоли Configuration Manager выберите **Библиотека программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="eda28-210">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="eda28-211">В рабочей области **Библиотека программного обеспечения** разверните узел **Управление приложениями**, а затем выберите **Пакеты**.</span><span class="sxs-lookup"><span data-stu-id="eda28-211">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="eda28-212">В списке пакетов выберите созданный вами пакет **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="eda28-212">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>  
  
4.  <span data-ttu-id="eda28-213">На вкладке **Главная** в группе **Развертывание** выберите **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="eda28-213">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>  
  
5.  <span data-ttu-id="eda28-214">На странице **Общие** **мастера развертывания программного обеспечения** нажмите кнопку **Обзор**, после чего выберите ранее созданную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="eda28-214">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="eda28-215">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-215">Choose **Next**.</span></span>  
  
6.  <span data-ttu-id="eda28-216">На странице **Содержимое** мастера убедитесь, что отображается нужная точка распространения, после чего нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-216">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="eda28-217">На странице **Параметры развертывания** убедитесь, что в поле **Действие** выбрано **Установить**, а в поле **Цель** — **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="eda28-217">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="eda28-218">После этого установка программного пакета на целевых компьютерах будет обязательной.</span><span class="sxs-lookup"><span data-stu-id="eda28-218">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="eda28-219">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-219">Choose **Next**.</span></span>  
  
8.  <span data-ttu-id="eda28-220">На странице **Планирование** укажите, когда нужно установить .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eda28-220">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="eda28-221">Выберите **Создать**, чтобы задать время установки, или настройте выполнение установки при входе или выходе пользователя либо как можно скорее.</span><span class="sxs-lookup"><span data-stu-id="eda28-221">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="eda28-222">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-222">Choose **Next**.</span></span>  
  
9. <span data-ttu-id="eda28-223">На странице **Взаимодействие с пользователем** оставьте значения по умолчанию и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-223">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="eda28-224">В вашей рабочей среде могут использоваться политики, требующие выбора других параметров для расписания развертывания.</span><span class="sxs-lookup"><span data-stu-id="eda28-224">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="eda28-225">Сведения об этих параметрах см. в статье [Свойства имени объявления: вкладка "Расписание"](http://technet.microsoft.com/library/bb694016.aspx) в библиотеке TechNet.</span><span class="sxs-lookup"><span data-stu-id="eda28-225">For information about these options, see [Advertisement Name Properties: Schedule Tab](http://technet.microsoft.com/library/bb694016.aspx) in the TechNet Library.</span></span>  
  
10. <span data-ttu-id="eda28-226">На странице **Точки распространения** оставьте значения по умолчанию и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eda28-226">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>  
  
11. <span data-ttu-id="eda28-227">Завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="eda28-227">Complete the wizard.</span></span> <span data-ttu-id="eda28-228">Ход развертывания можно отслеживать в узле **Развертывания** рабочей области **Отслеживание**.</span><span class="sxs-lookup"><span data-stu-id="eda28-228">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>  
  
 <span data-ttu-id="eda28-229">Произойдет развертывание пакета в целевой коллекции и начнется автоматическая установка платформы .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="eda28-229">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="eda28-230">Дополнительные сведения о кодах ошибок установки .NET Framework 4.5 см. подразделе [Коды возврата](#return_codes) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eda28-230">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>  
  
<a name="resources"></a>   
## <a name="resources"></a><span data-ttu-id="eda28-231">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="eda28-231">Resources</span></span>  
 <span data-ttu-id="eda28-232">Для получения дополнительных сведений об инфраструктуре для тестирования развертывания распространяемого пакета [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] обратитесь к следующим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="eda28-232">For more information about the infrastructure for testing the deployment of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable package, see the following resources.</span></span>  
  
 <span data-ttu-id="eda28-233">**Active Directory, DNS, DHCP**</span><span class="sxs-lookup"><span data-stu-id="eda28-233">**Active Directory, DNS, DHCP:**</span></span>  
  
-   [<span data-ttu-id="eda28-234">Доменные службы Active Directory для Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="eda28-234">Active Directory Domain Services for Windows Server 2008</span></span>](http://technet.microsoft.com/library/dd378891.aspx)  
  
-   [<span data-ttu-id="eda28-235">DNS-сервер</span><span class="sxs-lookup"><span data-stu-id="eda28-235">DNS Server</span></span>](http://technet.microsoft.com/library/cc732997.aspx)  
  
-   [<span data-ttu-id="eda28-236">DHCP-сервер</span><span class="sxs-lookup"><span data-stu-id="eda28-236">DHCP Server</span></span>](http://technet.microsoft.com/library/cc896553.aspx)  
  
 <span data-ttu-id="eda28-237">**SQL Server 2008**</span><span class="sxs-lookup"><span data-stu-id="eda28-237">**SQL Server 2008:**</span></span>  
  
-   [<span data-ttu-id="eda28-238">Установка SQL Server 2008 (видеоматериал по SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eda28-238">Installing SQL Server 2008 (SQL Server Video)</span></span>](http://technet.microsoft.com/library/dd299415.aspx)  
  
-   [<span data-ttu-id="eda28-239">Обзор безопасности SQL Server 2008 для администраторов баз данных</span><span class="sxs-lookup"><span data-stu-id="eda28-239">SQL Server 2008 Security Overview for Database Administrators</span></span>](http://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)  
  
 <span data-ttu-id="eda28-240">**System Center 2012 Configuration Manager (точка управления, точка распространения)**</span><span class="sxs-lookup"><span data-stu-id="eda28-240">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>  
  
-   [<span data-ttu-id="eda28-241">Администрирование сайтов для System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eda28-241">Site Administration for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg681983.aspx)  
  
-   [<span data-ttu-id="eda28-242">Планирование и развертывание одного сайта Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eda28-242">Configuration Manager Single Site Planning and Deployment</span></span>](http://technet.microsoft.com/library/bb680961.aspx)  
  
 <span data-ttu-id="eda28-243">**Клиент System Center 2012 Configuration Manager для компьютеров под управлением Windows**</span><span class="sxs-lookup"><span data-stu-id="eda28-243">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>  
  
-   [<span data-ttu-id="eda28-244">Развертывание клиентов для System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eda28-244">Deploying Clients for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg699391.aspx)  
  
<a name="troubleshooting"></a>   
## <a name="troubleshooting"></a><span data-ttu-id="eda28-245">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="eda28-245">Troubleshooting</span></span>  
  
### <a name="log-file-locations"></a><span data-ttu-id="eda28-246">Расположение файлов журнала</span><span class="sxs-lookup"><span data-stu-id="eda28-246">Log file locations</span></span>  
 <span data-ttu-id="eda28-247">Во время установки .NET Framework создаются следующие файлы журнала:</span><span class="sxs-lookup"><span data-stu-id="eda28-247">The following log files are generated during .NET Framework setup:</span></span>  
  
 <span data-ttu-id="eda28-248">%temp%\Microsoft .NET Framework *версия*\*.txt</span><span class="sxs-lookup"><span data-stu-id="eda28-248">%temp%\Microsoft .NET Framework *version*\*.txt</span></span>  
 <span data-ttu-id="eda28-249">%temp%\Microsoft .NET Framework *версия*\*.html</span><span class="sxs-lookup"><span data-stu-id="eda28-249">%temp%\Microsoft .NET Framework *version*\*.html</span></span>  
  
 <span data-ttu-id="eda28-250">Здесь *версия* — это устанавливаемая версия платформы .NET Framework, например 4.5 или 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="eda28-250">where *version* is the version of the .NET Framework that you're installing, such as 4.5 or 4.7.2.</span></span>  
 
 <span data-ttu-id="eda28-251">Вы также можете указать каталог, в который записываются файлы журнала, с помощью параметра командной строки `/log` в команде установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eda28-251">You can also specify the directory to which log files are written by using the `/log` command-line option in the .NET Framework installation command.</span></span> <span data-ttu-id="eda28-252">Дополнительные сведения см. в статье [Руководство по развертыванию .NET Framework для разработчиков](deployment-guide-for-developers.md#command-line-options).</span><span class="sxs-lookup"><span data-stu-id="eda28-252">For more information, see [.NET Framework deployment guide for developers](deployment-guide-for-developers.md#command-line-options).</span></span> 
 
 <span data-ttu-id="eda28-253">Для сбора файлов журнала .NET Framework и создания CAB-файла, уменьшающего размер файлов, можно использовать [средство сбора журналов](https://www.microsoft.com/download/details.aspx?id=12493).</span><span class="sxs-lookup"><span data-stu-id="eda28-253">You can use the [log collection tool](https://www.microsoft.com/download/details.aspx?id=12493) to collect the .NET Framework log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>  
  
<a name="return_codes"></a>   
### <a name="return-codes"></a><span data-ttu-id="eda28-254">Коды возврата</span><span class="sxs-lookup"><span data-stu-id="eda28-254">Return codes</span></span>  
 <span data-ttu-id="eda28-255">В следующей таблице перечислены наиболее распространенные коды возврата программы установки распространяемого пакета [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda28-255">The following table lists the most common return codes from the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable installation program.</span></span> <span data-ttu-id="eda28-256">Коды возврата одинаковы для всех версий установщика.</span><span class="sxs-lookup"><span data-stu-id="eda28-256">The return codes are the same for all versions of the installer.</span></span>  
  
 <span data-ttu-id="eda28-257">Подробные сведения см. в разделе [Коды ошибок загрузки](#additional_error_codes).</span><span class="sxs-lookup"><span data-stu-id="eda28-257">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>  
  
|<span data-ttu-id="eda28-258">Код возврата</span><span class="sxs-lookup"><span data-stu-id="eda28-258">Return code</span></span>|<span data-ttu-id="eda28-259">Описание:</span><span class="sxs-lookup"><span data-stu-id="eda28-259">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="eda28-260">0</span><span class="sxs-lookup"><span data-stu-id="eda28-260">0</span></span>|<span data-ttu-id="eda28-261">Установка успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="eda28-261">Installation completed successfully.</span></span>|  
|<span data-ttu-id="eda28-262">1602</span><span class="sxs-lookup"><span data-stu-id="eda28-262">1602</span></span>|<span data-ttu-id="eda28-263">Установка отменена пользователем.</span><span class="sxs-lookup"><span data-stu-id="eda28-263">The user canceled installation.</span></span>|  
|<span data-ttu-id="eda28-264">1603</span><span class="sxs-lookup"><span data-stu-id="eda28-264">1603</span></span>|<span data-ttu-id="eda28-265">Во время установки произошла неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="eda28-265">A fatal error occurred during installation.</span></span>|  
|<span data-ttu-id="eda28-266">1641</span><span class="sxs-lookup"><span data-stu-id="eda28-266">1641</span></span>|<span data-ttu-id="eda28-267">Для завершения установки необходима перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="eda28-267">A restart is required to complete the installation.</span></span> <span data-ttu-id="eda28-268">Сообщение указывает на успешное завершение действия.</span><span class="sxs-lookup"><span data-stu-id="eda28-268">This message indicates success.</span></span>|  
|<span data-ttu-id="eda28-269">3010</span><span class="sxs-lookup"><span data-stu-id="eda28-269">3010</span></span>|<span data-ttu-id="eda28-270">Для завершения установки необходима перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="eda28-270">A restart is required to complete the installation.</span></span> <span data-ttu-id="eda28-271">Сообщение указывает на успешное завершение действия.</span><span class="sxs-lookup"><span data-stu-id="eda28-271">This message indicates success.</span></span>|  
|<span data-ttu-id="eda28-272">5100</span><span class="sxs-lookup"><span data-stu-id="eda28-272">5100</span></span>|<span data-ttu-id="eda28-273">Компьютер пользователя не отвечает системным требованиям.</span><span class="sxs-lookup"><span data-stu-id="eda28-273">The user's computer does not meet system requirements.</span></span>|  
  
<a name="additional_error_codes"></a>   
### <a name="download-error-codes"></a><span data-ttu-id="eda28-274">Коды ошибок загрузки</span><span class="sxs-lookup"><span data-stu-id="eda28-274">Download error codes</span></span>  
  
-   [<span data-ttu-id="eda28-275">Коды ошибок Background Intelligent Transfer Service (BITS)</span><span class="sxs-lookup"><span data-stu-id="eda28-275">Background Intelligent Transfer Service (BITS) error codes</span></span>](http://msdn.microsoft.com/library/aa362823.aspx)  
  
-   [<span data-ttu-id="eda28-276">Коды ошибок моникера URL</span><span class="sxs-lookup"><span data-stu-id="eda28-276">URL moniker error codes</span></span>](http://msdn.microsoft.com/library/ms775145.aspx)  
  
-   [<span data-ttu-id="eda28-277">Коды ошибок WinHttp</span><span class="sxs-lookup"><span data-stu-id="eda28-277">WinHttp error codes</span></span>](http://msdn.microsoft.com/library/aa383770.aspx)  
  
 <span data-ttu-id="eda28-278">Другие коды ошибок</span><span class="sxs-lookup"><span data-stu-id="eda28-278">Other error codes:</span></span>  
  
-   [<span data-ttu-id="eda28-279">Коды ошибок установщика Windows</span><span class="sxs-lookup"><span data-stu-id="eda28-279">Windows Installer error codes</span></span>](http://msdn.microsoft.com/library/aa368542.aspx)  
  
-   [<span data-ttu-id="eda28-280">Коды результатов агента обновления Windows</span><span class="sxs-lookup"><span data-stu-id="eda28-280">Windows Update Agent result codes</span></span>](http://technet.microsoft.com/library/cc720442.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="eda28-281">См. также</span><span class="sxs-lookup"><span data-stu-id="eda28-281">See Also</span></span>  
 [<span data-ttu-id="eda28-282">Руководство по развертыванию для разработчиков</span><span class="sxs-lookup"><span data-stu-id="eda28-282">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [<span data-ttu-id="eda28-283">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="eda28-283">System Requirements</span></span>](../../../docs/framework/get-started/system-requirements.md)
