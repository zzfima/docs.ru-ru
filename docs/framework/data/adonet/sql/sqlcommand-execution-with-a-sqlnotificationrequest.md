---
title: "Выполнение SqlCommand с помощью SqlNotificationRequest | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Выполнение SqlCommand с помощью SqlNotificationRequest
Объект <xref:System.Data.SqlClient.SqlCommand> можно настроить таким образом, чтобы при изменении выбранных с сервера данных создавалось уведомление, когда результирующий набор повторного запроса будет отличаться от результирующего набора первого запроса.  Это полезно в сценариях, в которых нужно создать пользовательские очереди уведомлений или не требуется поддерживать активные объекты.  
  
## Создание уведомления о запросах  
 Объект <xref:System.Data.Sql.SqlNotificationRequest> можно использовать для создания уведомления о запросах, привязав его к объекту `SqlCommand`.  После создания запроса объект `SqlNotificationRequest` больше не требуется.  Очередь можно запрашивать на наличие уведомлений и реагировать соответствующим образом.  Уведомления создаются, даже если приложение закрывается и запускается повторно.  
  
 Если выполняется команда со связанным уведомлением, любые изменения в исходном результирующем наборе приводят к отправке сообщения в очередь SQL Server, указанной в запросе уведомления.  
  
 Опрос очереди SQL Server и интерпретация сообщения зависят от конкретного приложения.  За опрос очереди и реакцию, основанную на содержимом сообщения, отвечает приложение.  
  
> [!NOTE]
>  При использовании уведомления о запросах SQL Server вместе с объектом <xref:System.Data.SqlClient.SqlDependency> присвойте очереди собственное имя, а не используйте имя службы по умолчанию.  
  
 Для <xref:System.Data.Sql.SqlNotificationRequest> не существует новых клиентских элементов безопасности.  Это в основном функция сервера, который создает специальные права доступа, необходимые пользователю для запроса уведомления.  
  
### Пример  
 В приведенном ниже фрагменте кода демонстрируется создание объекта <xref:System.Data.Sql.SqlNotificationRequest> и его связь с объектом <xref:System.Data.Sql.SqlCommand>.  
  
```vb  
' Assume connection is an open SqlConnection.  
' Create a new SqlCommand object.  
Dim command As New SqlCommand( _  
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)  
  
' Create a SqlNotificationRequest object.  
Dim notficationRequest As New SqlNotificationRequest()  
notficationRequest.id = "NotificationID"  
notficationRequest.Service = "mySSBQueue"  
  
' Associate the notification request with the command.  
command.Notification = notficationRequest  
' Execute the command.  
command.ExecuteReader()  
' Process the DataReader.  
' You can use Transact-SQL syntax to periodically poll the   
' SQL Server queue to see if you have a new message.  
```  
  
```csharp  
// Assume connection is an open SqlConnection.  
// Create a new SqlCommand object.  
SqlCommand command=new SqlCommand(  
 "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection);  
  
// Create a SqlNotificationRequest object.  
SqlNotificationRequest notficationRequest=new SqlNotificationRequest();  
notficationRequest.id="NotificationID";  
notficationRequest.Service="mySSBQueue";  
  
// Associate the notification request with the command.  
command.Notification=notficationRequest;  
// Execute the command.  
command.ExecuteReader();  
// Process the DataReader.  
// You can use Transact-SQL syntax to periodically poll the   
// SQL Server queue to see if you have a new message.  
  
```  
  
## См. также  
 [Уведомления о запросах в SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)