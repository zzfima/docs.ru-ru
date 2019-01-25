---
title: Поддерживаемые сценарии развертывания
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 605521cb91945812db178db3a82883b4d13bc636
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614488"
---
# <a name="supported-deployment-scenarios"></a>Поддерживаемые сценарии развертывания
Подмножество функций Windows Communication Foundation (WCF), поддерживается для использования в частично доверенных приложениях предназначен для соответствия требованиям некоторых, но не все сценарии использования WCF. На сервере, соответствующий требованиям WCF к сети Интернет поставщиков услуг совместного размещения работающих приложений независимых поставщиков в [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] набор по соображениям безопасности разрешений среднего уровня доверия. На клиенте поддержка частичного доверия WCF разработан в соответствии с требованиями развертывания технологий, таких как [развертывания ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) или [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]технология приложения браузера XAML, которая допускает беспрепятственное и безопасное Развертывание классических приложений с ненадежных узлов.  
  
## <a name="minimum-permission-requirements"></a>Минимальные требования к разрешениям  
 WCF поддерживает подмножество функций в приложениях, выполняемых в рамках одного из следующих наборов разрешений со стандартными именами:  
  
-   Разрешения среднего уровня доверия;  
  
-   Набор разрешений зоны Интернета.  
  
 Попытка использовать WCF в частично доверенных приложениях с более строгими разрешениями может привести к возникновению исключений безопасности во время выполнения.  
  
 Дополнительные сведения о различных функциях, поддерживаемых в этих наборах разрешений, см. в разделе [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Частичное доверие на сервере  
 Многие коммерческие поставщики услуг размещения веб-приложений [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] требуют, чтобы выполняемые на их серверах приложения запускались с набором разрешений среднего уровня доверия [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] . Службы WCF могут работать в таких средах, если они используют <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>, или <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> Безопасность на уровне транспорта.  
  
 Службы WCF, работающие в со средним уровнем доверия, средах размещения, также может служить службы среднего уровня, отправляя сообщения на другие серверы в ответ на клиентские запросы. На сервере поддерживаются промежуточные сценарии, если среда размещения предоставила приложению соответствующее разрешение <xref:System.Net.WebPermission> на отправку исходящих запросов на требуемый сервер.  
  
 В дополнение к обмен сообщениями SOAP, с помощью одного из поддерживаемых протоколом SOAP привязок, WCF поддерживает <xref:System.ServiceModel.WebHttpBinding> для создания веб-службы в частично доверенных приложениях. [Модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [синдикации WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), и [интеграция с AJAX и поддержка JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) возможностей WCF поддерживаются в режиме частичного доверия.  
  
 Службы рабочего процесса требуют наличия разрешений полного доверия, их невозможно использовать в частично доверенных приложениях.  
  
 Дополнительные сведения см. в разделе [Как Использование среднего уровня доверия в ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Частичное доверие на клиенте  
 Необходимо предпринять определенные дополнительные меры безопасности при загрузке и запуске кода с ненадежных веб-сайтов Интернета. Технология [развертывания ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) и технология приложения браузера XAML [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)](XBAP) используют частичное доверие для предоставления ограниченных разрешений (в зоне Интернета) ненадежному коду.  
  
 WCF можно использовать для взаимодействия с удаленными серверами из частично доверенных приложений, развернутых с использованием [развертывания ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) или XBAP. Набор разрешений зоны Интернета включает <xref:System.Net.WebPermission> для исходного узла, которое позволяет этим приложениям взаимодействовать с исходным сервером с помощью любой из поддерживаемых привязок WCF, описанные в [Partial Trust Feature Compatibility ](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>См. также
- [Управление доступом для кода](https://go.microsoft.com/fwlink/?LinkId=83717)
- [Обзор размещенных в веб-браузере приложений Windows Presentation Foundation](https://go.microsoft.com/fwlink/?LinkId=98397)
- [Частичное доверие](../../../../docs/framework/wcf/feature-details/partial-trust.md)
- [Средний уровень доверия ASP.NET](https://go.microsoft.com/fwlink/?LinkId=69328)
