---
title: SqlDependency в приложении ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: f3e28adc2cf7c24cee9ee344eb78404f01b79793
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780720"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="d7d24-102">SqlDependency в приложении ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d7d24-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="d7d24-103">В примере этого раздела показано, как косвенно использовать <xref:System.Data.SqlClient.SqlDependency>, используя объект ASP.NET <xref:System.Web.Caching.SqlCacheDependency>.</span><span class="sxs-lookup"><span data-stu-id="d7d24-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="d7d24-104">Объект <xref:System.Web.Caching.SqlCacheDependency> использует <xref:System.Data.SqlClient.SqlDependency> для прослушивания уведомлений и правильного обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="d7d24-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7d24-105">В примере кода предполагается, что вы включили уведомления о запросах, выполняя скрипты, [включив уведомления о запросах](enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="d7d24-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="d7d24-106">О примере приложения</span><span class="sxs-lookup"><span data-stu-id="d7d24-106">About the Sample Application</span></span>  
 <span data-ttu-id="d7d24-107">Пример приложения использует одну веб-страницу ASP.NET для вывода сведений о продукте из базы данных **AdventureWorks** SQL Server в <xref:System.Web.UI.WebControls.GridView> элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d7d24-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="d7d24-108">При загрузке страницы код записывает текущее время в элемент управления <xref:System.Web.UI.WebControls.Label>.</span><span class="sxs-lookup"><span data-stu-id="d7d24-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="d7d24-109">Затем он определяет объект <xref:System.Web.Caching.SqlCacheDependency> и устанавливает свойства на объекте <xref:System.Web.Caching.Cache> для хранения данных кэша до трех минут.</span><span class="sxs-lookup"><span data-stu-id="d7d24-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="d7d24-110">Затем код выполняет подключение к базе данных и получает данные.</span><span class="sxs-lookup"><span data-stu-id="d7d24-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="d7d24-111">После того, как страница загружена и приложение выполняется, ASP.NET получает данные из кэша. Это можно проверить, убедившись, что время на странице не меняется.</span><span class="sxs-lookup"><span data-stu-id="d7d24-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="d7d24-112">Если наблюдаемые данные изменяются, ASP.NET делает кэш недействительным и вновь заполняет элемент управления `GridView` свежими данными, обновляя время, отображаемое в элементе управления `Label`.</span><span class="sxs-lookup"><span data-stu-id="d7d24-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="d7d24-113">Создание примера приложения</span><span class="sxs-lookup"><span data-stu-id="d7d24-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="d7d24-114">Для создания и запуска примера приложения выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="d7d24-114">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="d7d24-115">Создайте новый веб-узел ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7d24-115">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="d7d24-116">Добавьте элемент управления <xref:System.Web.UI.WebControls.Label> и <xref:System.Web.UI.WebControls.GridView> на страницу Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="d7d24-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="d7d24-117">Откройте модуль класса страницы и добавить следующие директивы:</span><span class="sxs-lookup"><span data-stu-id="d7d24-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="d7d24-118">Добавьте следующий код в событие `Page_Load` страницы:</span><span class="sxs-lookup"><span data-stu-id="d7d24-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="d7d24-119">Добавьте два вспомогательных метода, `GetConnectionString` и `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="d7d24-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="d7d24-120">В заданной строке соединения используется интегрированная безопасность.</span><span class="sxs-lookup"><span data-stu-id="d7d24-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="d7d24-121">Необходимо убедиться, что используемая учетная запись имеет необходимые разрешения базы данных и что образец базы данных, **AdventureWorks**, включает уведомления.</span><span class="sxs-lookup"><span data-stu-id="d7d24-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="d7d24-122">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="d7d24-122">Testing the Application</span></span>  
 <span data-ttu-id="d7d24-123">Приложение кэширует данные, отображаемые на веб-форме, и обновляет их каждые три минуты, если нет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="d7d24-123">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="d7d24-124">Если в базе данных происходит изменение, кэш немедленно обновляется.</span><span class="sxs-lookup"><span data-stu-id="d7d24-124">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="d7d24-125">Запустите приложение из среды Visual Studio, которая загружает страницу в браузер.</span><span class="sxs-lookup"><span data-stu-id="d7d24-125">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="d7d24-126">Отображаемое время обновления кэша указывает, когда кэш обновлялся в последний раз.</span><span class="sxs-lookup"><span data-stu-id="d7d24-126">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="d7d24-127">Подождите три минуты, после чего обновите страницу, в результате чего возникнет событие запроса к серверу.</span><span class="sxs-lookup"><span data-stu-id="d7d24-127">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="d7d24-128">Отметим, что время, отображаемое на странице, изменилось.</span><span class="sxs-lookup"><span data-stu-id="d7d24-128">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="d7d24-129">Если обновить страницу раньше, чем через три минуты, время, отображаемое на странице, останется тем же.</span><span class="sxs-lookup"><span data-stu-id="d7d24-129">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="d7d24-130">Теперь обновите данные в базе данных с помощью команды Transact-SQL UPDATE, после чего обновите страницу.</span><span class="sxs-lookup"><span data-stu-id="d7d24-130">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="d7d24-131">Отображаемое время теперь указывает, что кэш был обновлен новыми данными из базы данных.</span><span class="sxs-lookup"><span data-stu-id="d7d24-131">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="d7d24-132">Отметим, что хотя кэш обновлен, время, отображаемое на странице, не изменяется, пока не возникнет событие запроса к серверу.</span><span class="sxs-lookup"><span data-stu-id="d7d24-132">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d24-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d7d24-133">See also</span></span>

- [<span data-ttu-id="d7d24-134">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7d24-134">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="d7d24-135">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7d24-135">ADO.NET Overview</span></span>](../ado-net-overview.md)
