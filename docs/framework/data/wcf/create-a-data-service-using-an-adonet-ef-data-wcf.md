---
title: Практическое руководство. Создание службы данных с использованием источника данных ADO.NET Entity Framework (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 78286cde925a4583a3610ce100d23e16adcefe49
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878077"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="ea78b-102">Практическое руководство. Создание службы данных с использованием источника данных ADO.NET Entity Framework (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="ea78b-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="ea78b-103">Службы данных WCF предоставляет данные сущности в виде службы данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="ea78b-104">Эти данные сущностей, предоставляемый платформой ADO.NET[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] когда источником данных является реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-104">This entity data is provided by the ADO.NET[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="ea78b-105">В этом разделе показано, как создать [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-на основе модели данных в Visual Studio веб-приложения, основанную на существующей базы данных и использовать эту модель данных для создания новой службы данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="ea78b-106">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Также предоставляет средство командной строки, позволяющее создать [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] модели за пределами проекта Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ea78b-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a Visual Studio project.</span></span> <span data-ttu-id="ea78b-107">Дополнительные сведения см. в разделе [Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="ea78b-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="ea78b-108">Добавление модели Entity Framework на основе существующей базы данных в существующее веб-приложение</span><span class="sxs-lookup"><span data-stu-id="ea78b-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="ea78b-109">На **проекта** меню, щелкните **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="ea78b-110">В **шаблоны** панели щелкните **данных** категории, а затем выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="ea78b-111">Введите имя модели и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="ea78b-112">Отображается первая страница мастера [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea78b-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>

4. <span data-ttu-id="ea78b-113">В **Выбор содержимого модели** выберите **создать из базы данных**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="ea78b-114">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-114">Then click **Next**.</span></span>

5. <span data-ttu-id="ea78b-115">Нажмите кнопку **новое подключение** кнопки.</span><span class="sxs-lookup"><span data-stu-id="ea78b-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="ea78b-116">В **свойства соединения** диалоговом окне введите имя сервера, выберите метод проверки подлинности, введите имя базы данных и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="ea78b-117">**Выбор подключения к данным** диалоговое окно обновляется параметры подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="ea78b-118">Убедитесь, что **сохранить настройки подключения сущности в App.Config как:** флажок.</span><span class="sxs-lookup"><span data-stu-id="ea78b-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="ea78b-119">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-119">Then click **Next**.</span></span>

8. <span data-ttu-id="ea78b-120">В **Choose Your Database Objects** диалоговое окно, выберите все объекты базы данных, которые планируется предоставлять в службе данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea78b-121">Объекты, включенные в модель данных, не предоставляются службой данных автоматически.</span><span class="sxs-lookup"><span data-stu-id="ea78b-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="ea78b-122">Они должны явно предоставляться самой службой.</span><span class="sxs-lookup"><span data-stu-id="ea78b-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="ea78b-123">Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ea78b-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="ea78b-124">Нажмите кнопку **Готово** завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="ea78b-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="ea78b-125">При этом создается модель данных по умолчанию на основе указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="ea78b-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] позволяет настроить модель данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="ea78b-127">Дополнительные сведения см. в разделе [задачи средств модели данных Entity](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ea78b-127">For more information, see [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="ea78b-128">Создание службы данных с использованием новой модели данных</span><span class="sxs-lookup"><span data-stu-id="ea78b-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="ea78b-129">Откройте в Visual Studio файл EDMX, представляющий модель данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="ea78b-130">В **браузер моделей**, щелкните правой кнопкой мыши модель, нажмите кнопку **свойства**и запишите имя контейнера сущностей.</span><span class="sxs-lookup"><span data-stu-id="ea78b-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="ea78b-131">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-131">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="ea78b-132">В **Добавление нового элемента** выберите **WCF-сервиса данных** шаблона в **Web** категории.</span><span class="sxs-lookup"><span data-stu-id="ea78b-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="ea78b-134">**WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ea78b-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

5. <span data-ttu-id="ea78b-135">Укажите имя для службы и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea78b-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="ea78b-136">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="ea78b-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="ea78b-137">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="ea78b-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="ea78b-138">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом, порожденным от класса <xref:System.Data.Objects.ObjectContext> и являющимся контейнером сущностей модели данных, который был отмечен на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="ea78b-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="ea78b-139">Включите в коде службы данных доступ авторизованных клиентов к наборам сущностей, предоставляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="ea78b-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="ea78b-140">Дополнительные сведения см. в разделе [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="ea78b-140">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>

8. <span data-ttu-id="ea78b-141">Чтобы проверить службы данных Northwind.svc с помощью веб-браузер, следуйте инструкциям в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="ea78b-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea78b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="ea78b-142">See also</span></span>

- [<span data-ttu-id="ea78b-143">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ea78b-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [<span data-ttu-id="ea78b-144">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="ea78b-144">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="ea78b-145">Практическое руководство. Создание службы данных с помощью поставщика отражения</span><span class="sxs-lookup"><span data-stu-id="ea78b-145">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="ea78b-146">Практическое руководство. Создание службы данных с использованием LINQ к источнику данных SQL</span><span class="sxs-lookup"><span data-stu-id="ea78b-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
