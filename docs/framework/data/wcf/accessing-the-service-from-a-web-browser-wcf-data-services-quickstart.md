---
title: "Доступ к службе из веб-браузера (краткое руководство по службе данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49deb2e209127f92a333195e9fcd0d1e1bece7d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a>Доступ к службе из веб-браузера (краткое руководство по службе данных WCF)
В этой задаче необходимо запустить [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] из [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] и отключить чтение потока в веб-браузере. Вам будет затем извлечем документ определения службы а также доступ к ресурсам службы данных, отправляя запросы HTTP GET через веб-браузер к предоставляемым ресурсам.  
  
> [!NOTE]
>  По умолчанию [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] автоматически задает номер порта URI `localhost` на локальном компьютере. В данной задаче в примерах URI используется порт номер `12345`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]как задать конкретный номер порта вашей [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] проекта см. в разделе [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a>Запрос сервисного документа по умолчанию с помощью Internet Explorer  
  
1.  В Internet Explorer из **средства** последовательно выберите пункты **обозревателя**, нажмите кнопку **содержимого** щелкните **параметры**и снимите  **Включение просмотра веб-канала**.  
  
     При этом чтение каналов будет отключено. Если не выключить эту функцию, то веб-браузер будет рассматривать документ в формате AtomPub в качестве канала XML, а не отображать необработанные данные XML.  
  
    > [!NOTE]
    >  Если браузер не может отобразить канал в виде необработанных XML-данных, его все равно можно просмотреть в виде исходного кода страницы.  
  
2.  В [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] нажмите клавишу F5 для запуска отладки приложения.  
  
3.  Откройте веб-браузер на локальном компьютере. В адресной строке введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     При этом будет возвращен сервисный документ по умолчанию, в котором содержится список наборов сущностей, предоставляемых службой данных.  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a>Доступ к ресурсам набора сущностей из веб-браузера  
  
1.  В адресной строке веб-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     При этом будет возвращен набор всех клиентов из образца базы данных Northwind.  
  
2.  В адресной строке веб-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     При этом возвращается экземпляр сущности для конкретного клиента `ALFKI`.  
  
3.  В адресной строке веб-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     При этом произойдет переход по связи между клиентами и заказами для возвращения набора всех заказов для конкретного клиента `ALFKI`.  
  
4.  В адресной строке веб-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     При этом будут отфильтрованы заказы, принадлежащие конкретному клиенту `ALFKI`, в результате чего будет возвращен только конкретный заказ на основе переданного значения `OrderID`.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Итак, мы успешно обратились к службам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] из веб-браузера, отправляя через браузер запросы HTTP GET к указанным ресурсам. Веб-браузер предоставляет простой способ проведения экспериментов с синтаксисом адресации запросов и просмотра результатов. Однако к производственной службе данных таким способом обычно не обращаются. Как правило, взаимодействие приложений со службой данных осуществляется через программный код или языки сценариев. Далее мы создадим клиентское приложение, которое использует клиентские библиотеки для обращения к ресурсам службы данных, как если бы они являлись объектами CLR.  
  
 [Создание клиентского приложения .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>См. также  
 [Доступ к ресурсам службы данных](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
