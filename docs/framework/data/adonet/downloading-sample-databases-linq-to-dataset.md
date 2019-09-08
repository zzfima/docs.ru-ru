---
title: Загрузка примеров баз данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: c67ee699cf594f476a728c7345b47b0c32dea7ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795177"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="51825-102">Загрузка примеров баз данных (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="51825-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="51825-103">Примеры и пошаговые руководства в документации по LINQ to DataSet используют образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="51825-103">The samples and walkthroughs in the LINQ to DataSet documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="51825-104">Этот продукт можно бесплатно загрузить с веб-узла корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51825-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="51825-105">Примеры и пошаговые руководства в документации по LINQ to DataSet используют SQL Server в качестве хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="51825-105">The samples and walkthroughs in the LINQ to DataSet documentation use SQL Server as the data store.</span></span> <span data-ttu-id="51825-106">Вместо SQL Server можно использовать SQL Server Express Edition, который доступен для бесплатной загрузки.</span><span class="sxs-lookup"><span data-stu-id="51825-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="51825-107">Загрузка и установка базы данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="51825-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="51825-108">Загрузка и установка образца базы данных AdventureWorks для SQL Server</span><span class="sxs-lookup"><span data-stu-id="51825-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1. <span data-ttu-id="51825-109">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="51825-109">Open Internet Explorer.</span></span>  
  
2. <span data-ttu-id="51825-110">Перейдите на веб-сайт [примеров SQL Server 2005 и образцов баз данных](https://go.microsoft.com/fwlink/?linkid=31046) .</span><span class="sxs-lookup"><span data-stu-id="51825-110">Go to the [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3. <span data-ttu-id="51825-111">Следуйте инструкциям на веб-узле по загрузке образца базы данных AdventureWorks для соответствующего процессора (например, AdventureWorksDB.msi) и сохраните файл с расширением MSI на компьютер.</span><span class="sxs-lookup"><span data-stu-id="51825-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4. <span data-ttu-id="51825-112">Если установлена предыдущая версия AdventureWorks, ее необходимо удалить перед запуском AdventureWorks.msi.</span><span class="sxs-lookup"><span data-stu-id="51825-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="51825-113">Удаление предыдущей версии образца базы данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="51825-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1. <span data-ttu-id="51825-114">Удалите базу данных AdventureWorks или AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="51825-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="51825-115">В меню **Установка и удаление программ**выберите **AdventureWorksDB** или **адвентуреворксби** и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="51825-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="51825-116">Удаление предыдущей версии образца базы данных AdventureWorks, установленной с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="51825-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1. <span data-ttu-id="51825-117">Удалите базу данных AdventureWorks или AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="51825-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="51825-118">В меню **Установка и удаление программ**выберите **Microsoft SQL Server 2005** и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="51825-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3. <span data-ttu-id="51825-119">В списке **компонент**выберите **компоненты рабочей станции** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51825-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4. <span data-ttu-id="51825-120">В **мастере установки SQL Server**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51825-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5. <span data-ttu-id="51825-121">На основе **проверки конфигурации системы**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51825-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6. <span data-ttu-id="51825-122">В меню **изменить или удалить экземпляр**щелкните **изменить установленные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="51825-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7. <span data-ttu-id="51825-123">В **области Выбор компонентов**разверните узел **Документация, примеры и примеры баз данных** .</span><span class="sxs-lookup"><span data-stu-id="51825-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8. <span data-ttu-id="51825-124">Выберите **пример кода и приложений**.</span><span class="sxs-lookup"><span data-stu-id="51825-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="51825-125">Разверните **образец базы данных**, выберите удаляемый образец базы данных и выберите **весь компонент будет недоступен**.</span><span class="sxs-lookup"><span data-stu-id="51825-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="51825-126">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51825-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="51825-127">Нажмите кнопку **установить** и завершите работу мастера установки.</span><span class="sxs-lookup"><span data-stu-id="51825-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="51825-128">Присоединение файлов образца базы данных AdventureWorks к SQL Server</span><span class="sxs-lookup"><span data-stu-id="51825-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1. <span data-ttu-id="51825-129">После скачивания файла образца базы данных программы установки дважды щелкните файл **AdventureWorksDB. msi** (или скачанный файл), чтобы установить базу данных.</span><span class="sxs-lookup"><span data-stu-id="51825-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="51825-130">По умолчанию база данных устанавливается в папку c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="51825-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2. <span data-ttu-id="51825-131">Подключите файлы базы данных AdventureWorks к экземпляру SQL Server, выполнив следующий скрипт в командной строке SQLCMD или в среде SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="51825-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="51825-132">Если файлы были установлены на другой диск или в другой каталог, нужно исправить соответствующие пути перед выполнением хранимой процедуры `sp_attach_db`.</span><span class="sxs-lookup"><span data-stu-id="51825-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="51825-133">Загрузка SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="51825-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="51825-134">Примеры и пошаговые руководства в разделе LINQ to DataSet используют SQL Server 2005 в качестве хранилища данных, но могут быть изменены для использования SQL Server Express Edition.</span><span class="sxs-lookup"><span data-stu-id="51825-134">The samples and walkthroughs in the LINQ to DataSet section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="51825-135">SQL Server Express Edition доступен бесплатно и его можно распространять вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="51825-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="51825-136">Если вы используете Visual Studio, SQL Server Express Edition входит в выпуски Pro и выше.</span><span class="sxs-lookup"><span data-stu-id="51825-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="51825-137">Загрузка и установка выпуска SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="51825-137">To download and install SQL Server Express Edition</span></span>  
  
1. <span data-ttu-id="51825-138">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="51825-138">Start Internet Explorer.</span></span>  
  
2. <span data-ttu-id="51825-139">Перейдите на страницу загрузки [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) .</span><span class="sxs-lookup"><span data-stu-id="51825-139">Go to the  [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3. <span data-ttu-id="51825-140">Следуйте указаниям по установке, содержащимся на веб-узле.</span><span class="sxs-lookup"><span data-stu-id="51825-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51825-141">См. также</span><span class="sxs-lookup"><span data-stu-id="51825-141">See also</span></span>

- [<span data-ttu-id="51825-142">Начало работы</span><span class="sxs-lookup"><span data-stu-id="51825-142">Getting Started</span></span>](getting-started-linq-to-dataset.md)
