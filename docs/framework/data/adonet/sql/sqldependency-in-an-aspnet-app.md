---
title: SqlDependency в приложении ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 51df8ad695b3e59b368499d35ac76cc7ac0cd6e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sqldependency-in-an-aspnet-application"></a>SqlDependency в приложении ASP.NET
В примере этого раздела показано, как косвенно использовать <xref:System.Data.SqlClient.SqlDependency>, используя объект ASP.NET <xref:System.Web.Caching.SqlCacheDependency>. Объект <xref:System.Web.Caching.SqlCacheDependency> использует <xref:System.Data.SqlClient.SqlDependency> для прослушивания уведомлений и правильного обновления кэша.  
  
> [!NOTE]
>  Образец кода предполагает включены уведомления о запросах, выполнив скрипты в [Включение уведомлений о запросах](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>О примере приложения  
 В примере приложения используется одной страницы ASP.NET, чтобы отобразить сведения о продукте из **AdventureWorks** базы данных SQL Server в <xref:System.Web.UI.WebControls.GridView> элемента управления. При загрузке страницы код записывает текущее время в элемент управления <xref:System.Web.UI.WebControls.Label>. Затем он определяет объект <xref:System.Web.Caching.SqlCacheDependency> и устанавливает свойства на объекте <xref:System.Web.Caching.Cache> для хранения данных кэша до трех минут. Затем код выполняет подключение к базе данных и получает данные. После того, как страница загружена и приложение выполняется, ASP.NET получает данные из кэша. Это можно проверить, убедившись, что время на странице не меняется. Если наблюдаемые данные изменяются, ASP.NET делает кэш недействительным и вновь заполняет элемент управления `GridView` свежими данными, обновляя время, отображаемое в элементе управления `Label`.  
  
## <a name="creating-the-sample-application"></a>Создание примера приложения  
 Для создания и запуска примера приложения выполните следующие шаги.  
  
1.  Создайте новый веб-узел ASP.NET.  
  
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
  
5.  Добавьте два вспомогательных метода, `GetConnectionString` и `GetSQL`. В заданной строке соединения используется интегрированная безопасность. Вам потребуется Проверьте наличие необходимых разрешений базы данных и что учетной записи, используется образец базы данных **AdventureWorks**, включены уведомления. Дополнительные сведения см. в разделе [специальные рекомендации при с помощью уведомлений о запросах](http://msdn.microsoft.com/library/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Тестирование приложения  
 Приложение кэширует данные, отображаемые на веб-форме, и обновляет их каждые три минуты, если нет никаких действий. Если в базе данных происходит изменение, кэш немедленно обновляется. Запустите приложение из среды Visual Studio, которая загружает страницу в браузер. Отображаемое время обновления кэша указывает, когда кэш обновлялся в последний раз. Подождите три минуты, после чего обновите страницу, в результате чего возникнет событие запроса к серверу. Отметим, что время, отображаемое на странице, изменилось. Если обновить страницу раньше, чем через три минуты, время, отображаемое на странице, останется тем же.  
  
 Теперь обновите данные в базе данных с помощью команды Transact-SQL UPDATE, после чего обновите страницу. Отображаемое время теперь указывает, что кэш был обновлен новыми данными из базы данных. Отметим, что хотя кэш обновлен, время, отображаемое на странице, не изменяется, пока не возникнет событие запроса к серверу.  
  
## <a name="see-also"></a>См. также  
 [Уведомления запросов в SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
