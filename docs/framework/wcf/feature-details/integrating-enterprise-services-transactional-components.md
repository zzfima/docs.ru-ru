---
title: Интеграция транзакционных компонентов служб Enterprise Services
ms.date: 03/30/2017
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
ms.openlocfilehash: 292573f911459d8a8419e09d81fd1e54dbc6c70b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184740"
---
# <a name="integrating-enterprise-services-transactional-components"></a><span data-ttu-id="dc5e6-102">Интеграция транзакционных компонентов служб Enterprise Services</span><span class="sxs-lookup"><span data-stu-id="dc5e6-102">Integrating Enterprise Services Transactional Components</span></span>

<span data-ttu-id="dc5e6-103">Фонд связи Windows (WCF) предоставляет автоматический механизм интеграции с корпоративными службами [(см. Интеграцию с приложениями КОМЗ).](integrating-with-com-plus-applications.md)</span><span class="sxs-lookup"><span data-stu-id="dc5e6-103">Windows Communication Foundation (WCF) provides an automatic mechanism for integrating with Enterprise Services (see [Integrating with COM+ Applications](integrating-with-com-plus-applications.md)).</span></span> <span data-ttu-id="dc5e6-104">Однако для разработки служб, которые внутренне используют транзакционные компоненты, размещенные внутри служб Enterprise Services, может потребоваться гибкость.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-104">However, you may want the flexibility to develop services that internally use transactional components hosted within Enterprise Services.</span></span> <span data-ttu-id="dc5e6-105">Поскольку функция WCF Transactions <xref:System.Transactions> построена на инфраструктуре, процесс интеграции корпоративных служб с WCF <xref:System.Transactions> идентичен процессу для определения совместимости между корпоративными службами и корпоративными услугами, как указано в [совместимости с корпоративными услугами и транзакциями КОМЗ.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="dc5e6-105">Because the WCF Transactions feature is built on the <xref:System.Transactions> infrastructure, the process for integrating Enterprise Services with WCF is identical to that for specifying interoperability between <xref:System.Transactions> and Enterprise Services, as outlined in [Interoperability with Enterprise Services and COM+ Transactions](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85)).</span></span>  
  
 <span data-ttu-id="dc5e6-106">Чтобы обеспечить требуемый уровень взаимодействия между входящей поточной транзакцией и транзакцией контекста COM+, реализация службы должна создать экземпляр <xref:System.Transactions.TransactionScope> и использовать соответствующее значение из перечисления <xref:System.Transactions.EnterpriseServicesInteropOption>.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-106">To provide the desired level of interoperability between the incoming flowed transaction and the COM+ context transaction, the service implementation must create a <xref:System.Transactions.TransactionScope> instance and use the appropriate value from the <xref:System.Transactions.EnterpriseServicesInteropOption> enumeration.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a><span data-ttu-id="dc5e6-107">Интеграция служб Enterprise Services с операцией службы</span><span class="sxs-lookup"><span data-stu-id="dc5e6-107">Integrating Enterprise Services with a Service Operation</span></span>  
 <span data-ttu-id="dc5e6-108">В представленном ниже коде показана операция с разрешенным потоком транзакций, которая создает область <xref:System.Transactions.TransactionScope> с параметром <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-108">The following code demonstrates an operation, with Allowed transaction flow, that creates a <xref:System.Transactions.TransactionScope> with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> option.</span></span> <span data-ttu-id="dc5e6-109">В этом сценарии используются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-109">The following conditions apply in this scenario:</span></span>  
  
- <span data-ttu-id="dc5e6-110">Если клиент передает транзакцию, операция, включая вызов компонента Enterprise Services, выполняется в рамках области этой транзакции.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-110">If the client flows a transaction, the operation, including the call to the Enterprise Services component, is executed within the scope of that transaction.</span></span> <span data-ttu-id="dc5e6-111">Использование параметра <xref:System.Transactions.EnterpriseServicesInteropOption.Full> обеспечивает синхронизацию транзакции с контекстом <xref:System.EnterpriseServices>. Это означает, что внешняя транзакция для <xref:System.Transactions> и <xref:System.EnterpriseServices> одна и та же.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-111">Using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the transaction is synchronized with the <xref:System.EnterpriseServices> context, which means that the ambient transaction for <xref:System.Transactions> and the <xref:System.EnterpriseServices> is the same.</span></span>  
  
