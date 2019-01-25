---
title: Как выполнить Создание службы данных с использованием LINQ к источнику данных SQL (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 7447a9f2ab0b2a9cca396ee947a0eb5fe2cc8715
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608577"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a><span data-ttu-id="45322-102">Как выполнить Создание службы данных с использованием LINQ к источнику данных SQL (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="45322-102">How to: Create a Data Service Using a LINQ to SQL Data Source (WCF Data Services)</span></span>

<span data-ttu-id="45322-103">Службы данных WCF предоставляет данные сущности в виде службы данных.</span><span class="sxs-lookup"><span data-stu-id="45322-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="45322-104">Поставщик отражения позволяет определить модель данных, основанный на любой класс, который предоставляет члены, которые возвращают <xref:System.Linq.IQueryable%601> реализации.</span><span class="sxs-lookup"><span data-stu-id="45322-104">The reflection provider enables you to define a data model that is based on any class that exposes members that return an <xref:System.Linq.IQueryable%601> implementation.</span></span> <span data-ttu-id="45322-105">Для выполнения обновлений данных в источнике данных эти классы должны также реализовать интерфейс <xref:System.Data.Services.IUpdatable>.</span><span class="sxs-lookup"><span data-stu-id="45322-105">To be able to make updates to data in the data source, these classes must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="45322-106">Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="45322-106">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span> <span data-ttu-id="45322-107">В этом разделе показано, как создать классы LINQ to SQL, обращающиеся к образцу базы данных Northwind с помощью поставщика, а также как создать службу данных на основе этих классов.</span><span class="sxs-lookup"><span data-stu-id="45322-107">This topic shows you how to create LINQ to SQL classes that access the Northwind sample database by using the reflection provider, as well as how to create the data service that is based on these data classes.</span></span>

## <a name="to-add-linq-to-sql-classes-to-a-project"></a><span data-ttu-id="45322-108">Добавление в проект объектов классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="45322-108">To add LINQ to SQL classes to a project</span></span>

1. <span data-ttu-id="45322-109">Из приложения Visual Basic или C#, на **проекта** меню, щелкните **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="45322-109">From within a Visual Basic or C# application, on the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="45322-110">Нажмите кнопку **LINQ to SQL Classes** шаблона.</span><span class="sxs-lookup"><span data-stu-id="45322-110">Click the **LINQ to SQL Classes** template.</span></span>

3. <span data-ttu-id="45322-111">Измените имя на **Northwind.dbml**.</span><span class="sxs-lookup"><span data-stu-id="45322-111">Change the name to **Northwind.dbml**.</span></span>

4. <span data-ttu-id="45322-112">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="45322-112">Click **Add**.</span></span>

     <span data-ttu-id="45322-113">Файл Northwind.dbml добавляется в проект и открывается реляционный конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="45322-113">The Northwind.dbml file is added to the project and the Object Relational Designer (O/R Designer) opens.</span></span>

5. <span data-ttu-id="45322-114">В **Server**/**обозреватель баз данных**, в окне Northwind разверните **таблиц** и перетащите `Customers` таблицы на реляционный конструктор объектов (O/R Конструктор).</span><span class="sxs-lookup"><span data-stu-id="45322-114">In **Server**/**Database Explorer**, under Northwind, expand **Tables** and drag the `Customers` table onto the Object Relational Designer (O/R Designer).</span></span>

     <span data-ttu-id="45322-115">При этом в области конструктора создается и отображается класс сущностей `Customer`.</span><span class="sxs-lookup"><span data-stu-id="45322-115">A `Customer` entity class is created and appears on the design surface.</span></span>

6. <span data-ttu-id="45322-116">Повторите шаг 6 для таблиц `Orders`, `Order_Details` и `Products`.</span><span class="sxs-lookup"><span data-stu-id="45322-116">Repeat step 6 for the `Orders`, `Order_Details`, and `Products` tables.</span></span>

7. <span data-ttu-id="45322-117">Щелкните правой кнопкой мыши новый DBML-файл, представляющий LINQ к классам SQL и нажмите кнопку **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="45322-117">Right-click the new .dbml file that represents the LINQ to SQL classes and click **View Code**.</span></span>

     <span data-ttu-id="45322-118">При этом создается новая страница с выделенным кодом Northwind.cs, содержащая разделяемый класс, производный от класса <xref:System.Data.Linq.DataContext>, представляющего в данном случае контекст `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="45322-118">This creates a new code-behind page named Northwind.cs that contains a partial class definition for the class that inherits from the <xref:System.Data.Linq.DataContext> class, which in this case is `NorthwindDataContext`.</span></span>

8. <span data-ttu-id="45322-119">Замените содержимое файла Northwind.cs следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="45322-119">Replace the contents of the Northwind.cs code file with the following code.</span></span> <span data-ttu-id="45322-120">Этот код реализует поставщик отражения, расширяя контекст <xref:System.Data.Linq.DataContext> и классы данных, сформированные LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="45322-120">This code implements the reflection provider by extending the <xref:System.Data.Linq.DataContext> and data classes generated by LINQ to SQL:</span></span>

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a><span data-ttu-id="45322-121">Создание службы данных с использованием модели данных на основе LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="45322-121">To create a data service by using a LINQ to SQL-based data model</span></span>

1. <span data-ttu-id="45322-122">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="45322-122">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="45322-123">В **Добавление нового элемента** выберите **WCF-сервиса данных** шаблон из **Web** категории.</span><span class="sxs-lookup"><span data-stu-id="45322-123">In the **Add New Item** dialog box, select the **WCF Data Service** template from the **Web** category.</span></span>

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="45322-125">**WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="45322-125">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="45322-126">Укажите имя для службы и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="45322-126">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="45322-127">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="45322-127">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="45322-128">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="45322-128">By default, the code-editor window opens.</span></span>

4. <span data-ttu-id="45322-129">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="45322-129">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindDataContext`.</span></span>

5. <span data-ttu-id="45322-130">В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="45322-130">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]

     <span data-ttu-id="45322-131">Это позволяет авторизованным клиентам осуществлять доступ к ресурсам трех указанных наборов сущностей.</span><span class="sxs-lookup"><span data-stu-id="45322-131">This enables authorized clients to access resources for the three specified entity sets.</span></span>

6. <span data-ttu-id="45322-132">Чтобы проверить службы данных Northwind.svc с помощью веб-браузер, следуйте инструкциям в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="45322-132">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45322-133">См. также</span><span class="sxs-lookup"><span data-stu-id="45322-133">See also</span></span>

- [<span data-ttu-id="45322-134">Практическое руководство. Создание службы данных с использованием источника данных ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="45322-134">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [<span data-ttu-id="45322-135">Практическое руководство. Создание службы данных с помощью поставщика отражения</span><span class="sxs-lookup"><span data-stu-id="45322-135">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="45322-136">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="45322-136">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)