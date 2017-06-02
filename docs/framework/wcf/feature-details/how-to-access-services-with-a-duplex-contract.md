---
title: "Практическое руководство. Доступ к службам с дуплексным контрактом | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "дуплексные контракты [WCF]"
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Практическое руководство. Доступ к службам с дуплексным контрактом
Одной из особенностей [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является возможность создать службу, использующую дуплексный шаблон обмена сообщениями.Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова.В этом разделе приведены основные этапы создания клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в классе клиента, который реализует интерфейс обратного вызова.  
  
 Двойная привязка предоставляет службе IP\-адрес клиента.Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.  
  
 Инструкции по созданию простой службы и клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md).  
  
### Доступ к дуплексной службе  
  
1.  Создайте службу, содержащую два интерфейса.Первый интерфейс предназначен для службы, второй — для обратного вызова.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о создании дуплексной службы см. в разделе [Как создавать дуплексный контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
2.  Запустите службу.  
  
3.  С помощью [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) создайте контракты \(интерфейсы\) для клиента.Сведения о том, как это сделать, см. в разделе [Как создать клиент](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
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
  
5.  Создайте экземпляр класса <xref:System.ServiceModel.InstanceContext>.Конструктору требуется экземпляр класса клиента.  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  Создайте экземпляр клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], используя конструктор, которому требуется объект <xref:System.ServiceModel.InstanceContext>.Вторым параметром конструктора является имя конечной точки, определенное в файле конфигурации.  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  Вызовите требуемые методы клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Пример  
 В следующем примере кода показано, как создать класс клиента, обращающийся к дуплексному контракту.  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## Безопасность платформы .NET Framework  
  
## См. также  
 [Учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Как создавать дуплексный контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)   
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Как создать клиент](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Практическое руководство. Использование ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)