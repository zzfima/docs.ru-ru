---
title: Как выполнить Создание одностороннего контракта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
ms.openlocfilehash: f7636d7013c236e0c51e5326a84ae47f2f98e283
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693627"
---
# <a name="how-to-create-a-one-way-contract"></a>Как выполнить Создание одностороннего контракта
В этом разделе приведены основные этапы создания методов, использующих односторонние контракты. Такие методы вызывают операции над службой Windows Communication Foundation (WCF) из клиента, но не ожидать ответа. Контракты этого типа можно использовать, к примеру, для публикации уведомлений для большого количества подписчиков. Также можно использовать односторонние контракты при создании дуплексного (двустороннего) контракта, что позволяет клиентам и серверам взаимодействовать независимо (клиент может инициировать вызовы сервера, а сервер - вызовы клиента). В частности, это позволяет серверу выполнять односторонние вызовы клиента, которые клиент может воспринимать как события. Подробные сведения об указании односторонних методов см. в описаниях свойства <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> и класса <xref:System.ServiceModel.OperationContractAttribute>.  
  
 Дополнительные сведения о создании клиентского приложения для дуплексного контракта см. в разделе [как: Доступ к службам с односторонним контрактом и контрактом типа запрос ответ](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md). Работающий пример см. в разделе [односторонней](../../../../docs/framework/wcf/samples/one-way.md) образца.  
  
### <a name="to-create-a-one-way-contract"></a>Создание одностороннего контракта  
  
1.  Создайте контракт службы, применив класс <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу, определяющему реализуемые службой методы.  
  
2.  Укажите, какие именно методы интерфейса может вызвать клиент, применив к ним класс <xref:System.ServiceModel.OperationContractAttribute>.  
  
3.  Отметьте операции, не имеющие выходных данных (возвращаемого значения и параметров out и ref), как односторонние, присвоив свойству <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> значение `true`. Обратите внимание, что все операции с классом <xref:System.ServiceModel.OperationContractAttribute> по умолчанию соответствуют требованиям контракта типа запрос-ответ, поскольку свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> по умолчанию имеет значение `false`. Поэтому необходимо явно задать свойству атрибута значение `true`, если требуется использовать односторонний контракт для метода.  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется контракт для службы, включающей несколько односторонних методов. Все методы имеют односторонние контракты, за исключением метода `Equals`, по умолчанию имеющего контракт типа запрос-ответ и возвращающего результат.  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md)
- [Практическое руководство. Определите контракт службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [Session](../../../../docs/framework/wcf/samples/session.md)
- [Практическое руководство. Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
