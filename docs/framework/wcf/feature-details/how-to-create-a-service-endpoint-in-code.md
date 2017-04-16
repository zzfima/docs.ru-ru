---
title: "Как создать конечную точку службы в коде | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Как создать конечную точку службы в коде
В этом примере контракт `ICalculator` определен для службы калькулятора, служба реализуется в классе `CalculatorService`, а затем ее конечная точка задается в коде с указанием того, что служба должна использовать класс <xref:System.ServiceModel.BasicHttpBinding>.  
  
 В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде.Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.  
  
#### Создание конечной точки службы в коде  
  
1.  Создайте интерфейс, определяющий контракт службы.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2.  Реализуйте контракт службы, определенный на шаге 1.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3.  В ведущем приложении создайте базовый адрес для службы и привязку, которая используется со службой.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4.  Создайте основное приложение и вызовите <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> или одну из других перегрузок, чтобы добавить конечную точку службы для основного приложения.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     Чтобы указать привязку в коде, но использовать конечные точки по умолчанию, предоставляемые средой выполнения, передайте базовый адрес в конструктор при создании <xref:System.ServiceModel.ServiceHost> и не вызывайте метод <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] о конечных точках по умолчанию см. в разделах [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## См. также  
 [Как задать привязку службы в коде](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)