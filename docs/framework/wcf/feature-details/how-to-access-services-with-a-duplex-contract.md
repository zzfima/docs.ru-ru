---
title: "Практическое руководство. Доступ к службам с дуплексным контрактом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 425d17fa34b61985ad3600f992e028e156f6adb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Практическое руководство. Доступ к службам с дуплексным контрактом
Одной из особенностей [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является возможность создать службу, использующую дуплексный шаблон обмена сообщениями. Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова. В этом разделе приведены основные этапы создания клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в классе клиента, который реализует интерфейс обратного вызова.  
  
 Двойная привязка предоставляет службе IP-адрес клиента. Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.  
  
 Учебник по созданию базового [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы и клиента см. в разделе [учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md).  
  
### <a name="to-access-a-duplex-service"></a>Доступ к дуплексной службе  
  
1.  Создайте службу, содержащую два интерфейса. Первый интерфейс предназначен для службы, второй - для обратного вызова. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Создание дуплексной службы. в разделе [как: создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
2.  Запустите службу.  
  
3.  Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контрактов (интерфейсы) для клиента. Сведения о том, как это сделать в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
4.  Реализуйте в классе клиента интерфейс обратного вызова, как показано в следующем примере.  
  
    ```csharp  
    public class CallbackHandler : ICalculatorDuplexCallback  
    {  
        public void Result(double result)  
        {  
            Console.WriteLine("Result ({0})", result);  
        }  
        public void Equation(string equation)  
        {  
            Console.WriteLine("Equation({0})", equation);  
        }  
    }  
    ```  
  
    ```vb  
    Public Class CallbackHandler   
    Implements ICalculatorDuplexCallback  
       Public Sub Result (ByVal result As Double)  
          Console.WriteLine("Result ({0})", result)  
       End Sub  
        Public Sub Equation(ByVal equation As String)  
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  Создайте экземпляр класса <xref:System.ServiceModel.InstanceContext>. Конструктору требуется экземпляр класса клиента.  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  Создайте экземпляр клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], используя конструктор, которому требуется объект <xref:System.ServiceModel.InstanceContext>. Вторым параметром конструктора является имя конечной точки, определенное в файле конфигурации.  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  Вызовите требуемые методы клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как создать класс клиента, обращающийся к дуплексному контракту.  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
  
## <a name="see-also"></a>См. также  
 [Руководство по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Практическое руководство. Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Практическое руководство. Создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Практическое руководство. Использование ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
