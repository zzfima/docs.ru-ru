---
title: "Использование служб данных в клиентском приложении (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 79c4f7e066f4961caa66d3fd19dee9eb0f21ada4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Использование служб данных в клиентском приложении (службы данных WCF)
Можно получить доступ к службу, предоставляющую [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала, указав URI в веб-браузере. URI предоставляет адрес ресурса, и сообщения запроса отправляются по этим адресам для доступа или изменения базовых данных, представляемых ресурсом. Браузер формирует команду HTTP GET и возвращает запрошенный ресурс в виде канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Дополнительные сведения см. в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Хотя веб-браузер может быть полезен для проверки того, что служба [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] возвращает ожидаемые данные, доступ к производственным службам [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], позволяющим создавать, обновлять и удалять данные, обычно осуществляется из кода приложения или языков создания скриптов на веб-странице. Этот раздел содержит общие сведения о доступе к [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналов из клиентского приложения.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Доступ и изменение данных с помощью семантики REST  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]помогают осуществлять взаимодействие служб, предоставляющих [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналов и приложений, использующих [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналов. Приложения обращаются и изменяют данные в [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-служба на основе, отправляя сообщения запросов конкретного действия HTTP и с URI, Адресующим ресурс сущности, для которого следует выполнить действие. Если необходимо передать данные сущности, они передаются в специально закодированных полезных данных в тексте сообщения.  
  
### <a name="http-actions"></a>Действия HTTP  
 Службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] поддерживают следующие действия HTTP для создания, чтения, обновления и удаления данных сущностей, представленных адресуемыми ресурсами.  
  
-   **HTTP GET** -это действие по умолчанию при доступе к ресурсу из браузера. Сообщение запроса не содержит полезных данных, а возвращается метод ответа с полезными данными, содержащими запрошенные данные.  
  
-   **HTTP POST** -вставляет данные новой сущности в переданный ресурс. Вставляемые данные передаются в виде полезных данных сообщения запроса. Полезные данные ответного сообщения содержат данные созданной сущности. К ним относятся все ключевые значения, формируемые автоматически. Заголовок содержит также URI, адресующий ресурс новой сущности.  
  
-   **HTTP DELETE** -удаляет данные сущности, представленной указанным ресурсом. Полезные данные в сообщениях запроса и ответа отсутствуют.  
  
-   **HTTP PUT** — заменяет существующие данные сущности в запрошенном ресурсе новыми данными, введенные в полезные данные сообщения запроса.  
  
-   **HTTP MERGE** — в связи с неэффективностью выполнения удаления, а затем вставки в источник данных только для изменения данных сущности [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] представляют новое действие HTTP MERGE. Полезные данные сообщения запроса содержат свойства, которые необходимо изменить в адресуемом ресурсе сущности. Поскольку метод HTTP MERGE не определен в спецификации HTTP, ему может потребоваться дополнительная обработка для отправки запроса HTTP MERGE через серверы, не поддерживающие службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 Дополнительные сведения см. в разделе [OData: операции](http://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Форматы представления информации  
 Для запросов HTTP PUT, HTTP POST или HTTP MERGE полезные данные сообщения запроса содержат данные сущности, отправляемые службе данных. Содержимое полезных данных зависит от формата данных сообщения. Ответы HTTP на все действия, кроме DELETE, также содержат полезные данные. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]поддерживает следующие форматы полезных данных для доступа и изменения данных с использованием службы:  
  
-   **Atom** -Кодировка сообщений на основе XML, определяемые [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] как расширение протокола публикации Atom (AtomPub) для поддержки обмена данными по протоколу HTTP для веб-каналов, подкастов, вики и функций Интернета на основе XML. Дополнительные сведения см. в разделе [OData: формат Atom](http://go.microsoft.com/fwlink/?LinkId=185794).  
  
-   **JSON** -JavaScript Object Notation (JSON) является облегченный формат обмена данными, основанный на подмножество языка программирования JavaScript. Дополнительные сведения см. в разделе [OData: формат JSON](http://go.microsoft.com/fwlink/?LinkId=185795).  
  
 Формат сообщения полезных данных запрашивается в заголовке HTTP-запроса. Дополнительные сведения см. в разделе [OData: операции](http://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Доступ и изменения данных с помощью клиентских библиотек  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]включает в себя клиентские библиотеки, позволяющие легко использовать [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] канала из .NET Framework и приложений на базе Silverlight. Эти библиотеки упрощают отправку и получение сообщений HTTP. Кроме того, они преобразуют полезные данные сообщений в объекты CLR, представляющие данные сущностей. Клиентские библиотеки содержат два базовых класса: <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601>. Эти классы позволяют отправлять запросы к службе данных и работать с возвращенными данными сущностей как с объектами CLR. Дополнительные сведения см. в разделе [клиентскую библиотеку служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) и [WCF Data Services (Silverlight)](http://msdn.microsoft.com/en-us/c0cd9f4b-1372-48e4-9935-c8421239da30).  
  
 Можно использовать **добавить ссылку на службу** диалоговое окно в Visual Studio для добавления ссылки на службу данных. Эта программа запрашивает метаданные службы у упомянутой службы данных и формирует контекст <xref:System.Data.Services.Client.DataServiceContext>, который представляет службу данных, а также клиентские классы службы данных, которые представляют сущности. Дополнительные сведения см. в разделе [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
 Существуют программные библиотеки, которые используются для получения [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала в клиентских приложениях других видов. Дополнительные сведения см. в разделе [OData SDK](http://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>См. также  
 [Доступ к ресурсам службы данных](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
