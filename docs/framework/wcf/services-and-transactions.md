---
title: Службы и транзакции
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: 85792584660bd742ad3d313bf04ef1ce88bddcc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="services-and-transactions"></a>Службы и транзакции
Приложения Windows Communication Foundation (WCF) могут инициировать транзакцию из клиента и координировать ее в пределах операции службы. Клиенты могут инициировать транзакцию, вызвать несколько операций службы и обеспечить, чтобы операции службы либо фиксировались, либо откатывались как единый блок.  
  
 Чтобы включить поведение транзакции в контракте службы, укажите атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> и задайте его свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> и <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> для операций службы, для которых требуются клиентские транзакции. Параметр <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> указывает, следует ли автоматически завершать транзакцию, в которой выполняется метод, при отсутствии необработанных исключений. Дополнительные сведения об этих атрибутах см. в разделе [атрибуты транзакции ServiceModel](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
 Работа, выполняемая операциями службы и управляемая диспетчером ресурсов (например, ведение журнала обновления базы данных), является частью транзакции клиента.  
  
 В следующем примере показано использование атрибутов <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> для управления поведением транзакций на стороне сервера.  
  
```  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog(String.Format("Added {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog(String.Format("Subtracted {0} from {1}", n1, n2));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog(String.Format("Multiplied {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog(String.Format("Divided {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
}  
```  
  
 Можно включить транзакции и транзакция потока путем настройки клиента и службы привязки для использования протокола WS-AtomicTransaction и параметр [ \<transactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) элемента `true`, как показано в следующем образце конфигурации.  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"   
          binding="netTcpBinding"   
          bindingConfiguration="netTcpBindingWSAT"   
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 Клиенты могут начинать транзакции путем создания <xref:System.Transactions.TransactionScope> и вызова операций службы в области транзакции.  
  
```  
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка транзакций в System.ServiceModel](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)  
 [Модели транзакций](../../../docs/framework/wcf/feature-details/transaction-models.md)  
 [Поток транзакций WS](../../../docs/framework/wcf/samples/ws-transaction-flow.md)
