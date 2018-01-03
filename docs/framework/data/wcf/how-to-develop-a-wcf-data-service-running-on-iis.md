---
title: "Как разработать службу данных WCF Data Service, работающую на IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93b6e8b6e687f2e39fd5792aba08eaa47fa29fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="351f8-102">Как разработать службу данных WCF Data Service, работающую на IIS</span><span class="sxs-lookup"><span data-stu-id="351f8-102">How to: Develop a WCF Data Service Running on IIS</span></span>
<span data-ttu-id="351f8-103">В этом разделе показано, как использовать [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для создания службы данных, основанный на образце базы данных Northwind, размещенное на веб-приложения ASP.NET, на котором работает в Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="351f8-103">This topic shows how to use [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="351f8-104">Пример создания службы данных Northwind в виде веб-приложения ASP.NET, работающая на сервере разработки ASP.NET см. в разделе [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="351f8-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="351f8-105">Для создания службы данных Northwind необходимо установить образец базы данных Northwind на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="351f8-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="351f8-106">Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758)(Образцы баз данных для SQL Server).</span><span class="sxs-lookup"><span data-stu-id="351f8-106">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
 <span data-ttu-id="351f8-107">Данный раздел иллюстрирует создание службы данных с помощью поставщика Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="351f8-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="351f8-108">Доступны другие поставщики служб данных.</span><span class="sxs-lookup"><span data-stu-id="351f8-108">Other data services providers are available.</span></span> <span data-ttu-id="351f8-109">Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="351f8-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="351f8-110">После создания службы требуется явно предоставить доступ к ресурсам службы данных.</span><span class="sxs-lookup"><span data-stu-id="351f8-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="351f8-111">Дополнительные сведения см. в разделе [как: разрешить доступ к службе данных](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="351f8-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="351f8-112">Создание веб-приложения ASP.NET, работающего на базе IIS</span><span class="sxs-lookup"><span data-stu-id="351f8-112">To create the ASP.NET Web application that runs on IIS</span></span>  
  
1.  <span data-ttu-id="351f8-113">В Visual Studio на **файл** выберите пункт **New**, а затем выберите **проекта**.</span><span class="sxs-lookup"><span data-stu-id="351f8-113">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="351f8-114">В **новый проект** диалогового окна выберите Visual Basic или Visual C# в качестве языка программирования.</span><span class="sxs-lookup"><span data-stu-id="351f8-114">In the **New Project** dialog box, select either Visual Basic or Visual C# as the programming language.</span></span>  
  
3.  <span data-ttu-id="351f8-115">В **шаблоны** выберите **веб-приложение ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="351f8-115">In the **Templates** pane, select **ASP.NET Web Application**.</span></span> <span data-ttu-id="351f8-116">Примечание. Если используется среда Visual Studio Web Developer, то вместо нового веб-приложения нужно будет создать новый веб-узел.</span><span class="sxs-lookup"><span data-stu-id="351f8-116">Note: If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
4.  <span data-ttu-id="351f8-117">Тип `NorthwindService` как имя проекта.</span><span class="sxs-lookup"><span data-stu-id="351f8-117">Type `NorthwindService` as the name of the project.</span></span>  
  
5.  <span data-ttu-id="351f8-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="351f8-118">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="351f8-119">На **проекта** последовательно выберите пункты **свойства службы Northwind**.</span><span class="sxs-lookup"><span data-stu-id="351f8-119">On the **Project** menu, select **NorthwindService Properties**.</span></span>  
  
7.  <span data-ttu-id="351f8-120">Выберите **Web** , а затем выберите **использовать локальный веб-сервер IIS**.</span><span class="sxs-lookup"><span data-stu-id="351f8-120">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>  
  
8.  <span data-ttu-id="351f8-121">Нажмите кнопку **создать виртуальный каталог** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="351f8-121">Click **Create Virtual Directory** and then click **OK**.</span></span>  
  
9. <span data-ttu-id="351f8-122">С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).</span><span class="sxs-lookup"><span data-stu-id="351f8-122">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="351f8-123">32-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="351f8-123">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   <span data-ttu-id="351f8-124">64-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="351f8-124">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     <span data-ttu-id="351f8-125">Она регистрирует Windows Communication Foundation (WCF) на компьютере.</span><span class="sxs-lookup"><span data-stu-id="351f8-125">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>  
  
10. <span data-ttu-id="351f8-126">С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).</span><span class="sxs-lookup"><span data-stu-id="351f8-126">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="351f8-127">32-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="351f8-127">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   <span data-ttu-id="351f8-128">64-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="351f8-128">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     <span data-ttu-id="351f8-129">Это необходимо для того, чтобы проверить правильность работы служб IIS после установки WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="351f8-129">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="351f8-130">Возможно, потребуется перезапустить службы IIS.</span><span class="sxs-lookup"><span data-stu-id="351f8-130">You might have to also restart IIS.</span></span>  
  
