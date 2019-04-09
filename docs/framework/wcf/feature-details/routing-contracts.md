---
title: Контракты маршрутизации
ms.date: 03/30/2017
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
ms.openlocfilehash: 660652caa804b8c19f6dd18bcba51bf4abc3ba12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145357"
---
# <a name="routing-contracts"></a>Контракты маршрутизации
Контракты маршрутизации определяют схемы обмена сообщениями, которые может обрабатывать служба маршрутизации.  Эти контракты являются бестиповыми, с их помощью служба может получать сообщение без набора знаний о схеме сообщения или действии. Благодаря этому служба маршрутизации может перенаправлять сообщения без дополнительной настройки под особенности маршрутизируемых сообщений.  
  
## <a name="routing-contracts"></a>Контракты маршрутизации  
 Поскольку служба маршрутизации принимает общий объект сообщения WCF, наиболее важным аспектом при выборе контракта является форма канала, который будет использоваться для связи с клиентами и серверами. При обработке сообщений служба маршрутизации использует симметричные циклы обработки сообщений, поэтому, как правило, форма входящего контракта должна быть такой же, как форма исходящего контракта. Однако бывают случаи, когда диспетчер модели службы можно изменить фигуры, например если диспетчер преобразует дуплексный канал в канал типа запрос ответ, или удаляет поддержку сеанса из канала, если он не является обязательным и не используется (т. е Если **SessionMode.Allowed**преобразования **IInputSessionChannel** в **IInputChannel**).  
  
 Для поддержки этих циклов сообщений служба маршрутизации предоставляет контракты из пространства имен <xref:System.ServiceModel.Routing>, которые должны использоваться при определении конечных точек службы, используемых службой маршрутизации. Эти контракты являются бестиповыми, что позволяет принимать любые типы сообщений или действия, а также позволяет службе маршрутизации обрабатывать сообщения без набора знаний их схемы. Дополнительные сведения о контрактах, используемых службой маршрутизации, см. в разделе [контракты маршрутизации](../../../../docs/framework/wcf/feature-details/routing-contracts.md).  
  
 Контракты, предоставляемые службой маршрутизации, находятся в пространстве имен <xref:System.ServiceModel.Routing>, они описаны в следующей таблице.  
  
|Контракт|Фигура|Форма канала|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel IOutputChannel, "->"|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel IOutputSessionChannel, "->"|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel IRequestChannel, "->"|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel IDuplexSessionChannel, "->"|  
  
## <a name="see-also"></a>См. также

- [Служба маршрутизации](../../../../docs/framework/wcf/feature-details/routing-service.md)
- [Введение в маршрутизацию](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
