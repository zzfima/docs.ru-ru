---
title: "Как асинхронно вызывать операции службы WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Как асинхронно вызывать операции службы WCF
В этом разделе описано, каким образом клиент может асинхронно обратиться к операции службы.Служба в этом разделе реализует интерфейс `ICalculator`.Клиент может асинхронно вызывать операции этого интерфейса с помощью управляемой событиями модели асинхронного вызова.\(Дополнительные сведения об управляемой событиями модели асинхронного вызова см. в разделе [Многопотоковое программирование с асинхронной технологией на основе событий](http://go.microsoft.com/fwlink/?LinkId=248184)\).Пример, в котором показана реализация асинхронной операции в службе, см. в разделе [Как асинхронно реализовывать операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [Синхронные и асинхронные операции](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
>  Управляемая событиями модель асинхронных вызовов не поддерживается при использовании класса <xref:System.ServiceModel.ChannelFactory%601>.Сведения об асинхронных вызовах с использованием <xref:System.ServiceModel.ChannelFactory%601> см. в разделе [Практическое руководство. Асинхронный вызов операций с использованием фабрики каналов](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## Процедура  
  
#### Асинхронных вызов операций службы WCF  
  
1.  Запустите средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с параметрами командной строки `/async` и `/tcv:Version35`, как показано в следующей команде.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     При этом помимо синхронной операции и стандартной асинхронной операции на базе делегата создается класс клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который содержит:  
  
    -   Две операции \<`operationName`\>`Async` для использования с асинхронными вызовами на базе событий.Пример:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   События с завершенными операциями в форме \<`operationName`\>`Completed` для использования с асинхронными вызовами на базе событий.Пример:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   Типы <xref:System.EventArgs?displayProperty=fullName> для каждой операции \(в форме \<`operationName`\>`CompletedEventArgs`\) для использования с асинхронными вызовами на базе событий.Пример:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  В вызывающем приложении создайте метод обратного вызова, вызываемый после завершения асинхронной операции, как показано в следующем образца кода.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  Перед вызовом операции используйте новый универсальный обработчик <xref:System.EventHandler%601?displayProperty=fullName> типа \<`operationName`\>`EventArgs`, чтобы добавить метод обработчика \(созданный на предыдущем шаге\) в событие \<`operationName`\>`Completed`.После этого вызовите метод \<`operationName`\>`Async`.Пример:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## Пример  
  
> [!NOTE]
>  Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>.Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>. Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`.При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>.Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## См. также  
 [Как асинхронно реализовывать операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)