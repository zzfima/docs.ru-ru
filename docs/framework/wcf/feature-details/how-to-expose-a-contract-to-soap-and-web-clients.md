---
title: "Практическое руководство. Предоставление контрактов SOAP- и веб-клиентам | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Практическое руководство. Предоставление контрактов SOAP- и веб-клиентам
По умолчанию [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] делает конечные точки доступными только для клиентов SOAP.  В разделе [Как создать простую веб\-службу WCF HTTP](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md) доступ к конечной точке предоставляется клиентам, не использующим протокол SOAP.  Иногда может потребоваться сделать один и тот же контракт доступным обоими способами: в качестве сетевой конечной точки и в качестве конечной точки SOAP.  В данном разделе приводится пример того, как это сделать.  
  
### Определение контракта службы  
  
1.  Определите контракт службы с использованием интерфейса, отмеченного атрибутами <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> и <xref:System.ServiceModel.Web.WebGetAttribute>, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
     [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]  
  
    > [!NOTE]
    >  По умолчанию атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> сопоставляет с операцией вызовы POST.  Однако можно указать метод для сопоставления с операцией, задав параметр «method\=».  В методе <xref:System.ServiceModel.Web.WebGetAttribute> отсутствует параметр «method\=», при этом метод сопоставляет с операцией службы только вызовы GET.  
  
2.  Реализуйте контракт службы, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]  
  
### Размещение службы  
  
1.  Создайте объект <xref:System.ServiceModel.ServiceHost>, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]  
  
2.  Добавьте объект <xref:System.ServiceModel.Description.ServiceEndpoint> с привязкой <xref:System.ServiceModel.BasicHttpBinding> для конечной точки SOAP, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]  
  
3.  Добавьте объект <xref:System.ServiceModel.Description.ServiceEndpoint> с привязкой <xref:System.ServiceModel.WebHttpBinding> для конечной точки, не использующей протокол SOAP, и добавьте в эту точку объект <xref:System.ServiceModel.Description.WebHttpBehavior>, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]  
  
4.  Вызовите метод `Open()` в экземпляре <xref:System.ServiceModel.ServiceHost>, чтобы открыть ведущее приложение службы, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]  
  
### Вызов операций службы, сопоставленных с операцией GET, в Internet Explorer  
  
1.  Откройте окно Internet Explorer, введите адрес `http://localhost:8000/Web/EchoWithGet?s=Hello, world!` и нажмите клавишу ВВОД.  Этот URL\-адрес содержит базовый адрес службы \("http:\/\/localhost:8000\/"\), относительный адрес конечной точки \(""\), вызываемую операцию службы \("EchoWithGet"\), вопросительный знак и следующий за ним список именованных параметров, в качестве разделителя между которыми используется амперсанд \(&\).  
  
### Вызов операций службы в сетевой конечной точке в коде  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.Web.WebChannelFactory%601> в блоке `using`, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]  
  
> [!NOTE]
>  Метод `Close()` автоматически вызывается для канала в конце блока `using`.  
  
1.  Создайте канал и вызовите службу, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]  
  
### Вызов операций службы в конечной точке SOAP  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.ChannelFactory> в блоке `using`, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
     [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]  
  
2.  Создайте канал и вызовите службу, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
     [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]  
  
### Закрытие узла службы  
  
1.  Закройте ведущее приложение службы, как показано в следующем коде.  
  
     [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
     [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]  
  
## Пример  
 Ниже приведен полный код для этого раздела.  
  
 [!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
 [!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]  
  
## Компиляция кода  
 При компиляции Service.cs обращается к файлам System.ServiceModel.dll и System.ServiceModel.Web.dll.  
  
## См. также  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Web.WebGetAttribute>   
 <xref:System.ServiceModel.Web.WebInvokeAttribute>   
 <xref:System.ServiceModel.Web.WebServiceHost>   
 <xref:System.ServiceModel.ChannelFactory>   
 <xref:System.ServiceModel.Description.WebHttpBehavior>   
 [Модель веб\-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)