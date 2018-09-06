---
title: SqlDependency в приложении ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 5465238e4b9deaa13c76cb35122fcaded7acd7f7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864843"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="2291b-102">SqlDependency в приложении ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2291b-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="2291b-103">В примере этого раздела показано, как косвенно использовать <xref:System.Data.SqlClient.SqlDependency>, используя объект ASP.NET <xref:System.Web.Caching.SqlCacheDependency>.</span><span class="sxs-lookup"><span data-stu-id="2291b-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="2291b-104">Объект <xref:System.Web.Caching.SqlCacheDependency> использует <xref:System.Data.SqlClient.SqlDependency> для прослушивания уведомлений и правильного обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="2291b-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2291b-105">Образец кода предполагает, что вы включили уведомления о запросах путем выполнения скриптов в [Включение уведомлений о запросах](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="2291b-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="2291b-106">О примере приложения</span><span class="sxs-lookup"><span data-stu-id="2291b-106">About the Sample Application</span></span>  
 <span data-ttu-id="2291b-107">Пример приложения использует одной страницы ASP.NET для отображения сведений о продукте из **AdventureWorks** базы данных SQL Server в <xref:System.Web.UI.WebControls.GridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2291b-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="2291b-108">При загрузке страницы код записывает текущее время в элемент управления <xref:System.Web.UI.WebControls.Label>.</span><span class="sxs-lookup"><span data-stu-id="2291b-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="2291b-109">Затем он определяет объект <xref:System.Web.Caching.SqlCacheDependency> и устанавливает свойства на объекте <xref:System.Web.Caching.Cache> для хранения данных кэша до трех минут.</span><span class="sxs-lookup"><span data-stu-id="2291b-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="2291b-110">Затем код выполняет подключение к базе данных и получает данные.</span><span class="sxs-lookup"><span data-stu-id="2291b-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="2291b-111">После того, как страница загружена и приложение выполняется, ASP.NET получает данные из кэша. Это можно проверить, убедившись, что время на странице не меняется.</span><span class="sxs-lookup"><span data-stu-id="2291b-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="2291b-112">Если наблюдаемые данные изменяются, ASP.NET делает кэш недействительным и вновь заполняет элемент управления `GridView` свежими данными, обновляя время, отображаемое в элементе управления `Label`.</span><span class="sxs-lookup"><span data-stu-id="2291b-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="2291b-113">Создание примера приложения</span><span class="sxs-lookup"><span data-stu-id="2291b-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="2291b-114">Для создания и запуска примера приложения выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="2291b-114">Follow these steps to create and run the sample application:</span></span>  
  
1.  <span data-ttu-id="2291b-115">Создайте новый веб-узел ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2291b-115">Create a new ASP.NET Web site.</span></span>  
  
2.  <span data-ttu-id="2291b-116">Добавьте элемент управления <xref:System.Web.UI.WebControls.Label> и <xref:System.Web.UI.WebControls.GridView> на страницу Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="2291b-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3.  <span data-ttu-id="2291b-117">Откройте модуль класса страницы и добавить следующие директивы:</span><span class="sxs-lookup"><span data-stu-id="2291b-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  <span data-ttu-id="2291b-118">Добавьте следующий код в событие `Page_Load` страницы:</span><span class="sxs-lookup"><span data-stu-id="2291b-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  <span data-ttu-id="2291b-119">Добавьте два вспомогательных метода, `GetConnectionString` и `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="2291b-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="2291b-120">В заданной строке соединения используется интегрированная безопасность.</span><span class="sxs-lookup"><span data-stu-id="2291b-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="2291b-121">Необходимо будет проверить наличие необходимых разрешений базы данных и что учетной записи, используемой базе данных, **AdventureWorks**, включены уведомления.</span><span class="sxs-lookup"><span data-stu-id="2291b-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span> <span data-ttu-id="2291b-122">Дополнительные сведения см. в разделе [особые соображения при с помощью уведомлений о запросах](https://msdn.microsoft.com/library/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).</span><span class="sxs-lookup"><span data-stu-id="2291b-122">For more information, see [Special Considerations When Using Query Notifications](https://msdn.microsoft.com/library/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="2291b-123">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="2291b-123">Testing the Application</span></span>  
 <span data-ttu-id="2291b-124">Приложение кэширует данные, отображаемые на веб-форме, и обновляет их каждые три минуты, если нет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2291b-124">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="2291b-125">Если в базе данных происходит изменение, кэш немедленно обновляется.</span><span class="sxs-lookup"><span data-stu-id="2291b-125">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="2291b-126">Запустите приложение из среды Visual Studio, которая загружает страницу в браузер.</span><span class="sxs-lookup"><span data-stu-id="2291b-126">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="2291b-127">Отображаемое время обновления кэша указывает, когда кэш обновлялся в последний раз.</span><span class="sxs-lookup"><span data-stu-id="2291b-127">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="2291b-128">Подождите три минуты, после чего обновите страницу, в результате чего возникнет событие запроса к серверу.</span><span class="sxs-lookup"><span data-stu-id="2291b-128">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="2291b-129">Отметим, что время, отображаемое на странице, изменилось.</span><span class="sxs-lookup"><span data-stu-id="2291b-129">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="2291b-130">Если обновить страницу раньше, чем через три минуты, время, отображаемое на странице, останется тем же.</span><span class="sxs-lookup"><span data-stu-id="2291b-130">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="2291b-131">Теперь обновите данные в базе данных с помощью команды Transact-SQL UPDATE, после чего обновите страницу.</span><span class="sxs-lookup"><span data-stu-id="2291b-131">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="2291b-132">Отображаемое время теперь указывает, что кэш был обновлен новыми данными из базы данных.</span><span class="sxs-lookup"><span data-stu-id="2291b-132">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="2291b-133">Отметим, что хотя кэш обновлен, время, отображаемое на странице, не изменяется, пока не возникнет событие запроса к серверу.</span><span class="sxs-lookup"><span data-stu-id="2291b-133">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2291b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2291b-134">See Also</span></span>  
 [<span data-ttu-id="2291b-135">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="2291b-135">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="2291b-136">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2291b-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
