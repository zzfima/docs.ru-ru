---
title: Создание службы данных WCF в Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 361582866dabf51665e1dc94fdc49e8710d8ad3e
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091829"
---
# <a name="create-the-data-service"></a><span data-ttu-id="c0c8e-102">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="c0c8e-102">Create the data service</span></span>

<span data-ttu-id="c0c8e-103">В этом разделе создайте образец службы данных, который использует службы данных WCF для предоставления [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канал, основанный на образце базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="c0c8e-103">In this topic, you create a sample data service that uses WCF Data Services to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="c0c8e-104">Задача включает следующие основные шаги.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="c0c8e-105">создайте веб-приложение ASP.NET;</span><span class="sxs-lookup"><span data-stu-id="c0c8e-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="c0c8e-106">Определение модели данных с использованием средств для работы с моделью EDM.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="c0c8e-107">Добавление службы данных в веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="c0c8e-108">Включите доступ к службе данных.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="c0c8e-109">Создание веб-приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c0c8e-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="c0c8e-110">В Visual Studio на **файл** меню, выберите **New** > **проекта**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="c0c8e-111">В **новый проект** диалоговое окно, в разделе Visual Basic или Visual C# выберите **Web** категории, а затем выберите **веб-приложение ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="c0c8e-112">Введите `NorthwindService` как имя проекта и выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="c0c8e-113">В **новое веб-приложение ASP.NET** диалоговом окне выберите **пустой** , а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="c0c8e-114">(Необязательно) Укажите конкретный номер порта для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="c0c8e-115">Примечание: номер порта `12345` используется в этой серии разделы краткого руководства.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="c0c8e-116">В **обозревателе решений**, щелкните правой кнопкой мыши на проекте ASP.NET, который вы только что создали и затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="c0c8e-117">Выберите **Web** и задайте значение **определенный порт** текстового поля, чтобы `12345`.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="c0c8e-118">Определение модели данных</span><span class="sxs-lookup"><span data-stu-id="c0c8e-118">Define the data model</span></span>

1. <span data-ttu-id="c0c8e-119">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="c0c8e-120">В **Добавление нового элемента** выберите **данных** категории, а затем выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="c0c8e-121">Введите имя модели данных `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="c0c8e-122">В **мастер моделей EDM**выберите **конструктор EF из базы данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="c0c8e-123">Подключите модель данных в базу данных, выполнив одно из следующих действий, а затем нажмите кнопку **Далее**:</span><span class="sxs-lookup"><span data-stu-id="c0c8e-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    -   <span data-ttu-id="c0c8e-124">Если у вас нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создайте новое соединение.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="c0c8e-125">Дополнительные сведения см. в разделе [Как Создание подключений к базам данных SQL Server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c0c8e-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="c0c8e-126">Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="c0c8e-127">\- или -</span><span class="sxs-lookup"><span data-stu-id="c0c8e-127">\- or -</span></span>

    -   <span data-ttu-id="c0c8e-128">Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="c0c8e-129">На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="c0c8e-130">Нажмите кнопку **Готово** чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="c0c8e-131">Создание службы данных WCF</span><span class="sxs-lookup"><span data-stu-id="c0c8e-131">Create the WCF data service</span></span>

1. <span data-ttu-id="c0c8e-132">В **обозревателе решений**, правой кнопкой мыши проект ASP.NET и затем выберите **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="c0c8e-133">В **Добавление нового элемента** выберите **WCF-сервиса данных** шаблон элемента из **Web** категории.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="c0c8e-135">**WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="c0c8e-136">Имя службы, введите `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="c0c8e-137">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="c0c8e-138">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="c0c8e-139">В **обозревателе решений**, служба имеет имя Northwind с расширением *. svc.cs* или *. svc.vb*.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="c0c8e-140">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="c0c8e-141">Определение класса должно выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="c0c8e-142">Разрешить доступ к ресурсам службы данных</span><span class="sxs-lookup"><span data-stu-id="c0c8e-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="c0c8e-143">В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="c0c8e-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="c0c8e-144">Это обеспечивает авторизованным клиентам доступ для чтения и записи к ресурсам указанных наборов сущностей.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0c8e-145">Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="c0c8e-146">Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="c0c8e-147">Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c0c8e-147">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0c8e-148">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c0c8e-148">Next steps</span></span>

<span data-ttu-id="c0c8e-149">Вы успешно создали новую службу данных, предоставляющего канал OData, основанный на образце базы данных Northwind и включили доступ к каналу для клиентов, имеющих разрешения на веб-приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="c0c8e-150">Далее необходимо запустить службу данных из Visual Studio и доступа к каналу путем отправки запросов HTTP GET через веб-браузер OData:</span><span class="sxs-lookup"><span data-stu-id="c0c8e-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c0c8e-151">Доступ к службе из веб-браузер</span><span class="sxs-lookup"><span data-stu-id="c0c8e-151">Access the service from a web browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="c0c8e-152">См. также</span><span class="sxs-lookup"><span data-stu-id="c0c8e-152">See also</span></span>

- <span data-ttu-id="c0c8e-153">[Средства модели EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c0c8e-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>