- <span data-ttu-id="dc5e6-112">Если клиент не передает транзакцию, при присвоении <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> значения `true` для операции создается новая область транзакции.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-112">If the client does not flow a transaction, setting <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true` creates a new transaction scope for the operation.</span></span> <span data-ttu-id="dc5e6-113">Аналогично, использование параметра <xref:System.Transactions.EnterpriseServicesInteropOption.Full> обеспечивает идентичность транзакции операции и транзакции, используемой внутри контекста компонента <xref:System.EnterpriseServices>.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-113">Similarly, using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the operation’s transaction is the same as the transaction used inside the <xref:System.EnterpriseServices> component's context.</span></span>  
  
 <span data-ttu-id="dc5e6-114">Любые дополнительные вызовы метода также происходят в пределах области той же транзакции операции.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-114">Any additional method calls also occur within the scope of the same operation’s transaction.</span></span>  
  
```csharp
[ServiceContract()]  
public interface ICustomerServiceContract  
{  
   [OperationContract]  
   [TransactionFlow(TransactionFlowOption.Allowed)]  
   void UpdateCustomerNameOperation(int customerID, string newCustomerName);  
}  
  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CustomerService : ICustomerServiceContract  
{  
   [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
   public void UpdateCustomerNameOperation(int customerID, string newCustomerName)  
   {  
   // Create a transaction scope with full ES interop  
      using (TransactionScope ts = new TransactionScope(  
                     TransactionScopeOption.Required,  
                     new TransactionOptions(),  
                     EnterpriseServicesInteropOption.Full))  
      {  
         // Create an Enterprise Services component  
         // Call UpdateCustomer method on an Enterprise Services
         // component
  
         // Call UpdateOtherCustomerData method on an Enterprise
         // Services component
         ts.Complete();  
      }  
  
      // Do UpdateAdditionalData on an non-Enterprise Services  
      // component  
   }  
}  
```  
  
 <span data-ttu-id="dc5e6-115">Если между текущей транзакцией операции и вызовами транзакционных компонентов Enterprise Services синхронизация не требуется, при создании экземпляра <xref:System.Transactions.EnterpriseServicesInteropOption.None> используйте параметр <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-115">If no synchronization is required between an operation’s current transaction and calls to transactional Enterprise Services components, then use the <xref:System.Transactions.EnterpriseServicesInteropOption.None> option when instantiating the <xref:System.Transactions.TransactionScope> instance.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-client"></a><span data-ttu-id="dc5e6-116">Интеграция служб Enterprise Services с клиентом</span><span class="sxs-lookup"><span data-stu-id="dc5e6-116">Integrating Enterprise Services with a Client</span></span>  
 <span data-ttu-id="dc5e6-117">В представленном ниже клиентском коде показано использование экземпляра <xref:System.Transactions.TransactionScope> с параметром <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-117">The following code demonstrates client code using a <xref:System.Transactions.TransactionScope> instance with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> setting.</span></span> <span data-ttu-id="dc5e6-118">В этом сценарии вызовы операций службы, которые поддерживают поток транзакций, происходят в рамках области той же транзакции, что и вызовы компонентов Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-118">In this scenario, calls to service operations that support transaction flow occur within the scope of the same transaction as the calls to Enterprise Services components.</span></span>  
  
```csharp
static void Main()  
{  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
  
    // Create a transaction scope with full ES interop  
    using (TransactionScope ts = new TransactionScope(  
          TransactionScopeOption.Required,  
          new TransactionOptions(),  
          EnterpriseServicesInteropOption.Full))  
    {  
        // Call Add calculator service operation  
  
        // Create an Enterprise Services component  
  
        // Call UpdateCustomer method on an Enterprise Services
        // component
  
        ts.Complete();  
    }  
  
    // Closing the client gracefully closes the connection and
    // cleans up resources  
    client.Close();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc5e6-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dc5e6-119">See also</span></span>

- [<span data-ttu-id="dc5e6-120">Интеграция с приложениями КОМЗ</span><span class="sxs-lookup"><span data-stu-id="dc5e6-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="dc5e6-121">Интеграция с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="dc5e6-121">Integrating with COM Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
