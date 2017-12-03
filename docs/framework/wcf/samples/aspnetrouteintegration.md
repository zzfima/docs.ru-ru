---
title: AspNetRouteIntegration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a942a26ad239233f13ee8791d1178fb47573e710
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="aspnetrouteintegration"></a>AspNetRouteIntegration
Этот образец демонстрирует размещение службы REST [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с помощью маршрутов ASP.NET. [Базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образца показано резидентной версию этого сценария и обсуждается реализация service в глубину. В этом разделе основное внимание уделено возможности интеграции с ASP.NET. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] о маршрутизации ASP.NET см. в разделе <xref:System.Web.Routing>.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет доступ к коллекции клиентов в стиле REST (относительно ресурсов). Как и службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] на основе SOAP, эту службу можно разместить в ASP.NET с помощью SVC-файла. Однако зачастую это нежелательно для работы по HTTP, поскольку в этом случае для службы требуется указание SVC-файла в URL. Кроме того, в этом случае требуется развертывание SVC-файла вместе с библиотекой службы. Этих ограничений можно избежать, разместив службы с помощью маршрутов ASP.NET, как показано в данном образце.  
  
 Этот образец размещает службы в ASP.NET путем добавления маршрута <xref:System.ServiceModel.Activation.ServiceRoute> в файл Global.asax. Маршрут <xref:System.ServiceModel.Activation.ServiceRoute> указывает тип службы (в этом случае «Service»), тип фабрики узла служб, который должен использоваться для службы (в этом случае <xref:System.ServiceModel.Activation.WebServiceHostFactory>) и базовый адрес HTTP для службы (в этом случае «~/Customers»).  
  
 Помимо этого, в образец включен файл Web.config, который добавляет модуль <xref:System.Web.Routing.UrlRoutingModule> (для включения маршрутов ASP.NET), а также конфигурацию для службы. В частности, эта конфигурация задает службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] конечную точку <xref:System.ServiceModel.Description.WebHttpEndpoint> по умолчанию, параметру <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> которой установлено значение `true`. В результате этого инфраструктура [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает автоматическую страницу справки в формате HTML по адресу `http://localhost/Customers/help`, которая предоставляет сведения о том, как сформировать запросы HTTP службе и как получить доступ к ответу службы в формате HTTP, например образец того, как данные покупателя представлены в форматах XML и JSON.  
  
 Предоставление таким способом доступа к коллекции покупателей (и в целом к любому ресурсу) позволяет клиенту взаимодействовать со службой единым образом с помощью URI и команд HTTP `GET`, `PUT`, `DELETE` и `POST`.  
  
 В файле Program.cs из проекта «Клиент» показывается, как можно разработать клиент с помощью <xref:System.Net.HttpWebRequest>. Заметьте, что это лишь один из способов доступа к службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Также возможен доступ к службе с помощью других классов .NET Framework, например фабрики каналов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и <xref:System.Net.WebClient>. Другие примеры в пакете SDK (такие как [базовой службы HTTP](../../../../docs/framework/wcf/samples/basic-http-service.md) образца и [автоматический выбор формата](../../../../docs/framework/wcf/samples/automatic-format-selection.md) образец) показано, как использовать эти классы для взаимодействия с [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы.  
  
 Этот образец состоит из трех проектов.  
  
 Служба  
 Проект веб-приложения, в который включена служба WCF HTTP, размещенная в ASP.NET.  
  
 Клиент  
 Проект консольного приложения, вызывающий службу.  
  
 Общие  
 Общая библиотека, содержащая тип `Customer`, который используется клиентом и службой. Во время выполнения клиентского консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте решение для образца ASP.NET Routes Integration в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
3.  Если он не открыт, нажмите клавиши «CTRL + W, S» для открытия **обозревателе решений** окна.  
  
4.  Из **обозревателе решений** щелкните правой кнопкой мыши **службы** проект и поместите курсор над **отладки** контекстного меню, чтобы **запуск Новый экземпляр** и выберите пункт контекстного меню **запустить новый экземпляр**.  Запускается сервер разработки ASP.NET, на котором размещается служба.  
  
5.  Из **обозревателе решений** щелкните правой кнопкой мыши **клиента** проект и поместите курсор над **отладки** контекстного меню, чтобы **запуск нового Экземпляр** и выберите пункт контекстного меню **запустить новый экземпляр**.  
  
6.  На клиенте открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы. HTML-страницу справки можно просмотреть в любой момент времени, введя URI этой страницы в браузере. Во время работы образца клиент записывает состояние текущего действия.  
  
7.  Чтобы завершить клиентское консольное приложение, нажмите любую клавишу.  
  
8.  Нажмите клавиши Shift + F5, чтобы остановить отладку службы, в области уведомлений Windows щелкните правой кнопкой мыши значок сервера разработки ASP.NET и выберите **остановить** в контекстном меню.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a>См. также
