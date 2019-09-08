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
# <a name="sqldependency-in-an-aspnet-application"></a>SqlDependency в приложении ASP.NET
В примере этого раздела показано, как косвенно использовать <xref:System.Data.SqlClient.SqlDependency>, используя объект ASP.NET <xref:System.Web.Caching.SqlCacheDependency>. Объект <xref:System.Web.Caching.SqlCacheDependency> использует <xref:System.Data.SqlClient.SqlDependency> для прослушивания уведомлений и правильного обновления кэша.  
  
> [!NOTE]
> В примере кода предполагается, что вы включили уведомления о запросах, выполняя скрипты, [включив уведомления о запросах](enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>О примере приложения  
 Пример приложения использует одну веб-страницу ASP.NET для вывода сведений о продукте из базы данных **AdventureWorks** SQL Server в <xref:System.Web.UI.WebControls.GridView> элементе управления. При загрузке страницы код записывает текущее время в элемент управления <xref:System.Web.UI.WebControls.Label>. Затем он определяет объект <xref:System.Web.Caching.SqlCacheDependency> и устанавливает свойства на объекте <xref:System.Web.Caching.Cache> для хранения данных кэша до трех минут. Затем код выполняет подключение к базе данных и получает данные. После того, как страница загружена и приложение выполняется, ASP.NET получает данные из кэша. Это можно проверить, убедившись, что время на странице не меняется. Если наблюдаемые данные изменяются, ASP.NET делает кэш недействительным и вновь заполняет элемент управления `GridView` свежими данными, обновляя время, отображаемое в элементе управления `Label`.  
  
## <a name="creating-the-sample-application"></a>Создание примера приложения  
 Для создания и запуска примера приложения выполните следующие шаги.  
  
1. Создайте новый веб-узел ASP.NET.  
  
2. Добавьте элемент управления <xref:System.Web.UI.WebControls.Label> и <xref:System.Web.UI.WebControls.GridView> на страницу Default.aspx.  
  
3. Откройте модуль класса страницы и добавить следующие директивы:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. Добавьте следующий код в событие `Page_Load` страницы:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. Добавьте два вспомогательных метода, `GetConnectionString` и `GetSQL`. В заданной строке соединения используется интегрированная безопасность. Необходимо убедиться, что используемая учетная запись имеет необходимые разрешения базы данных и что образец базы данных, **AdventureWorks**, включает уведомления.
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Тестирование приложения  
 Приложение кэширует данные, отображаемые на веб-форме, и обновляет их каждые три минуты, если нет никаких действий. Если в базе данных происходит изменение, кэш немедленно обновляется. Запустите приложение из среды Visual Studio, которая загружает страницу в браузер. Отображаемое время обновления кэша указывает, когда кэш обновлялся в последний раз. Подождите три минуты, после чего обновите страницу, в результате чего возникнет событие запроса к серверу. Отметим, что время, отображаемое на странице, изменилось. Если обновить страницу раньше, чем через три минуты, время, отображаемое на странице, останется тем же.  
  
 Теперь обновите данные в базе данных с помощью команды Transact-SQL UPDATE, после чего обновите страницу. Отображаемое время теперь указывает, что кэш был обновлен новыми данными из базы данных. Отметим, что хотя кэш обновлен, время, отображаемое на странице, не изменяется, пока не возникнет событие запроса к серверу.  
  
## <a name="see-also"></a>См. также

- [Уведомления запросов в SQL Server](query-notifications-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
