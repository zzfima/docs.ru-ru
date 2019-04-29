---
title: Отслеживание SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: f3c48b40e2d3d7dec2b9008b3de738f9b2983610
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785922"
---
# <a name="sql-tracking"></a><span data-ttu-id="9062d-102">Отслеживание SQL</span><span class="sxs-lookup"><span data-stu-id="9062d-102">SQL Tracking</span></span>
<span data-ttu-id="9062d-103">Этот образец показывает, как создать настраиваемый участник отслеживания SQL, который вносит записи отслеживания в базу данных SQL.</span><span class="sxs-lookup"><span data-stu-id="9062d-103">This sample demonstrates how to write a custom SQL tracking participant, that writes tracking records to a SQL database.</span></span> <span data-ttu-id="9062d-104">Windows Workflow Foundation (WF) предоставляет отслеживание для обеспечения видимости выполнения экземпляра рабочего процесса рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9062d-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="9062d-105">Среда выполнения отслеживания выдает записи отслеживания рабочего процесса в ходе его выполнения.</span><span class="sxs-lookup"><span data-stu-id="9062d-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="9062d-106">Дополнительные сведения об отслеживании рабочего процесса см. в разделе [отслеживание и трассировка рабочих процессов](../workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="9062d-106">For more information about workflow tracking, see [Workflow Tracking and Tracing](../workflow-tracking-and-tracing.md).</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="9062d-107">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="9062d-107">To use this sample</span></span>

1. <span data-ttu-id="9062d-108">Убедитесь, что на компьютере установлен SQL Server 2008, SQL Server 2008 Express или более новая версия.</span><span class="sxs-lookup"><span data-stu-id="9062d-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="9062d-109">Скрипты, упакованные в состав образца, предполагают использование экземпляра SQL Express на локальном компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="9062d-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="9062d-110">Если вы работаете с другим экземпляром, до запуска образца следует внести изменения в скрипты, относящиеся к базе данных.</span><span class="sxs-lookup"><span data-stu-id="9062d-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>

2. <span data-ttu-id="9062d-111">Создание базы данных отслеживания на SQL Server посредством запуска команды Trackingsetup.cmd в каталоге скриптов (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span><span class="sxs-lookup"><span data-stu-id="9062d-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="9062d-112">Создает базу данных с именем TrackingSample.</span><span class="sxs-lookup"><span data-stu-id="9062d-112">This creates a database called TrackingSample.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9062d-113">Этот скрипт создает базу данных на экземпляре SQL Express по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9062d-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="9062d-114">Если установку необходимо произвести на другом экземпляре базы данных, внесите изменения в скрипт Trackingsetup.cmd.</span><span class="sxs-lookup"><span data-stu-id="9062d-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>  
  
3. <span data-ttu-id="9062d-115">Откройте SqlTrackingSample.sln в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="9062d-115">Open SqlTrackingSample.sln in Visual Studio 2010.</span></span>  
  
4. <span data-ttu-id="9062d-116">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="9062d-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5. <span data-ttu-id="9062d-117">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="9062d-117">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="9062d-118">Откроется окно браузера со списком каталогов для приложения.</span><span class="sxs-lookup"><span data-stu-id="9062d-118">The browser window opens and shows the directory listing for the application.</span></span>  
  
6. <span data-ttu-id="9062d-119">Щелкните файл StockPriceService.xamlx в браузере.</span><span class="sxs-lookup"><span data-stu-id="9062d-119">In the browser, click StockPriceService.xamlx.</span></span>  
  
7. <span data-ttu-id="9062d-120">В браузере отображается страница StockPriceService, содержащая адрес WSDL локальной службы.</span><span class="sxs-lookup"><span data-stu-id="9062d-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="9062d-121">Скопируйте этот адрес.</span><span class="sxs-lookup"><span data-stu-id="9062d-121">Copy this address.</span></span>  
  
     <span data-ttu-id="9062d-122">Примером адреса WSDL локальной службы является `http://localhost:65193/StockPriceService.xamlx?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="9062d-122">An example of the local service WSDL address is `http://localhost:65193/StockPriceService.xamlx?wsdl`.</span></span>  
  
8. <span data-ttu-id="9062d-123">С помощью [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] запустите клиент тестирования WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="9062d-123">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="9062d-124">Этот файл размещается в каталоге Microsoft Visual Studio 10.0\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="9062d-124">It is located in the Microsoft Visual Studio 10.0\Common7\IDE directory.</span></span>  
  
9. <span data-ttu-id="9062d-125">В тестовом клиенте WCF выберите **файл** меню и выберите **добавить службу**.</span><span class="sxs-lookup"><span data-stu-id="9062d-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="9062d-126">Вставьте в текстовое поле адрес локальной службы.</span><span class="sxs-lookup"><span data-stu-id="9062d-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="9062d-127">Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9062d-127">Click **OK** to close the dialog.</span></span>  
  
10. <span data-ttu-id="9062d-128">В тестовом клиенте WCF дважды щелкните **GetStockPrice**.</span><span class="sxs-lookup"><span data-stu-id="9062d-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="9062d-129">Откроется `GetStockPrice` операцию, которая принимает один параметр типа в значение `Contoso` и нажмите кнопку **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="9062d-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>  
  
11. <span data-ttu-id="9062d-130">Выданные записи отслеживания будут записаны в базу данных SQL.</span><span class="sxs-lookup"><span data-stu-id="9062d-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="9062d-131">Чтобы просмотреть записи отслеживания, откройте базу данных TrackingSample в среде SQL Management Studio и перейдите в раздел просмотра таблиц.</span><span class="sxs-lookup"><span data-stu-id="9062d-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> <span data-ttu-id="9062d-132">Дополнительные сведения о SQL Server Management Studio, см. в разделе [Знакомство с SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645).</span><span class="sxs-lookup"><span data-stu-id="9062d-132">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645).</span></span> <span data-ttu-id="9062d-133">SQL Server 2008 Management Studio Express можно загрузить [здесь](https://go.microsoft.com/fwlink/?LinkId=180520).</span><span class="sxs-lookup"><span data-stu-id="9062d-133">SQL Server 2008 Management Studio Express can be downloaded [here](https://go.microsoft.com/fwlink/?LinkId=180520).</span></span> <span data-ttu-id="9062d-134">Применение запроса select для таблиц выводит соответствующие данные записей отслеживания, хранимых в соответствующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="9062d-134">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="9062d-135">Удаление образца</span><span class="sxs-lookup"><span data-stu-id="9062d-135">To uninstall the sample</span></span>  
  
1. <span data-ttu-id="9062d-136">Запустите скрипт Trackingcleanup.cmd, расположенный в каталоге образцов (\WF\Basic\Tracking\SqlTracking).</span><span class="sxs-lookup"><span data-stu-id="9062d-136">Run theTrackingcleanup.cmd script in the sample directory (\WF\Basic\Tracking\SqlTracking).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9062d-137">Скрипт Trackingcleanup.cmd пытается удалить базу данных, хранящуюся в SQL Express вашего локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="9062d-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="9062d-138">При использовании другого экземпляра сервера SQL следует внести изменения в скрипт Trackingcleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="9062d-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="9062d-139">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9062d-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9062d-140">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9062d-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9062d-141">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="9062d-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9062d-142">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9062d-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a><span data-ttu-id="9062d-143">См. также</span><span class="sxs-lookup"><span data-stu-id="9062d-143">See also</span></span>

- [<span data-ttu-id="9062d-144">Образцы наблюдения за AppFabric</span><span class="sxs-lookup"><span data-stu-id="9062d-144">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
