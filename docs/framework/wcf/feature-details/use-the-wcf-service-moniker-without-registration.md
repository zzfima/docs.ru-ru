---
title: Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: fd61528770b16b13430be3691aef19c1cc743e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497975"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a><span data-ttu-id="460b8-102">Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации</span><span class="sxs-lookup"><span data-stu-id="460b8-102">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>
<span data-ttu-id="460b8-103">Для подключения и взаимодействия со службой Windows Communication Foundation (WCF), клиентское приложение WCF необходимо располагать сведениями об адресе службы, конфигурацию привязки и контракта службы.</span><span class="sxs-lookup"><span data-stu-id="460b8-103">To connect to and communicate with a Windows Communication Foundation (WCF) service, a WCF client application must have the details of the service address, the binding configuration, and the service contract.</span></span>  
  
 <span data-ttu-id="460b8-104">Моникер службы WCF обычно получает требуемый контракт посредством предварительной регистрации требуемых типов атрибутов, но может возникнуть ситуация, когда это нецелесообразно.</span><span class="sxs-lookup"><span data-stu-id="460b8-104">The WCF service moniker typically obtains the required contract through prior registration of the required attribute types, but there might be cases where this is not feasible.</span></span> <span data-ttu-id="460b8-105">Вместо регистрации моникер может получать определение контракта в виде документа на языке WSDL - путем использования параметра `wsdl` или с помощью обмена метаданными (MEX), путем использования параметра `mexAddress`.</span><span class="sxs-lookup"><span data-stu-id="460b8-105">In place of registration, the moniker can obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document, through the use of the `wsdl` parameter or through Metadata Exchange, through the use of the `mexAddress` parameter.</span></span>  
  
 <span data-ttu-id="460b8-106">Это делает возможной реализацию таких сценариев, как распространение электронной таблицы Excel, в которой значения некоторых ячеек вычисляются посредством взаимодействия с веб-службой.</span><span class="sxs-lookup"><span data-stu-id="460b8-106">This enables scenarios such as the distribution of an Excel spreadsheet where some of the cell values are calculated through Web service interactions.</span></span> <span data-ttu-id="460b8-107">В подобном сценарии может быть нецелесообразным регистрировать сборку контракта службы на всех клиентах, которые могут открывать документ.</span><span class="sxs-lookup"><span data-stu-id="460b8-107">In this scenario, it might not be feasible to register the service contract assembly on all clients that might open the document.</span></span> <span data-ttu-id="460b8-108">Параметр `wsdl` или параметр `mexAddress` позволяет получить автономное решение.</span><span class="sxs-lookup"><span data-stu-id="460b8-108">The `wsdl` parameter or the `mexAddress` parameter enables a self-contained solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="460b8-109">Для защиты от изменения запросов и ответов или спуфинга необходимо использовать взаимную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="460b8-109">Mutual authentication must be used to protect against request and response tampering or spoofing.</span></span> <span data-ttu-id="460b8-110">В частности, важно, чтобы клиенты были уверены в том, что отвечающая конечная точка обмена данными является ожидаемой доверенной стороной.</span><span class="sxs-lookup"><span data-stu-id="460b8-110">Specifically, it is important for clients to be assured that the Metadata Exchange endpoint that is responding is the intended trusted party.</span></span>  
  
## <a name="example"></a><span data-ttu-id="460b8-111">Пример</span><span class="sxs-lookup"><span data-stu-id="460b8-111">Example</span></span>  
 <span data-ttu-id="460b8-112">В этом примере показано использование моникера службы в сочетании с контрактом MEX.</span><span class="sxs-lookup"><span data-stu-id="460b8-112">This example shows the use of the service moniker with a MEX contract.</span></span> <span data-ttu-id="460b8-113">Служба со следующим контрактом предоставляется посредством привязки wsHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="460b8-113">A service with the following contract is exposed with a wsHttpBinding.</span></span>  
  
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
  
 <span data-ttu-id="460b8-114">Может использоваться для создания клиента WCF для удаленной службы следующий пример строки моникера.</span><span class="sxs-lookup"><span data-stu-id="460b8-114">To construct a WCF client for the remote service the following example moniker string can be used.</span></span>  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 <span data-ttu-id="460b8-115">В ходе выполнения клиентского приложения клиент выполняет обмен данными `WS-MetadataExchange` с переданным параметром `mexAddress`.</span><span class="sxs-lookup"><span data-stu-id="460b8-115">During the execution of the client application, the client performs a `WS-MetadataExchange` with the provided `mexAddress`.</span></span> <span data-ttu-id="460b8-116">В результате могут быть возвращены сведения об адресе, привязке и контракте для ряда служб.</span><span class="sxs-lookup"><span data-stu-id="460b8-116">This might return the address, binding and contract details for a number of services.</span></span> <span data-ttu-id="460b8-117">Параметры `address`, `contract`, `contractNamespace`, `binding` и `bindingNamespace` используются для идентификации требуемой службы.</span><span class="sxs-lookup"><span data-stu-id="460b8-117">The `address`, `contract`, `contractNamespace`, `binding` and `bindingNamespace` parameters are used to identify the intended service.</span></span> <span data-ttu-id="460b8-118">После сопоставления этих параметров, моникер строит клиент WCF с соответствующим определением контракта, и можно затем вызывать с помощью клиента WCF, как и в случае с типизированным контрактом.</span><span class="sxs-lookup"><span data-stu-id="460b8-118">Once those parameters have been matched, the moniker constructs a WCF client with the appropriate contract definition and calls can then be made using the WCF client, as with the typed contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="460b8-119">Если моникер сформирован неправильно или служба недоступна, при вызове метода `GetObject` будет возвращена ошибка "Синтаксическая ошибка".</span><span class="sxs-lookup"><span data-stu-id="460b8-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error saying "Invalid Syntax".</span></span> <span data-ttu-id="460b8-120">При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.</span><span class="sxs-lookup"><span data-stu-id="460b8-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460b8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="460b8-121">See Also</span></span>  
 [<span data-ttu-id="460b8-122">Практическое руководство. Регистрация и настройка моникера службы</span><span class="sxs-lookup"><span data-stu-id="460b8-122">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
