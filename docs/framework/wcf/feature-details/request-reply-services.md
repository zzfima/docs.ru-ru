---
title: "Службы типа &quot;запрос-ответ&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "контракты [WCF], службы типа "запрос-ответ""
  - "контракты типа "запрос-ответ" [WCF]"
  - "WCF [WCF], службы типа "запрос-ответ""
  - "Windows Communication Foundation [WCF], службы типа "запрос-ответ""
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Службы типа &quot;запрос-ответ&quot;
Типом контракта операции службы в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] по умолчанию является "запрос\-ответ".Клиенты вызывают операции службы и ожидают ответа от службы.Вызывать операции службы можно либо синхронно \(клиент блокируется до тех пор, пока не получит ответ от службы или не истечет время вызова\), либо асинхронно \(клиент вызывает операцию службы, продолжает работать и получает ответ от службы в другом потоке\).  
  
 Чтобы создать контракт службы типа запрос\-ответ, определите контракт службы и примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждой из операций, как показано в следующем примере кода.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
  
```  
  
 Присваивать свойству <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> значение `false`, поскольку это поведение по умолчанию.  
  
## См. также  
 [Односторонние службы](../../../../docs/framework/wcf/feature-details/one-way-services.md)   
 [Дуплексные службы](../../../../docs/framework/wcf/feature-details/duplex-services.md)