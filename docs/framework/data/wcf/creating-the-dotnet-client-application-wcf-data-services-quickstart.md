---
title: Создание клиентского приложения .NET Framework (краткое руководство по службам данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 4beaba24e42b15ebc45ece6e5319a2b14df54ab6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975384"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="80463-102">Создание клиентского приложения .NET Framework (краткое руководство по службам данных WCF)</span><span class="sxs-lookup"><span data-stu-id="80463-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="80463-103">Это последняя задача краткого руководства по WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="80463-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="80463-104">В этой задаче вы добавите в решение консольное приложение, добавите ссылку на веб-канал Open Data Protocol (OData) в это новое клиентское приложение и получите доступ к каналу OData из клиентского приложения с помощью созданных клиентских классов службы данных и клиента. Libraries.</span><span class="sxs-lookup"><span data-stu-id="80463-104">In this task, you will add a console application to the solution, add a reference to the Open Data Protocol (OData) feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="80463-105">Для доступа к каналу данных наличие клиентского приложения на основе .NET Framework необязательно.</span><span class="sxs-lookup"><span data-stu-id="80463-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="80463-106">Доступ к службе данных может осуществляться любым компонентом приложения, использующим канал OData.</span><span class="sxs-lookup"><span data-stu-id="80463-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="80463-107">Дополнительные сведения см. [в разделе Использование службы данных в клиентском приложении](using-a-data-service-in-a-client-application-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="80463-107">For more information, see [Using a Data Service in a Client Application](using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="80463-108">Создание клиентского приложения в среде Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80463-108">To create the client application by using Visual Studio</span></span>

1. <span data-ttu-id="80463-109">В **Обозреватель решений**щелкните решение правой кнопкой мыши, выберите **Добавить**, а затем — **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="80463-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="80463-110">В левой области выберите **установленные** > [**Visual C#**  или **Visual Basic**] > **Рабочий стол Windows**, а затем выберите шаблон **приложения WPF** .</span><span class="sxs-lookup"><span data-stu-id="80463-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3. <span data-ttu-id="80463-111">Введите `NorthwindClient` в поле имя проекта, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="80463-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4. <span data-ttu-id="80463-112">Откройте файл MainWindow.xaml и замените XAML-код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="80463-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="80463-113">Добавление в проект ссылки на службу данных</span><span class="sxs-lookup"><span data-stu-id="80463-113">To add a data service reference to the project</span></span>

1. <span data-ttu-id="80463-114">В **Обозреватель решений**щелкните правой кнопкой мыши проект узлом NorthwindClient, выберите **Добавить** > **ссылку на службу**, а затем нажмите кнопку **обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="80463-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="80463-115">При этом отображается служба данных Northwind, созданная в первой задаче.</span><span class="sxs-lookup"><span data-stu-id="80463-115">This displays the Northwind data service that you created in the first task.</span></span>

2. <span data-ttu-id="80463-116">В текстовом поле **пространство имен** введите `Northwind`и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="80463-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="80463-117">При этом в проект добавляется новый файл кода, содержащий классы данных, которые используются для обращения и взаимодействия с ресурсами службы данных как с объектами.</span><span class="sxs-lookup"><span data-stu-id="80463-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="80463-118">Классы данных создаются в пространстве имен `NorthwindClient.Northwind`.</span><span class="sxs-lookup"><span data-stu-id="80463-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="80463-119">Обращение к данным службы данных в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="80463-119">To access data service data in the WPF application</span></span>

1. <span data-ttu-id="80463-120">В **Обозреватель решений** в разделе **узлом NorthwindClient**щелкните правой кнопкой мыши проект и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="80463-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2. <span data-ttu-id="80463-121">В диалоговом окне **Добавление ссылки** перейдите на вкладку **.NET** , выберите сборку System. Data. Services. Client. dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="80463-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="80463-122">В **Обозреватель решений** в разделе **узлом NorthwindClient**откройте кодовую страницу файла MainWindow. XAML и добавьте следующую инструкцию `using` (`Imports` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="80463-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. <span data-ttu-id="80463-123">Вставьте следующий код, запрашивающий службу данных и привязывающий результат к коллекции <xref:System.Data.Services.Client.DataServiceCollection%601> класса `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="80463-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="80463-124">Имя узла `localhost:12345` нужно заменить на сервер и порт, на котором размещен экземпляр службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="80463-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. <span data-ttu-id="80463-125">Вставьте следующий код, сохраняющий изменения, в класс `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="80463-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="80463-126">Сборка и запуск приложения NothwindClient</span><span class="sxs-lookup"><span data-stu-id="80463-126">To build and run the NorthwindClient application</span></span>

1. <span data-ttu-id="80463-127">В **Обозреватель решений**щелкните правой кнопкой мыши проект узлом NorthwindClient и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="80463-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2. <span data-ttu-id="80463-128">Нажмите клавишу **F5** , чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="80463-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="80463-129">При этом выполняется сборка решения и запуск клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="80463-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="80463-130">Данные извлекаются из службы данных и отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="80463-130">Data is requested from the service and displayed in the console.</span></span>

3. <span data-ttu-id="80463-131">Измените значение в столбце **количество** сетки данных и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="80463-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="80463-132">Изменения будут сохранены в службе данных.</span><span class="sxs-lookup"><span data-stu-id="80463-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80463-133">Эта версия приложения NorthwindClient не поддерживает добавление и удаление сущностей.</span><span class="sxs-lookup"><span data-stu-id="80463-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80463-134">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="80463-134">Next Steps</span></span>

<span data-ttu-id="80463-135">Вы успешно создали клиентское приложение, которое обращается к примеру веб-канала OData Northwind.</span><span class="sxs-lookup"><span data-stu-id="80463-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="80463-136">Вы также выполнили WCF Data Services быстрый запуск.</span><span class="sxs-lookup"><span data-stu-id="80463-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="80463-137">Дополнительные сведения о доступе к каналу OData из .NET Framework приложения см. в разделе [WCF Data Services Client Library](wcf-data-services-client-library.md).</span><span class="sxs-lookup"><span data-stu-id="80463-137">For more information about accessing an OData feed from a .NET Framework application, see [WCF Data Services Client Library](wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="80463-138">См. также</span><span class="sxs-lookup"><span data-stu-id="80463-138">See also</span></span>

- [<span data-ttu-id="80463-139">Начало работы</span><span class="sxs-lookup"><span data-stu-id="80463-139">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="80463-140">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="80463-140">Resources</span></span>](wcf-data-services-resources.md)
