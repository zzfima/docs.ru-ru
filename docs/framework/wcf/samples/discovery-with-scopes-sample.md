---
title: Образец обнаружения с помощью областей
ms.date: 03/30/2017
ms.assetid: 6a37a754-6b8c-4ebe-bdf2-d4f0520271d5
ms.openlocfilehash: ee6fdb69f6417e6c43d671c7c76bda8af067d5a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502204"
---
# <a name="discovery-with-scopes-sample"></a>Образец обнаружения с помощью областей
В образце описывается использование областей для категоризации конечных точек, доступных для обнаружения, а также способы использования <xref:System.ServiceModel.Discovery.DiscoveryClient> для выполнения асинхронного поиска конечных точек. В службе этот образец показывает, как настраивать обнаружение всех конечных точек, добавляя поведение обнаружения конечных точек и используя его для добавления области к конечной точке, а также управляя возможностью обнаружения конечных точек. В клиенте образец описывает способы создания клиентами <xref:System.ServiceModel.Discovery.DiscoveryClient> и настройки параметров поиска для включения областей в <xref:System.ServiceModel.Discovery.FindCriteria>. В этом образце также описываются способы ограничений клиентами ответов путем добавления критериев завершения.  
  
## <a name="service-features"></a>Функции службы  
 В этом проекте показаны две конечные точки службы, добавляемые к <xref:System.ServiceModel.ServiceHost>. Во всех конечных точках имеются <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>, связанные с ними. Это поведение используется для добавления областей URI к обеим конечным точкам. Области используются для различения конечных точек, что обеспечивает возможность настройки поиска для клиентов. Для второй конечной точки возможность обнаружения можно выключить при задании для свойства <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> значения `false`. При этом метаданные обнаружения, связанные с этой конечной точкой, не отправляются как часть всех сообщений обнаружения.  
  
## <a name="client-features"></a>Функции клиентов  
 Метод `FindCalculatorServiceAddress()` используется для демонстрации способов использования <xref:System.ServiceModel.Discovery.DiscoveryClient> и передачи <xref:System.ServiceModel.Discovery.FindCriteria> с двумя ограничениями. Область добавляется к критерию, а для свойства <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> задается значение 1. Область ограничивает результаты, обеспечивая их доступность только для служб, публикующих одну область. При задании для <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> значения 1 ограничивает ответы, которые ожидаются <xref:System.ServiceModel.Discovery.DiscoveryClient>, самое большее, до 1 конечной точки. Вызов <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> представляет собой синхронную операцию, блокирующую поток, пока не истечет время ожидания или нахождения одной конечной точки.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  В этом образце используются конечные точки HTTP, и для работы этого образца необходимо добавить соответствующие списки управления доступом по URL-адресу. В разделе [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) подробные сведения. Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями. Если команда не работает, следует указать домен и имя пользователя в следующих аргументах: `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`.  
  
2.  Постройте решение.  
  
3.  Выполните исполняемый файл службы из каталога сборки.  
  
4.  Выполните исполняемый файл клиента. Учтите, что клиент может определить расположение службы.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryWithScopes`  
  
## <a name="see-also"></a>См. также