11. <span data-ttu-id="351f8-131">Если приложение ASP.NET запущено в службах IIS7, нужно также выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="351f8-131">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="351f8-132">Откройте диспетчер служб IIS и перейдите в приложение PhotoService на **веб-сайт по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="351f8-132">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="351f8-133">В **Просмотр возможностей**, дважды щелкните **проверки подлинности**.</span><span class="sxs-lookup"><span data-stu-id="351f8-133">In **Features View**, double-click **Authentication**.</span></span>  
  
    3.  <span data-ttu-id="351f8-134">На **проверки подлинности** выберите **анонимную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="351f8-134">On the **Authentication** page, select **Anonymous Authentication**.</span></span>  
  
    4.  <span data-ttu-id="351f8-135">В **действия** области, нажмите кнопку **изменить** Чтобы задать участника безопасности, в области которого анонимные пользователи будут подключаться к сайту.</span><span class="sxs-lookup"><span data-stu-id="351f8-135">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>  
  
    5.  <span data-ttu-id="351f8-136">В **изменение учетных данных анонимной проверки подлинности** выберите **удостоверение пула приложений**.</span><span class="sxs-lookup"><span data-stu-id="351f8-136">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="351f8-137">При использовании учетной записи сетевой службы анонимным пользователям предоставляется доступ к внутренней сети, связанной с этой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="351f8-137">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>  
  
12. <span data-ttu-id="351f8-138">С помощью среды SQL Server Management Studio, программы sqlcmd.exe или редактора Transact-SQL в Visual Studio выполните следующую команду Transact-SQL для экземпляра SQL Server с прикрепленной базой данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="351f8-138">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     <span data-ttu-id="351f8-139">Она создает имя входа в экземпляр SQL Server для учетной записи Windows, используемой для запуска служб IIS.</span><span class="sxs-lookup"><span data-stu-id="351f8-139">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="351f8-140">Это позволит службам IIS подключиться к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="351f8-140">This enables IIS to connect to the SQL Server instance.</span></span>  
  
13. <span data-ttu-id="351f8-141">После присоединения базы данных Northwind выполните следующие команды Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="351f8-141">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>  
  
    ```sql  
    USE Northwind  
    GO  
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]   
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];  
    GO  
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]   
    WITH DEFAULT_DATABASE=[Northwind];   
    GO  
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'  
    GO  
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'  
    GO   
    ```  
  
     <span data-ttu-id="351f8-142">Они предоставляют право на новое имя входа, позволяющее службам IIS читать данные из базы данных Northwind и записывать данные в эту базу данных.</span><span class="sxs-lookup"><span data-stu-id="351f8-142">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="351f8-143">Определение модели данных</span><span class="sxs-lookup"><span data-stu-id="351f8-143">To define the data model</span></span>  
  
1.  <span data-ttu-id="351f8-144">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавление нового элемента.**</span><span class="sxs-lookup"><span data-stu-id="351f8-144">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="351f8-145">В **Добавление нового элемента** выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="351f8-145">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="351f8-146">Введите имя модели данных, `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="351f8-146">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="351f8-147">В мастера модели EDM, выберите **создать из базы данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="351f8-147">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="351f8-148">Подключите модель данных в базу данных, выполнив одно из следующих действий и нажмите кнопку **Далее**:</span><span class="sxs-lookup"><span data-stu-id="351f8-148">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="351f8-149">Если нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="351f8-149">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="351f8-150">Дополнительные сведения см. в разделе [как: создание подключений к базам данных SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="351f8-150">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="351f8-151">Этот экземпляр [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] должен содержать присоединенный образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="351f8-151">This [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="351f8-152">\- или -</span><span class="sxs-lookup"><span data-stu-id="351f8-152">\- or -</span></span>  
  
    -   <span data-ttu-id="351f8-153">Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.</span><span class="sxs-lookup"><span data-stu-id="351f8-153">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="351f8-154">На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="351f8-154">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="351f8-155">Нажмите кнопку **Готово** для завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="351f8-155">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="351f8-156">Эта сформированная модель данных предоставляет свойства внешнего ключа для типов сущности.</span><span class="sxs-lookup"><span data-stu-id="351f8-156">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="351f8-157">Модели данных, созданные с помощью Visual Studio 2008, не включают эти свойства внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="351f8-157">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="351f8-158">В связи с этим перед получением доступа к этой версии службы данных Northwind необходимо обновить клиентские классы службы данных любого клиентского приложения для доступа к службе данных, созданного с помощью среды Visual Studio 2008.</span><span class="sxs-lookup"><span data-stu-id="351f8-158">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="351f8-159">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="351f8-159">To create the data service</span></span>  
  
1.  <span data-ttu-id="351f8-160">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="351f8-160">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="351f8-161">В **Добавление нового элемента** выберите **службы данных ADO.NET**.</span><span class="sxs-lookup"><span data-stu-id="351f8-161">In the **Add New Item** dialog box, select **ADO.NET Data Service**.</span></span>  
  
3.  <span data-ttu-id="351f8-162">Имя службы, введите `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="351f8-162">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="351f8-163">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="351f8-163">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="351f8-164">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="351f8-164">By default, the code-editor window opens.</span></span> <span data-ttu-id="351f8-165">В **обозревателе решений**, для службы будет отображаться имя Northwind с расширением. svc.cs или. svc.vb.</span><span class="sxs-lookup"><span data-stu-id="351f8-165">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="351f8-166">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="351f8-166">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="351f8-167">Определение класса должно выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="351f8-167">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a><span data-ttu-id="351f8-168">См. также</span><span class="sxs-lookup"><span data-stu-id="351f8-168">See Also</span></span>  
 [<span data-ttu-id="351f8-169">Предоставление данных как службы</span><span class="sxs-lookup"><span data-stu-id="351f8-169">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
