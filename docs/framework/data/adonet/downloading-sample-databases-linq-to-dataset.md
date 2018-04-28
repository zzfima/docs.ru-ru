---
title: Загрузка примеров баз данных (LINQ to DataSet)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8e19e51ecf4868d0d49e26b4aafd7e8b3840992d
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="ae7b4-102">Загрузка примеров баз данных (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ae7b4-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="ae7b4-103">Примеры и пошаговые руководства в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] документации используется образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-103">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="ae7b4-104">Этот продукт можно бесплатно загрузить с веб-сайта загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="ae7b4-105">Образцы и пошаговые руководства в документации по [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] используют в качестве хранилища данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-105">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use SQL Server as the data store.</span></span> <span data-ttu-id="ae7b4-106">Вместо SQL Server можно использовать SQL Server Express Edition, который доступен для бесплатной загрузки.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="ae7b4-107">Загрузка и установка базы данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="ae7b4-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="ae7b4-108">Загрузка и установка образца базы данных AdventureWorks для SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae7b4-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1.  <span data-ttu-id="ae7b4-109">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-109">Open Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="ae7b4-110">Последовательно выберите пункты [образцы SQL Server 2005 и образцов баз данных](http://go.microsoft.com/fwlink/?linkid=31046) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-110">Go to the [SQL Server 2005 Samples and Sample Databases](http://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3.  <span data-ttu-id="ae7b4-111">Следуйте инструкциям на веб-узле по загрузке образца базы данных AdventureWorks для соответствующего процессора (например, AdventureWorksDB.msi) и сохраните файл с расширением MSI на компьютер.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4.  <span data-ttu-id="ae7b4-112">Если установлена предыдущая версия AdventureWorks, ее необходимо удалить перед запуском AdventureWorks.msi.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="ae7b4-113">Удаление предыдущей версии образца базы данных AdventureWorks </span><span class="sxs-lookup"><span data-stu-id="ae7b4-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1.  <span data-ttu-id="ae7b4-114">Удалите базу данных AdventureWorks или AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="ae7b4-115">Из **Установка и удаление программ**выберите **AdventureWorksDB** или **AdventureWorksBI** и нажмите кнопку **удалить**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="ae7b4-116">Удаление предыдущей версии образца базы данных AdventureWorks, установленной с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="ae7b4-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1.  <span data-ttu-id="ae7b4-117">Удалите базу данных AdventureWorks или AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="ae7b4-118">Из **Установка и удаление программ**выберите **Microsoft SQL Server 2005** и нажмите кнопку **изменений**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3.  <span data-ttu-id="ae7b4-119">Из **Выбор компонентов**выберите **компоненты рабочей станции** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ae7b4-120">Из **вас приветствует мастер установки SQL Server**, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="ae7b4-121">Из **Проверка конфигурации системы**, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6.  <span data-ttu-id="ae7b4-122">Из **изменить или удалить экземпляр**, нажмите кнопку **изменить установленные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7.  <span data-ttu-id="ae7b4-123">Из **Выбор компонентов**, разверните **документация, примеры и образцы баз данных** узла.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8.  <span data-ttu-id="ae7b4-124">Выберите **образцы кода и приложений**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="ae7b4-125">Разверните **образцы баз данных**, выберите образец базы данных, который необходимо удалить и выберите **компонент станет недоступным**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="ae7b4-126">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="ae7b4-127">Нажмите кнопку **установить** и завершите работу мастера установки.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="ae7b4-128">Присоединение файлов образца базы данных AdventureWorks к SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae7b4-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="ae7b4-129">После загрузки файла установщика образца базы данных, дважды щелкните **AdventureWorksDB.msi** файла (или загруженный файл) для установки базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="ae7b4-130">По умолчанию база данных устанавливается в папку c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="ae7b4-131">Подключите файлы базы данных AdventureWorks к экземпляру SQL Server, выполнив следующий скрипт в командной строке SQLCMD или в среде SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="ae7b4-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="ae7b4-132">Если файлы были установлены на другой диск или в другой каталог, нужно исправить соответствующие пути перед выполнением хранимой процедуры `sp_attach_db`.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="ae7b4-133">Загрузка SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="ae7b4-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="ae7b4-134">Примеры и пошаговые руководства в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] раздела, используемая в качестве хранилища данных SQL Server 2005, но можно изменить, чтобы вместо этого используйте SQL Server Express Edition,.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-134">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="ae7b4-135">SQL Server Express Edition доступен бесплатно и его можно распространять вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="ae7b4-136">При использовании Visual Studio, SQL Server Express Edition включается в выпусках Pro и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="ae7b4-137">Загрузка и установка выпуска SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="ae7b4-137">To download and install SQL Server Express Edition</span></span>  
  
1.  <span data-ttu-id="ae7b4-138">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-138">Start Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="ae7b4-139">Последовательно выберите пункты [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) странице загрузки.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-139">Go to the  [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3.  <span data-ttu-id="ae7b4-140">Следуйте указаниям по установке, содержащимся на веб-узле.</span><span class="sxs-lookup"><span data-stu-id="ae7b4-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7b4-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ae7b4-141">See Also</span></span>  
 [<span data-ttu-id="ae7b4-142">Начало работы</span><span class="sxs-lookup"><span data-stu-id="ae7b4-142">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
