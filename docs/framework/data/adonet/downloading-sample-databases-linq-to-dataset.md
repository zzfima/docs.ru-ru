---
title: Загрузка примеров баз данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: 340ccd1e0e2d415fe60721775bd39acf9db00f85
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504501"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="df4f8-102">Загрузка примеров баз данных (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="df4f8-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="df4f8-103">Примеры и пошаговые руководства в LINQ to DataSet документации используется образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="df4f8-103">The samples and walkthroughs in the LINQ to DataSet documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="df4f8-104">Этот продукт можно бесплатно загрузить с веб-узла корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="df4f8-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="df4f8-105">Примеры и пошаговые руководства в LINQ to DataSet документации использовать в качестве хранилища данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df4f8-105">The samples and walkthroughs in the LINQ to DataSet documentation use SQL Server as the data store.</span></span> <span data-ttu-id="df4f8-106">Вместо SQL Server можно использовать SQL Server Express Edition, который доступен для бесплатной загрузки.</span><span class="sxs-lookup"><span data-stu-id="df4f8-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="df4f8-107">Загрузка и установка базы данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="df4f8-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="df4f8-108">Загрузка и установка образца базы данных AdventureWorks для SQL Server</span><span class="sxs-lookup"><span data-stu-id="df4f8-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1. <span data-ttu-id="df4f8-109">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="df4f8-109">Open Internet Explorer.</span></span>  
  
2. <span data-ttu-id="df4f8-110">Перейдите к [образцы SQL Server 2005 и образцов баз данных](https://go.microsoft.com/fwlink/?linkid=31046) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="df4f8-110">Go to the [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3. <span data-ttu-id="df4f8-111">Следуйте инструкциям на веб-узле по загрузке образца базы данных AdventureWorks для соответствующего процессора (например, AdventureWorksDB.msi) и сохраните файл с расширением MSI на компьютер.</span><span class="sxs-lookup"><span data-stu-id="df4f8-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4. <span data-ttu-id="df4f8-112">Если установлена предыдущая версия AdventureWorks, ее необходимо удалить перед запуском AdventureWorks.msi.</span><span class="sxs-lookup"><span data-stu-id="df4f8-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="df4f8-113">Удаление предыдущей версии образца базы данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="df4f8-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1. <span data-ttu-id="df4f8-114">Удалите базу данных AdventureWorks или AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="df4f8-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="df4f8-115">Из **Установка и удаление программ**выберите **AdventureWorksDB** или **AdventureWorksBI** и нажмите кнопку **удалить**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="df4f8-116">Удаление предыдущей версии образца базы данных AdventureWorks, установленной с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="df4f8-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1. <span data-ttu-id="df4f8-117">Удалите базу данных AdventureWorks или AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="df4f8-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="df4f8-118">Из **Установка и удаление программ**выберите **Microsoft SQL Server 2005** и нажмите кнопку **изменение**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3. <span data-ttu-id="df4f8-119">Из **выбора компонентов**выберите **компоненты рабочей станции** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4. <span data-ttu-id="df4f8-120">Из **Добро пожаловать в мастер установки SQL Server**, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5. <span data-ttu-id="df4f8-121">Из **Проверка конфигурации системы**, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6. <span data-ttu-id="df4f8-122">Из **изменить или удалить экземпляр**, нажмите кнопку **изменить установленные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7. <span data-ttu-id="df4f8-123">Из **Выбор компонентов**, разверните **документация, примеры и образцы баз данных** узла.</span><span class="sxs-lookup"><span data-stu-id="df4f8-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8. <span data-ttu-id="df4f8-124">Выберите **образцы кода и приложений**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="df4f8-125">Разверните **образцов баз данных**, выберите образец базы данных, который необходимо удалить и выберите **компонент станет недоступным**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="df4f8-126">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="df4f8-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="df4f8-127">Нажмите кнопку **установить** и завершение работы мастера установки.</span><span class="sxs-lookup"><span data-stu-id="df4f8-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="df4f8-128">Присоединение файлов образца базы данных AdventureWorks к SQL Server</span><span class="sxs-lookup"><span data-stu-id="df4f8-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1. <span data-ttu-id="df4f8-129">После загрузки файл установщика для образца базы данных, дважды щелкните файл **AdventureWorksDB.msi** файл (или загруженный файл) для установки базы данных.</span><span class="sxs-lookup"><span data-stu-id="df4f8-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="df4f8-130">По умолчанию база данных устанавливается в папку c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="df4f8-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2. <span data-ttu-id="df4f8-131">Подключите файлы базы данных AdventureWorks к экземпляру SQL Server, выполнив следующий скрипт в командной строке SQLCMD или в среде SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="df4f8-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="df4f8-132">Если файлы были установлены на другой диск или в другой каталог, нужно исправить соответствующие пути перед выполнением хранимой процедуры `sp_attach_db`.</span><span class="sxs-lookup"><span data-stu-id="df4f8-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="df4f8-133">Загрузка SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="df4f8-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="df4f8-134">Примеры и пошаговые руководства в LINQ to DataSet разделе использовать как хранилище данных SQL Server 2005, но можно изменить, чтобы вместо этого используйте SQL Server Express Edition.</span><span class="sxs-lookup"><span data-stu-id="df4f8-134">The samples and walkthroughs in the LINQ to DataSet section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="df4f8-135">SQL Server Express Edition доступен бесплатно и его можно распространять вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="df4f8-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="df4f8-136">Если вы используете Visual Studio, SQL Server Express Edition включается в выпуски Pro и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="df4f8-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="df4f8-137">Загрузка и установка выпуска SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="df4f8-137">To download and install SQL Server Express Edition</span></span>  
  
1. <span data-ttu-id="df4f8-138">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="df4f8-138">Start Internet Explorer.</span></span>  
  
2. <span data-ttu-id="df4f8-139">Перейдите к [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) странице загрузки.</span><span class="sxs-lookup"><span data-stu-id="df4f8-139">Go to the  [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3. <span data-ttu-id="df4f8-140">Следуйте указаниям по установке, содержащимся на веб-узле.</span><span class="sxs-lookup"><span data-stu-id="df4f8-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4f8-141">См. также</span><span class="sxs-lookup"><span data-stu-id="df4f8-141">See also</span></span>

- [<span data-ttu-id="df4f8-142">Начало работы</span><span class="sxs-lookup"><span data-stu-id="df4f8-142">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
