---
title: Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: c08fc362694469560eb7368eb5e536c08ec19bdf
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975999"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации
Чтобы подключиться к службе Windows Communication Foundation (WCF) и взаимодействовать с ней, клиентское приложение WCF должно иметь сведения об адресе службы, конфигурации привязки и контракте службы.  
  
 Моникер службы WCF обычно получает требуемый контракт путем выполнения предварительной регистрации требуемых типов атрибутов, но в некоторых случаях это нецелесообразно. Вместо регистрации моникер может получать определение контракта в виде документа на языке WSDL - путем использования параметра `wsdl` или с помощью обмена метаданными (MEX), путем использования параметра `mexAddress`.  
  
 Это делает возможной реализацию таких сценариев, как распространение электронной таблицы Excel, в которой значения некоторых ячеек вычисляются посредством взаимодействия с веб-службой. В подобном сценарии может быть нецелесообразным регистрировать сборку контракта службы на всех клиентах, которые могут открывать документ. Параметр `wsdl` или параметр `mexAddress` позволяет получить автономное решение.  
  
> [!NOTE]
> Для защиты от изменения запросов и ответов или спуфинга необходимо использовать взаимную проверку подлинности. В частности, важно, чтобы клиенты были уверены в том, что отвечающая конечная точка обмена данными является ожидаемой доверенной стороной.  
  
## <a name="example"></a>Пример  
 В этом примере показано использование моникера службы в сочетании с контрактом MEX. Служба со следующим контрактом предоставляется посредством привязки wsHttpBinding.  
  
```csharp
using System.ServiceModel;  
  
// ...
  
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
  
 Чтобы создать клиент WCF для удаленной службы, можно использовать следующий пример строки моникера.  
  
```
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 В ходе выполнения клиентского приложения клиент выполняет обмен данными `WS-MetadataExchange` с переданным параметром `mexAddress`. В результате могут быть возвращены сведения об адресе, привязке и контракте для ряда служб. Параметры `address`, `contract`, `contractNamespace`, `binding` и `bindingNamespace` используются для идентификации требуемой службы. После сопоставления этих параметров моникер формирует клиент WCF с соответствующим определением контракта, а затем вызовы могут выполняться с помощью клиента WCF, как и типизированный контракт.  
  
> [!NOTE]
> Если моникер сформирован неправильно или служба недоступна, при вызове метода `GetObject` будет возвращена ошибка "Синтаксическая ошибка". При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Регистрация и настройка моникера службы](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
