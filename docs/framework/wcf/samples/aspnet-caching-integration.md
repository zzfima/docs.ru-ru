---
title: "Интеграция кэширования ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8830f1c19b7a91d6c22d3b5955624c7d8a86f5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="aspnet-caching-integration"></a>Интеграция кэширования ASP.NET
В этом образце демонстрируется использование выходного кэша ASP.NET в модели веб-программирования WCF HTTP . См. в разделе [базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образец резидентной версию этого сценария, которое обсуждается реализация service в глубину. В этом разделе основное внимание уделено возможности интеграции выходного кэша ASP.NET.  
  
## <a name="demonstrates"></a>Демонстрации  
 Интеграция с выходным кэшем ASP.NET  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> используется вместе с выходным кэшем ASP.NET для службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Атрибут <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> применяется к операциям службы и предоставляет имя профиля кэша для файла конфигурации, который будет использован для ответов из заданной операции.  
  
 В файле Service.cs из образца проекта Service как `GetCustomer` и `GetCustomers` операции с пометкой <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, который предоставляет имя профиля кэша «CacheFor60Seconds». В файле Web.config проекта Service профиль кэша «CacheFor60Seconds» предоставляется в рамках <`caching`> элемента <`system.web`>. Для этого профиля кэша значение `duration` атрибут является «60», поэтому ответы, связанные с этим профилем, кэшируются в кэше вывода ASP.NET в 60 секунд. Кроме того, для этого профиля кэша `varmByParam` атрибута задано значение «format» так запросы с разными значениями для `format` параметра строки запроса их ответы, кэшируются отдельно. Наконец, профиля кэша `varyByHeader` атрибут имеет значение «Accept», поэтому запросы с другими значениями заголовка Accept кэшируются отдельно ответы.  
  
 В файле Program.cs из проекта «Клиент» показывается, как можно разработать клиент с помощью <xref:System.Net.HttpWebRequest>. Заметьте, что это лишь один из способов доступа к WCF-службе. Также возможен доступ к службе с помощью других классов .NET Framework, например фабрики каналов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и <xref:System.Net.WebClient>. Другие примеры в пакете SDK (такие как [базовой службы HTTP](../../../../docs/framework/wcf/samples/basic-http-service.md) образца и [автоматический выбор формата](../../../../docs/framework/wcf/samples/automatic-format-selection.md) образец) показывают, как использовать эти классы для взаимодействия с [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы.  
  
## <a name="to-run-the-sample"></a>Выполнение образца  
 Этот образец состоит из трех проектов.  
  
-   **Служба**: проект веб-приложения, в который включена служба WCF HTTP, размещенная в ASP.NET.  
  
-   **Клиент**: проект консольного приложения, обращающийся к службе.  
  
-   **Общие**: общая библиотека, содержащая тип Customer, используемые клиентом и службой.  
  
 Во время выполнения клиентского консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте решение для образца ASP.NET Caching Integration.  
  
2.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
3.  Если **обозревателе решений** окно еще не открыто, нажмите клавиши CTRL + W + S.  
  
4.  Из **обозревателе решений** окна щелкните правой кнопкой мыши **службы** проект и выберите **запустить новый экземпляр**. Запускается сервер разработки ASP.NET, на котором размещается служба.  
  
5.  Из **обозревателе решений** окна щелкните правой кнопкой мыши **клиента** проект и выберите **запустить новый экземпляр**.  
  
6.  На клиенте открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы. HTML-страницу справки можно просмотреть в любой момент времени, введя URI этой страницы в браузере.  
  
7.  Во время работы образца клиент записывает состояние текущего действия.  
  
8.  Чтобы завершить клиентское консольное приложение, нажмите любую клавишу.  
  
9. Чтобы прекратить отладку службы, нажмите клавиши SHIFT+F5.  
  
10. В области уведомлений Windows щелкните правой кнопкой мыши значок сервера разработки ASP.NET и выберите **остановить**.
