---
title: Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 0aea4c21b5ea34cb0e8d944d37c879e918d6b27e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800574"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="4628e-102">Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="4628e-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="4628e-103">WCF Data Services предоставляет данные сущности в качестве службы данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="4628e-104">Эти данные сущности предоставляются платформой ADO. Нетентити, если источником данных является реляционная база данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-104">This entity data is provided by the ADO.NETEntity Framework when the data source is a relational database.</span></span> <span data-ttu-id="4628e-105">Данный раздел иллюстрирует создание модели данных на основе Entity Framework в веб-приложении Visual Studio, основанном на существующей базе данных, и использование этой модели данных для создания новой службы данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-105">This topic shows you how to create an Entity Framework-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="4628e-106">Среда Entity Framework предоставляет также программу командной строки, формирующую модель Entity Framework вне проекта Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4628e-106">The Entity Framework also provides a command line tool that can generate an Entity Framework model outside of a Visual Studio project.</span></span> <span data-ttu-id="4628e-107">Дополнительные сведения см. в разделе [инструкции. Использование программы EdmGen. exe для создания файлов модели и сопоставления](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="4628e-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="4628e-108">Добавление модели Entity Framework на основе существующей базы данных в существующее веб-приложение</span><span class="sxs-lookup"><span data-stu-id="4628e-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="4628e-109">В меню **проект** выберите команду **Добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="4628e-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="4628e-110">В области **шаблоны** щелкните категорию **данных** , а затем выберите **ADO.NET EDM**.</span><span class="sxs-lookup"><span data-stu-id="4628e-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="4628e-111">Введите имя модели и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4628e-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="4628e-112">Открывается первая страница мастера моделей EDM.</span><span class="sxs-lookup"><span data-stu-id="4628e-112">The first page of the Entity Data Model Wizard is displayed.</span></span>

4. <span data-ttu-id="4628e-113">В диалоговом окне **Выбор содержимого модели** выберите **создать из базы данных**.</span><span class="sxs-lookup"><span data-stu-id="4628e-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="4628e-114">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4628e-114">Then click **Next**.</span></span>

5. <span data-ttu-id="4628e-115">Нажмите кнопку **создать подключение** .</span><span class="sxs-lookup"><span data-stu-id="4628e-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="4628e-116">В диалоговом окне **Свойства соединения** введите имя сервера, выберите метод проверки подлинности, введите имя базы данных и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4628e-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="4628e-117">В диалоговом окне **Выбор подключения к данным** будут обновлены параметры подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="4628e-118">Убедитесь, что установлен флажок **сохранить параметры подключения сущности в App. config AS:** .</span><span class="sxs-lookup"><span data-stu-id="4628e-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="4628e-119">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4628e-119">Then click **Next**.</span></span>

8. <span data-ttu-id="4628e-120">В диалоговом окне **Выбор объектов базы данных** выберите все объекты базы данных, которые планируется предоставить в службе данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4628e-121">Объекты, включенные в модель данных, не предоставляются службой данных автоматически.</span><span class="sxs-lookup"><span data-stu-id="4628e-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="4628e-122">Они должны явно предоставляться самой службой.</span><span class="sxs-lookup"><span data-stu-id="4628e-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="4628e-123">Дополнительные сведения см. [в разделе Настройка службы данных](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4628e-123">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="4628e-124">Чтобы завершить работу мастера, нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="4628e-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="4628e-125">При этом создается модель данных по умолчанию на основе указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="4628e-126">Entity Framework позволяет настроить модель данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-126">The Entity Framework enables to customize the data model.</span></span> <span data-ttu-id="4628e-127">Дополнительные сведения см. в разделе [EDM Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4628e-127">For more information, see [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="4628e-128">Создание службы данных с использованием новой модели данных</span><span class="sxs-lookup"><span data-stu-id="4628e-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="4628e-129">Откройте в Visual Studio файл EDMX, представляющий модель данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="4628e-130">В **обозревателе моделей**щелкните правой кнопкой мыши модель, выберите пункт **свойства**, а затем запишите имя контейнера сущностей.</span><span class="sxs-lookup"><span data-stu-id="4628e-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="4628e-131">В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="4628e-131">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="4628e-132">В диалоговом окне **Добавление нового элемента** выберите шаблон **WCF Data Service** в категории **веб** .</span><span class="sxs-lookup"><span data-stu-id="4628e-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="4628e-134">Шаблон **службы данных WCF** доступен в visual Studio 2015, но не в visual Studio 2017 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4628e-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

5. <span data-ttu-id="4628e-135">Укажите имя службы и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4628e-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="4628e-136">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="4628e-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="4628e-137">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="4628e-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="4628e-138">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом, порожденным от класса <xref:System.Data.Objects.ObjectContext> и являющимся контейнером сущностей модели данных, который был отмечен на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="4628e-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="4628e-139">Включите в коде службы данных доступ авторизованных клиентов к наборам сущностей, предоставляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="4628e-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="4628e-140">Дополнительные сведения см. [в разделе Создание службы данных](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="4628e-140">For more information, see [Creating the Data Service](creating-the-data-service.md).</span></span>

8. <span data-ttu-id="4628e-141">Чтобы протестировать службу данных Northwind. svc с помощью веб-браузера, следуйте инструкциям в разделе [обращение к службе из веб-браузера](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="4628e-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4628e-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="4628e-142">See also</span></span>

- [<span data-ttu-id="4628e-143">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="4628e-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="4628e-144">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="4628e-144">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="4628e-145">Практическое руководство. Создание службы данных с использованием поставщика отражений</span><span class="sxs-lookup"><span data-stu-id="4628e-145">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="4628e-146">Практическое руководство. Создание службы данных с использованием источника данных LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4628e-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
