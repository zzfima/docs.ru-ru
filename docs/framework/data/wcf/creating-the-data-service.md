---
title: Создание службы данных WCF в Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: d30b2e30639837730ecb185a2c0f659a63955004
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975396"
---
# <a name="create-the-data-service"></a><span data-ttu-id="00003-102">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="00003-102">Create the data service</span></span>

<span data-ttu-id="00003-103">В этом разделе вы создадите образец службы данных, который использует WCF Data Services для предоставления веб-канала Open Data Protocol (OData), основанного на образце базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="00003-103">In this topic, you create a sample data service that uses WCF Data Services to expose an Open Data Protocol (OData) feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="00003-104">Задача включает следующие основные шаги.</span><span class="sxs-lookup"><span data-stu-id="00003-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="00003-105">создайте веб-приложение ASP.NET;</span><span class="sxs-lookup"><span data-stu-id="00003-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="00003-106">Определение модели данных с использованием средств для работы с моделью EDM.</span><span class="sxs-lookup"><span data-stu-id="00003-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="00003-107">Добавление службы данных в веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="00003-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="00003-108">Включите доступ к службе данных.</span><span class="sxs-lookup"><span data-stu-id="00003-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="00003-109">Создание веб-приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="00003-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="00003-110">В Visual Studio в меню **файл** выберите пункт **создать**  > **проект**.</span><span class="sxs-lookup"><span data-stu-id="00003-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="00003-111">В диалоговом окне **Новый проект** в разделе Visual Basic или Visual C# выберите категорию **веб-сайта** , а затем выберите **ASP.NET Web Application (веб-приложение**).</span><span class="sxs-lookup"><span data-stu-id="00003-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="00003-112">Введите `NorthwindService` в качестве имени проекта, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00003-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="00003-113">В диалоговом окне **новое веб-приложение ASP.NET** выберите **пусто** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00003-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="00003-114">(Необязательно) Укажите конкретный номер порта для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="00003-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="00003-115">Примечание. номер порта `12345` используется в этой серии кратких руководств.</span><span class="sxs-lookup"><span data-stu-id="00003-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="00003-116">В **Обозреватель решений**щелкните правой кнопкой мыши только что созданный проект ASP.NET, а затем выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="00003-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="00003-117">Перейдите на вкладку " **веб** " и задайте для параметра " **конкретный порт** " значение `12345`.</span><span class="sxs-lookup"><span data-stu-id="00003-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="00003-118">Определение модели данных</span><span class="sxs-lookup"><span data-stu-id="00003-118">Define the data model</span></span>

1. <span data-ttu-id="00003-119">В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="00003-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="00003-120">В диалоговом окне **Добавление нового элемента** выберите категорию **данные** , а затем выберите **ADO.NET EDM**.</span><span class="sxs-lookup"><span data-stu-id="00003-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="00003-121">В качестве имени модели данных введите `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="00003-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="00003-122">В **мастере EDM**выберите элемент **конструктор EF из базы данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="00003-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="00003-123">Подключите модель данных к базе данных, выполнив одно из следующих действий, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="00003-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="00003-124">Если подключение к базе данных уже не настроено, щелкните **создать подключение** и создайте новое подключение.</span><span class="sxs-lookup"><span data-stu-id="00003-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="00003-125">Дополнительные сведения см. в разделе [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="00003-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="00003-126">Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="00003-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="00003-127">\- или -</span><span class="sxs-lookup"><span data-stu-id="00003-127">\- or -</span></span>

    - <span data-ttu-id="00003-128">Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.</span><span class="sxs-lookup"><span data-stu-id="00003-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="00003-129">На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="00003-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="00003-130">Чтобы закрыть мастер, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="00003-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="00003-131">Создание службы данных WCF</span><span class="sxs-lookup"><span data-stu-id="00003-131">Create the WCF data service</span></span>

1. <span data-ttu-id="00003-132">В **Обозреватель решений**щелкните правой кнопкой мыши проект ASP.NET и выберите **Добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="00003-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="00003-133">В диалоговом окне **Добавление нового элемента** выберите шаблон элемента **службы данных WCF** из категории **веб** .</span><span class="sxs-lookup"><span data-stu-id="00003-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="00003-135">Шаблон **службы данных WCF** доступен в visual Studio 2015, но не в visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="00003-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="00003-136">В качестве имени службы введите `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="00003-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="00003-137">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="00003-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="00003-138">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="00003-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="00003-139">В **Обозреватель решений**служба имеет имя Northwind с расширением *SVC.CS* или *SVC. vb*.</span><span class="sxs-lookup"><span data-stu-id="00003-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="00003-140">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="00003-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="00003-141">Определение класса должно выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="00003-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="00003-142">Разрешение доступа к ресурсам службы данных</span><span class="sxs-lookup"><span data-stu-id="00003-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="00003-143">В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="00003-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="00003-144">Это обеспечивает авторизованным клиентам доступ для чтения и записи к ресурсам указанных наборов сущностей.</span><span class="sxs-lookup"><span data-stu-id="00003-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00003-145">Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="00003-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="00003-146">Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения.</span><span class="sxs-lookup"><span data-stu-id="00003-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="00003-147">Дополнительные сведения см. в разделе [Securing WCF Data Services](securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="00003-147">For more information, see [Securing WCF Data Services](securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="00003-148">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="00003-148">Next steps</span></span>

<span data-ttu-id="00003-149">Вы успешно создали новую службу данных, которая предоставляет канал OData, основанный на образце базы данных Northwind, и вы включили доступ к каналу для клиентов, имеющих разрешения для веб-приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="00003-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="00003-150">Далее вы запустите службу данных из Visual Studio и получите доступ к каналу OData, отправив запросы HTTP GET через веб-браузер:</span><span class="sxs-lookup"><span data-stu-id="00003-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="00003-151">Доступ к службе из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="00003-151">Access the service from a web browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="00003-152">См. также</span><span class="sxs-lookup"><span data-stu-id="00003-152">See also</span></span>

- <span data-ttu-id="00003-153">[Средства EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="00003-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
