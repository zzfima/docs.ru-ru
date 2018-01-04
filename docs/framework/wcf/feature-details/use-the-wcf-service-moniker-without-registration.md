---
title: "Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18f575e9bae37b66526d7b61a641374266ba627b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации
Для соединения со службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и обмена данными с ней клиентское приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должно располагать сведениями об адресе службы, конфигурации привязки и контракте службы.  
  
 Моникер службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обычно получает требуемый контракт посредством предварительной регистрации требуемых типов атрибутов, однако возможны ситуации, когда это нецелесообразно. Вместо регистрации моникер может получать определение контракта в виде документа на языке WSDL - путем использования параметра `wsdl` или с помощью обмена метаданными (MEX), путем использования параметра `mexAddress`.  
  
 Это делает возможной реализацию таких сценариев, как распространение электронной таблицы Excel, в которой значения некоторых ячеек вычисляются посредством взаимодействия с веб-службой. В подобном сценарии может быть нецелесообразным регистрировать сборку контракта службы на всех клиентах, которые могут открывать документ. Параметр `wsdl` или параметр `mexAddress` позволяет получить автономное решение.  
  
> [!NOTE]
>  Для защиты от изменения запросов и ответов или спуфинга необходимо использовать взаимную проверку подлинности. В частности, важно, чтобы клиенты были уверены в том, что отвечающая конечная точка обмена данными является ожидаемой доверенной стороной.  
  
## <a name="example"></a>Пример  
 В этом примере показано использование моникера службы в сочетании с контрактом MEX. Служба со следующим контрактом предоставляется посредством привязки wsHttpBinding.  
  
```  
using System.ServiceModel;  
  
...  
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 Для построения клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для удаленной службы можно использовать следующий пример строки моникера.  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 В ходе выполнения клиентского приложения клиент выполняет обмен данными `WS-MetadataExchange` с переданным параметром `mexAddress`. В результате могут быть возвращены сведения об адресе, привязке и контракте для ряда служб. Параметры `address`, `contract`, `contractNamespace`, `binding` и `bindingNamespace` используются для идентификации требуемой службы. Если параметры соответствуют требуемым, моникер строит клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с соответствующим определением контракта, после чего можно делать вызовы с использованием клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], как в случае с типизированным контрактом.  
  
> [!NOTE]
>  Если моникер сформирован неправильно или служба недоступна, при вызове метода `GetObject` будет возвращена ошибка "Синтаксическая ошибка". При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Регистрация и настройка моникера службы](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
