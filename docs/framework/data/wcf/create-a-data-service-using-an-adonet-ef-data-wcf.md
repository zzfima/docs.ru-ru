---
title: "Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e90b11800685707460171e5e2d250ef757979c44
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="68bb4-102">Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="68bb4-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="68bb4-103"> предоставляет данные сущности в виде службы данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-103"> exposes entity data as a data service.</span></span> <span data-ttu-id="68bb4-104">Эти данные сущностей обеспечивается [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Если источником данных является реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="68bb4-105">В этом разделе будет показано создание модели данных на базе [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] в веб-приложении [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], основанном на существующей базе данных, а также создание новой службы данных с помощью этой модели.</span><span class="sxs-lookup"><span data-stu-id="68bb4-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web application that is based on an existing database and use this data model to create a new data service.</span></span>  
  
 <span data-ttu-id="68bb4-106">Кроме того, в составе [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] предусмотрена программа командной строки, которая может создавать модель [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] за пределами проекта [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68bb4-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="68bb4-107">Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания модели и сопоставления файлов](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="68bb4-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="68bb4-108">Добавление модели Entity Framework на основе существующей базы данных в существующее веб-приложение</span><span class="sxs-lookup"><span data-stu-id="68bb4-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>  
  
1.  <span data-ttu-id="68bb4-109">На **проекта** меню, нажмите кнопку **добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-109">On the **Project** menu, click **Add new item**.</span></span>  
  
2.  <span data-ttu-id="68bb4-110">В **шаблоны** области, нажмите кнопку **данные** категории, а затем выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="68bb4-111">Введите имя модели и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-111">Type the model name and then click **Add**.</span></span>  
  
     <span data-ttu-id="68bb4-112">Отображается первая страница мастера [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68bb4-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>  
  
4.  <span data-ttu-id="68bb4-113">В **Выбор содержимого модели** выберите **создать из базы данных**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="68bb4-114">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-114">Then click **Next**.</span></span>  
  
5.  <span data-ttu-id="68bb4-115">Нажмите кнопку **новое подключение** кнопки.</span><span class="sxs-lookup"><span data-stu-id="68bb4-115">Click the **New Connection** button.</span></span>  
  
6.  <span data-ttu-id="68bb4-116">В **свойства соединения** диалоговое окно, введите имя сервера, выберите метод проверки подлинности, введите имя базы данных и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="68bb4-117">**Выбор подключения к данным**диалогового обновляется параметры подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>  
  
7.  <span data-ttu-id="68bb4-118">Убедитесь, что **сохранить настройки подключения сущности в App.Config как:** установлен флажок.</span><span class="sxs-lookup"><span data-stu-id="68bb4-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="68bb4-119">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-119">Then click **Next**.</span></span>  
  
8.  <span data-ttu-id="68bb4-120">В **Выбор объектов базы данных** диалоговое окно, выберите все объекты базы данных, которые планируется предоставлять в службе данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68bb4-121">Объекты, включенные в модель данных, не предоставляются службой данных автоматически.</span><span class="sxs-lookup"><span data-stu-id="68bb4-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="68bb4-122">Они должны явно предоставляться самой службой.</span><span class="sxs-lookup"><span data-stu-id="68bb4-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="68bb4-123">Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="68bb4-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
9. <span data-ttu-id="68bb4-124">Нажмите кнопку **Готово** для завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="68bb4-124">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="68bb4-125">При этом создается модель данных по умолчанию на основе указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="68bb4-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] позволяет настроить модель данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="68bb4-127">Дополнительные сведения см. в разделе [Задачи](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span><span class="sxs-lookup"><span data-stu-id="68bb4-127">For more information, see [Tasks](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="68bb4-128">Создание службы данных с использованием новой модели данных</span><span class="sxs-lookup"><span data-stu-id="68bb4-128">To create the data service by using the new data model</span></span>  
  
1.  <span data-ttu-id="68bb4-129">В [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] откройте EDMX-файл, представляющий модель данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the .edmx file that represents the data model.</span></span>  
  
2.  <span data-ttu-id="68bb4-130">В **браузер моделей**, щелкните правой кнопкой мыши модель, нажмите кнопку **свойства**и запишите имя контейнера сущностей.</span><span class="sxs-lookup"><span data-stu-id="68bb4-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>  
  
3.  <span data-ttu-id="68bb4-131">В **обозревателе решений**, щелкните правой кнопкой мыши имя вашего [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
4.  <span data-ttu-id="68bb4-132">В **Добавление нового элемента** выберите **службы данных WCF**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-132">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
5.  <span data-ttu-id="68bb4-133">Задайте имя для службы и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="68bb4-133">Supply a name for the service, and then click **OK**.</span></span>  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="68bb4-134"> создает метку XML и файлы с кодом для новой службы.</span><span class="sxs-lookup"><span data-stu-id="68bb4-134"> creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="68bb4-135">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="68bb4-135">By default, the code-editor window opens.</span></span>  
  
6.  <span data-ttu-id="68bb4-136">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом, порожденным от класса <xref:System.Data.Objects.ObjectContext> и являющимся контейнером сущностей модели данных, который был отмечен на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="68bb4-136">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>  
  
7.  <span data-ttu-id="68bb4-137">Включите в коде службы данных доступ авторизованных клиентов к наборам сущностей, предоставляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="68bb4-137">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="68bb4-138">Дополнительные сведения см. в разделе [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="68bb4-138">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
8.  <span data-ttu-id="68bb4-139">Для тестирования службы Northwind.svc данных с помощью веб-браузера, следуйте инструкциям в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="68bb4-139">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68bb4-140">См. также</span><span class="sxs-lookup"><span data-stu-id="68bb4-140">See Also</span></span>  
 [<span data-ttu-id="68bb4-141">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="68bb4-141">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="68bb4-142">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="68bb4-142">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="68bb4-143">Практическое руководство. Создание службы данных с использованием поставщика отражений</span><span class="sxs-lookup"><span data-stu-id="68bb4-143">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="68bb4-144">Практическое руководство. Создание службы данных с использованием источника данных LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="68bb4-144">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
