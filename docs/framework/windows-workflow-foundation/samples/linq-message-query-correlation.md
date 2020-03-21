---
title: Корреляция запросов сообщений LINQ
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: 507001b165efdcbe7c1e27a07749dbe2eafb468f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182810"
---
# <a name="linq-message-query-correlation"></a>Корреляция запросов сообщений LINQ
Этот образец демонстрирует, как выполнять корреляцию на основе содержимого с использованием пользовательской реализации <xref:System.ServiceModel.Dispatcher.MessageQuery> (в отличие от системной реализации <xref:System.ServiceModel.XPathMessageQuery>).  
  
## <a name="demonstrates"></a>Что демонстрирует  
 Пользовательская корреляция <xref:System.ServiceModel.Dispatcher.MessageQuery> на основе содержимого.  
  
## <a name="discussion"></a>Обсуждение  
 Этот образец показывает, как выполняется расширение базового класса <xref:System.ServiceModel.Dispatcher.MessageQuery> с целью корреляции. Пользовательская реализация `LinqMessageQuery` позволяет пользователям выдавать XName для поиска внутри сообщения с использованием XLinq. Данные, полученные в результате выполнения запроса, используются для формирования ключа корреляции с целью перенаправления сообщений в соответствующий экземпляр рабочего процесса.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP. Для выполнения этого образца необходимо добавить надлежащие URL-аКЛз (см. [Настройка HTTP и HTTPS](../../wcf/feature-details/configuring-http-and-https.md) для деталей), либо запустив Visual Studio в качестве администратора, либо выполняя следующую команду в повышенной подсказке для добавления соответствующих ACL. Убедитесь, что подставлены нужный домен и имя пользователя.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. После добавления списков управления доступом по URL-адресу выполните следующие действия.  
  
    1. Создайте решение.  
  
    2. Установите несколько проектов запуска, нажав на решение правой кнопкой мыши и выбрав **настройку startup Projects.** Добавление **обслуживания** и **клиента** (в этом порядке) в качестве нескольких стартап-проектов.  
  
    3. Запустите приложение. На консоль клиентского приложения выводится рабочий процесс, вначале отправляющий заказ, затем получающий идентификатор заказа на покупку и, наконец, подтверждающий заказ. В окне службы будут выведены сведения об обрабатываемых запросах.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
