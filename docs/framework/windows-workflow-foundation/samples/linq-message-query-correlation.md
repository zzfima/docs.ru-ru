---
title: "Корреляция запросов сообщений LINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3239d14ce8213b719305b5e32204569a8105997a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="linq-message-query-correlation"></a>Корреляция запросов сообщений LINQ
Этот образец демонстрирует, как выполнять корреляцию на основе содержимого с использованием пользовательской реализации <xref:System.ServiceModel.Dispatcher.MessageQuery> (в отличие от системной реализации <xref:System.ServiceModel.XPathMessageQuery>).  
  
## <a name="demonstrates"></a>Демонстрации  
 Пользовательская корреляция <xref:System.ServiceModel.Dispatcher.MessageQuery> на основе содержимого.  
  
## <a name="discussion"></a>Обсуждение  
 Этот образец показывает, как выполняется расширение базового класса <xref:System.ServiceModel.Dispatcher.MessageQuery> с целью корреляции. Пользовательская реализация `LinqMessageQuery` позволяет пользователям выдавать XName для поиска внутри сообщения с использованием XLinq. Данные, полученные в результате выполнения запроса, используются для формирования ключа корреляции с целью перенаправления сообщений в соответствующий экземпляр рабочего процесса.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP. Для запуска этого примера, соответствующие URL ACL, необходимо добавить (см. [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) подробные сведения), запустив Visual Studio от имени администратора, или, выполнив следующую команду в командной строке с повышенными привилегиями, чтобы добавить нужные списки управления доступом. Убедитесь, что подставлены нужный домен и имя пользователя.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  После добавления списков управления доступом по URL-адресу выполните следующие действия.  
  
    1.  Постройте решение.  
  
    2.  Задайте несколько запускаемых проектов, щелкните правой кнопкой мыши решение и выбрав **назначить запускаемые проекты**. Добавить **службы** и **клиента** (в указанном порядке) в качестве запускаемых проектов.  
  
    3.  Запустите приложение. На консоль клиентского приложения выводится рабочий процесс, вначале отправляющий заказ, затем получающий идентификатор заказа на покупку и, наконец, подтверждающий заказ. В окне службы будут выведены сведения об обрабатываемых запросах.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
