---
title: "SqlDependency в приложении ASP.NET (ADO.NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# SqlDependency в приложении ASP.NET (ADO.NET)
В примере этого раздела показано, как косвенно использовать <xref:System.Data.SqlClient.SqlDependency>, используя объект ASP.NET <xref:System.Web.Caching.SqlCacheDependency>.  Объект <xref:System.Web.Caching.SqlCacheDependency> использует <xref:System.Data.SqlClient.SqlDependency> для прослушивания уведомлений и правильного обновления кэша.  
  
> [!NOTE]
>  В образце кода предполагается, что включены уведомления о запросах путем выполнения скриптов из раздела [Включение уведомлений о запросах](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).  
  
## О примере приложения  
 В примере приложения используется одна веб\-страница ASP.NET для вывода сведений о продуктах из базы данных **AdventureWorks** SQL Server в элемент управления <xref:System.Web.UI.WebControls.GridView>.  При загрузке страницы код записывает текущее время в элемент управления <xref:System.Web.UI.WebControls.Label>.  Затем он определяет объект <xref:System.Web.Caching.SqlCacheDependency> и устанавливает свойства на объекте <xref:System.Web.Caching.Cache> для хранения данных кэша до трех минут.  Затем код выполняет подключение к базе данных и получает данные.  После того, как страница загружена и приложение выполняется, ASP.NET получает данные из кэша. Это можно проверить, убедившись, что время на странице не меняется.  Если наблюдаемые данные изменяются, ASP.NET делает кэш недействительным и вновь заполняет элемент управления `GridView` свежими данными, обновляя время, отображаемое в элементе управления `Label`.  
  
## Создание примера приложения  
 Для создания и запуска примера приложения выполните следующие шаги.  
  
1.  Создайте новый веб\-узел ASP.NET.  
  
2.  Добавьте элемент управления <xref:System.Web.UI.WebControls.Label> и <xref:System.Web.UI.WebControls.GridView> на страницу Default.aspx.  
  
3.  Откройте модуль класса страницы и добавить следующие директивы:  
  
    ```vb  
  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  Добавьте следующий код в событие `Page_Load` страницы:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  Добавьте два вспомогательных метода, `GetConnectionString` и `GetSQL`.  В заданной строке соединения используется интегрированная безопасность.  Необходимо будет убедиться, что используемая учетная запись обладает необходимыми разрешениями для базы данных, а в образце базы данных **AdventureWorks** включены уведомления.  Для получения дополнительной информации см. [Special Considerations When Using Query Notifications](http://msdn.microsoft.com/ru-ru/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### Тестирование приложения  
 Приложение кэширует данные, отображаемые на веб\-форме, и обновляет их каждые три минуты, если нет никаких действий.  Если в базе данных происходит изменение, кэш немедленно обновляется.  Запустите приложение из среды Visual Studio, которая загружает страницу в браузер.  Отображаемое время обновления кэша указывает, когда кэш обновлялся в последний раз.  Подождите три минуты, после чего обновите страницу, в результате чего возникнет событие запроса к серверу.  Отметим, что время, отображаемое на странице, изменилось.  Если обновить страницу раньше, чем через три минуты, время, отображаемое на странице, останется тем же.  
  
 Теперь обновите данные в базе данных с помощью команды Transact\-SQL UPDATE, после чего обновите страницу.  Отображаемое время теперь указывает, что кэш был обновлен новыми данными из базы данных.  Отметим, что хотя кэш обновлен, время, отображаемое на странице, не изменяется, пока не возникнет событие запроса к серверу.  
  
## См. также  
 [Уведомления о запросах в SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)