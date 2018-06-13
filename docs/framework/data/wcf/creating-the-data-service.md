---
title: Создание службы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: bb6e2f7c1160fa51cd897cc953ad0ed721559294
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362841"
---
# <a name="creating-the-data-service"></a><span data-ttu-id="c2d04-102">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="c2d04-102">Creating the Data Service</span></span>
<span data-ttu-id="c2d04-103">В этой задаче вы создадите образца службы данных, который использует [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для предоставления [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] канала, который основан на образце базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="c2d04-103">In this task, you will create a sample data service that uses [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that is based on the Northwind sample database.</span></span> <span data-ttu-id="c2d04-104">Задача включает следующие основные шаги.</span><span class="sxs-lookup"><span data-stu-id="c2d04-104">The task involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="c2d04-105">Создайте веб-приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2d04-105">Create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span>  
  
2.  <span data-ttu-id="c2d04-106">Определите модель данных с помощью средств [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2d04-106">Define the data model by using the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools.</span></span>  
  
3.  <span data-ttu-id="c2d04-107">Добавление службы данных в веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="c2d04-107">Add the data service to the Web application.</span></span>  
  
4.  <span data-ttu-id="c2d04-108">Включите доступ к службе данных.</span><span class="sxs-lookup"><span data-stu-id="c2d04-108">Enable access to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2d04-109">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Выполняется веб-приложение, создаваемое после завершения этой задачи [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , предоставляемые Visual Studio Development Server.</span><span class="sxs-lookup"><span data-stu-id="c2d04-109">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application that you create when you complete this task runs on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server provided by Visual Studio.</span></span> <span data-ttu-id="c2d04-110">Сервер разработки [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поддерживает доступ только с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c2d04-110">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server only supports access from the local computer.</span></span> <span data-ttu-id="c2d04-111">Чтобы упростить тестирование и устранение неполадок службы данных в ходе разработки, попробуйте также запустить с помощью IIS приложение со службой данных.</span><span class="sxs-lookup"><span data-stu-id="c2d04-111">To also make it easier to test and troubleshoot the data service during development, consider running the application that hosts the data service by using Internet Information Services (IIS).</span></span> <span data-ttu-id="c2d04-112">Для получения дополнительной информации см. [Практическое руководство. Разработка службы данных WCF Data Service, работающей на IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span><span class="sxs-lookup"><span data-stu-id="c2d04-112">For more information, see [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application"></a><span data-ttu-id="c2d04-113">Создание веб-приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c2d04-113">To create the ASP.NET Web application</span></span>  
  
1.  <span data-ttu-id="c2d04-114">В Visual Studio на **файл** выберите пункт **New**, а затем выберите **проекта**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-114">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="c2d04-115">В **новый проект** в поле выберите Visual Basic или Visual C# **Web** шаблона, а затем выберите **веб-приложение ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-115">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** template, and then select **ASP.NET Web Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2d04-116">Если используется среда Visual Studio Web Developer, то вместо нового веб-приложения нужно будет создать новый веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="c2d04-116">If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
3.  <span data-ttu-id="c2d04-117">Тип `NorthwindService` как имя проекта.</span><span class="sxs-lookup"><span data-stu-id="c2d04-117">Type `NorthwindService` as the name of the project.</span></span>  
  
4.  <span data-ttu-id="c2d04-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c2d04-119">(Необязательно) Укажите конкретный номер порта для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="c2d04-119">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="c2d04-120">Примечание. В оставшейся части этого краткого руководства используется номер порта `12345`.</span><span class="sxs-lookup"><span data-stu-id="c2d04-120">Note: the port number `12345` is used in the rest of the quickstart.</span></span>  
  
    1.  <span data-ttu-id="c2d04-121">В **обозревателе решений**, щелкните правой кнопкой мыши имя [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта только что создан и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-121">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project that you just created, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="c2d04-122">Выберите **Web** и задайте значение **определенный порт** текстового поля, чтобы `12345`.</span><span class="sxs-lookup"><span data-stu-id="c2d04-122">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="c2d04-123">Определение модели данных</span><span class="sxs-lookup"><span data-stu-id="c2d04-123">To define the data model</span></span>  
  
1.  <span data-ttu-id="c2d04-124">В **обозревателе решений**, щелкните правой кнопкой мыши имя [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **Добавление нового элемента.**</span><span class="sxs-lookup"><span data-stu-id="c2d04-124">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="c2d04-125">В **Добавление нового элемента** диалоговое окно, нажмите кнопку **данные** шаблона, а затем выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-125">In the **Add New Item** dialog box, click the **Data** template and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="c2d04-126">Введите имя модели данных, `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="c2d04-126">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="c2d04-127">В [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] мастера выберите **создать из базы данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-127">In the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c2d04-128">Подключите модель данных в базу данных, выполнив одно из следующих действий и нажмите кнопку **Далее**:</span><span class="sxs-lookup"><span data-stu-id="c2d04-128">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="c2d04-129">Если нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="c2d04-129">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="c2d04-130">Дополнительные сведения см. в разделе [как: создание подключений к базам данных SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="c2d04-130">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="c2d04-131">Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="c2d04-131">This SQL Server instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="c2d04-132">\- или -</span><span class="sxs-lookup"><span data-stu-id="c2d04-132">\- or -</span></span>  
  
    -   <span data-ttu-id="c2d04-133">Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.</span><span class="sxs-lookup"><span data-stu-id="c2d04-133">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="c2d04-134">На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="c2d04-134">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="c2d04-135">Нажмите кнопку **Готово** для завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="c2d04-135">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2d04-136">Эта сформированная модель данных предоставляет свойства внешнего ключа для типов сущности.</span><span class="sxs-lookup"><span data-stu-id="c2d04-136">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="c2d04-137">Модели данных, созданные с помощью Visual Studio 2008, не включают эти свойства внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="c2d04-137">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="c2d04-138">В связи с этим перед получением доступа к этой версии службы данных Northwind необходимо обновить клиентские классы службы данных любого клиентского приложения для доступа к службе данных, созданного с помощью среды Visual Studio 2008.</span><span class="sxs-lookup"><span data-stu-id="c2d04-138">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="c2d04-139">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="c2d04-139">To create the data service</span></span>  
  
1.  <span data-ttu-id="c2d04-140">В **обозревателе решений**, щелкните правой кнопкой мыши имя вашего [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-140">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="c2d04-141">В **Добавление нового элемента** выберите **службы данных WCF**.</span><span class="sxs-lookup"><span data-stu-id="c2d04-141">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
3.  <span data-ttu-id="c2d04-142">Имя службы, введите `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="c2d04-142">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="c2d04-143">Visual StudioVisual Studio создает файлы разметки и кодов XML для новой службы.</span><span class="sxs-lookup"><span data-stu-id="c2d04-143">Visual StudioVisual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="c2d04-144">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="c2d04-144">By default, the code-editor window opens.</span></span> <span data-ttu-id="c2d04-145">В **обозревателе решений**, для службы будет отображаться имя Northwind с расширением. svc.cs или. svc.vb.</span><span class="sxs-lookup"><span data-stu-id="c2d04-145">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="c2d04-146">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="c2d04-146">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="c2d04-147">Определение класса должно выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c2d04-147">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a><span data-ttu-id="c2d04-148">Включение доступа к ресурсам службы данных</span><span class="sxs-lookup"><span data-stu-id="c2d04-148">To enable access to data service resources</span></span>  
  
1.  <span data-ttu-id="c2d04-149">В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="c2d04-149">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="c2d04-150">Это обеспечивает авторизованным клиентам доступ для чтения и записи к ресурсам указанных наборов сущностей.</span><span class="sxs-lookup"><span data-stu-id="c2d04-150">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2d04-151">Клиент, пытающийся получить доступ к приложению [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], может также получить доступ к источникам, представляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="c2d04-151">Any client that can access the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="c2d04-152">Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения.</span><span class="sxs-lookup"><span data-stu-id="c2d04-152">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="c2d04-153">Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c2d04-153">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c2d04-154">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c2d04-154">Next Steps</span></span>  
 <span data-ttu-id="c2d04-155">Успешно создана новая служба данных, которая предоставляет [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] канала, который основан на базе данных Northwind и включен доступ к потоку для клиентов, имеющих разрешения на [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="c2d04-155">You have successfully created a new data service that exposes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span> <span data-ttu-id="c2d04-156">Теперь запустим эту службу данных из среды Visual Studio и обратимся к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с помощью запросов HTTP GET через веб-браузер.</span><span class="sxs-lookup"><span data-stu-id="c2d04-156">Next, you will start the data service from Visual Studio and you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by submitting HTTP GET requests through a Web browser:</span></span>  
  
 [<span data-ttu-id="c2d04-157">Доступ к службе из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="c2d04-157">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="c2d04-158">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d04-158">See Also</span></span>  
 [<span data-ttu-id="c2d04-159">Средства работы с моделью EDM ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c2d04-159">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
