---
title: Как разработать службу данных WCF Data Service, работающую на IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: af81e65dfd4661d62d7aa4a3e6075be312765cb7
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46531556"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="251a6-102">Практическое: разработке службы данных WCF, выполняющегося на сервере IIS</span><span class="sxs-lookup"><span data-stu-id="251a6-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="251a6-103">В этом разделе показано, как использовать службы данных WCF для создания службы данных, основанный на образце базы данных "Борей", которая размещена в веб-приложения ASP.NET, на котором выполняется на Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="251a6-103">This topic shows how to use WCF Data Services to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="251a6-104">Пример создания службы данных Northwind в качестве веб-приложения ASP.NET, выполняющегося на сервере разработки ASP.NET, см. в разделе [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="251a6-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="251a6-105">Для создания службы данных Northwind необходимо установить образец базы данных Northwind на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="251a6-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="251a6-106">Чтобы скачать этот образец базы данных, см. на странице загрузки [образцы баз данных для SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="251a6-106">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

 <span data-ttu-id="251a6-107">Данный раздел иллюстрирует создание службы данных с помощью поставщика Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="251a6-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="251a6-108">Доступны другие поставщики служб данных.</span><span class="sxs-lookup"><span data-stu-id="251a6-108">Other data services providers are available.</span></span> <span data-ttu-id="251a6-109">Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="251a6-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>

 <span data-ttu-id="251a6-110">После создания службы требуется явно предоставить доступ к ресурсам службы данных.</span><span class="sxs-lookup"><span data-stu-id="251a6-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="251a6-111">Дополнительные сведения см. в разделе [как: разрешить доступ к службе данных](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="251a6-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="251a6-112">Создание веб-приложение ASP.NET, который выполняется на IIS</span><span class="sxs-lookup"><span data-stu-id="251a6-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="251a6-113">В Visual Studio на **файл** меню, выберите **New** > **проекта**.</span><span class="sxs-lookup"><span data-stu-id="251a6-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="251a6-114">В **новый проект** выберите **установленные** > [**Visual C#** или **Visual Basic**] > **Web** категории.</span><span class="sxs-lookup"><span data-stu-id="251a6-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="251a6-115">Выберите **веб-приложение ASP.NET** шаблона.</span><span class="sxs-lookup"><span data-stu-id="251a6-115">Select the **ASP.NET Web Application** template.</span></span>

1. <span data-ttu-id="251a6-116">Введите `NorthwindService` как имя проекта.</span><span class="sxs-lookup"><span data-stu-id="251a6-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="251a6-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="251a6-117">Click **OK**.</span></span>

6. <span data-ttu-id="251a6-118">На **проекта** меню, выберите **свойства службы Northwind**.</span><span class="sxs-lookup"><span data-stu-id="251a6-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="251a6-119">Выберите **Web** , а затем выберите **использовать локальный веб-сервер IIS**.</span><span class="sxs-lookup"><span data-stu-id="251a6-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="251a6-120">Нажмите кнопку **создать виртуальный каталог** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="251a6-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="251a6-121">С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).</span><span class="sxs-lookup"><span data-stu-id="251a6-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    -   <span data-ttu-id="251a6-122">32-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="251a6-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    -   <span data-ttu-id="251a6-123">64-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="251a6-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="251a6-124">Она регистрирует Windows Communication Foundation (WCF) на компьютере.</span><span class="sxs-lookup"><span data-stu-id="251a6-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="251a6-125">С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).</span><span class="sxs-lookup"><span data-stu-id="251a6-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    -   <span data-ttu-id="251a6-126">32-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="251a6-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    -   <span data-ttu-id="251a6-127">64-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="251a6-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="251a6-128">Это необходимо для того, чтобы проверить правильность работы служб IIS после установки WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="251a6-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="251a6-129">Возможно, потребуется перезапустить службы IIS.</span><span class="sxs-lookup"><span data-stu-id="251a6-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="251a6-130">Если приложение ASP.NET запущено в службах IIS7, нужно также выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="251a6-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="251a6-131">Откройте диспетчер IIS и перейдите в приложение PhotoService на **веб-сайт по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="251a6-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="251a6-132">В **Просмотр возможностей**, дважды щелкните **проверки подлинности**.</span><span class="sxs-lookup"><span data-stu-id="251a6-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="251a6-133">На **проверки подлинности** выберите **анонимную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="251a6-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="251a6-134">В **действия** панели щелкните **изменить** Чтобы задать участника безопасности, в разделе которого анонимные пользователи будут подключаться к сайту.</span><span class="sxs-lookup"><span data-stu-id="251a6-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="251a6-135">В **изменение учетных данных анонимной проверки подлинности** выберите **удостоверение пула приложений**.</span><span class="sxs-lookup"><span data-stu-id="251a6-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="251a6-136">При использовании учетной записи сетевой службы анонимным пользователям предоставляется доступ к внутренней сети, связанной с этой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="251a6-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="251a6-137">С помощью среды SQL Server Management Studio, программы sqlcmd.exe или редактора Transact-SQL в Visual Studio выполните следующую команду Transact-SQL для экземпляра SQL Server с прикрепленной базой данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="251a6-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="251a6-138">Она создает имя входа в экземпляр SQL Server для учетной записи Windows, используемой для запуска служб IIS.</span><span class="sxs-lookup"><span data-stu-id="251a6-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="251a6-139">Это позволит службам IIS подключиться к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="251a6-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="251a6-140">После присоединения базы данных Northwind выполните следующие команды Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="251a6-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

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

    <span data-ttu-id="251a6-141">Они предоставляют право на новое имя входа, позволяющее службам IIS читать данные из базы данных Northwind и записывать данные в эту базу данных.</span><span class="sxs-lookup"><span data-stu-id="251a6-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="251a6-142">Определение модели данных</span><span class="sxs-lookup"><span data-stu-id="251a6-142">Define the data model</span></span>

1. <span data-ttu-id="251a6-143">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="251a6-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="251a6-144">В **Добавление нового элемента** выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="251a6-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="251a6-145">Введите имя модели данных, `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="251a6-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="251a6-146">В мастере модели EDM выберите **создать из базы данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="251a6-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="251a6-147">Подключите модель данных в базу данных, выполнив одно из следующих действий, а затем нажмите кнопку **Далее**:</span><span class="sxs-lookup"><span data-stu-id="251a6-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    -   <span data-ttu-id="251a6-148">Если у вас нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создайте новое соединение.</span><span class="sxs-lookup"><span data-stu-id="251a6-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="251a6-149">Дополнительные сведения см. в разделе [как: создание подключений к базам данных SQL Server](https://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="251a6-149">For more information, see [How to: Create Connections to SQL Server Databases](https://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="251a6-150">Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="251a6-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="251a6-151">\- или -</span><span class="sxs-lookup"><span data-stu-id="251a6-151">\- or -</span></span>

    -   <span data-ttu-id="251a6-152">Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.</span><span class="sxs-lookup"><span data-stu-id="251a6-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="251a6-153">На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="251a6-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="251a6-154">Нажмите кнопку **Готово** чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="251a6-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="251a6-155">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="251a6-155">Create the data service</span></span>

1. <span data-ttu-id="251a6-156">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="251a6-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="251a6-157">В **Добавление нового элемента** выберите **WCF-сервиса данных**.</span><span class="sxs-lookup"><span data-stu-id="251a6-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="251a6-159">**WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="251a6-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="251a6-160">Имя службы, введите `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="251a6-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="251a6-161">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="251a6-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="251a6-162">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="251a6-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="251a6-163">В **обозревателе решений**, служба имеет имя, Northwind и расширение. svc.cs или. svc.vb.</span><span class="sxs-lookup"><span data-stu-id="251a6-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="251a6-164">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="251a6-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="251a6-165">Определение класса должно выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="251a6-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="251a6-166">См. также</span><span class="sxs-lookup"><span data-stu-id="251a6-166">See also</span></span>

- [<span data-ttu-id="251a6-167">Предоставление данных как службы</span><span class="sxs-lookup"><span data-stu-id="251a6-167">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
