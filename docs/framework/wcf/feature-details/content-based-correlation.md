---
title: Корреляция по содержимому
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f46a2b68-8d24-4122-bbee-9573fc3f9fb4
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b4ebd49fbed12f1e8120e67f32496cd782531da
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="content-based-correlation"></a>Корреляция по содержимому
Когда службы рабочего процесса обмениваются данными с клиентами и другими службами, в сообщениях часто встречаются данные, уникальным образом направляющие сообщение в определенный экземпляр. При корреляции на основе содержимого эти данные в сообщении, например номер заказчика или идентификатор заказа, используются для маршрутизации сообщения в определенный экземпляр рабочего процесса. В этом разделе описывается использование корреляции на основе содержимого в рабочих процессах.  
  
## <a name="using-content-based-correlation"></a>Использование корреляции на основе содержимого  
 Корреляция на основе содержимого применяется, если служба рабочего процесса имеет несколько методов, доступных одному клиенту, и некоторые данные в сообщениях идентифицируют нужный экземпляр.  
  
> [!NOTE]
>  Корреляция на основе содержимого полезна, если нельзя применить корреляцию на основе контекста, так как привязка не относится ни к одному поддерживаемому типу привязок для обмена контекстом. Дополнительные сведения о корреляции контекста см. в разделе [обмен контекстом](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md).  
  
 В каждом действии по обмену сообщениями при обмене данными должно быть указано расположение в сообщении данных, уникальным образом идентифицирующих экземпляр. Это делается путем указания набора <xref:System.ServiceModel.MessageQuerySet> с помощью <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> или <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, выбирающих из сообщения данные, уникальным образом идентифицирующие экземпляр.  
  
> [!WARNING]
>  Данные, используемые для идентификации экземпляра, хэшируются в ключ корреляции. Необходимо убедиться, что данные, используемые для корреляции, являются уникальными. В противном случае в хэшированном ключе могут возникнуть конфликты, которые приведут к неправильной маршрутизации сообщения. Например, корреляция на основе только имени заказчика может вызвать конфликт, так как могут иметься заказчики с одинаковыми именами. Двоеточие (`:`) не должно встречаться в данных, используемых для корреляции сообщений, так как оно уже применяется в качестве разделителя ключа и значения в запросе к сообщению, формирующих строку, которая впоследствии хэшируется.  
  
 В следующем примере первоначального <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> в службе рабочего процесса возвращает `OrderId`, который затем передается обратно клиентом при вызове следующих <xref:System.ServiceModel.Activities.Receive> действия в службе рабочего процесса.  
  
 [!code-csharp[CFX_ContentCorrelation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#1)]  
  
 В предыдущем примере показана корреляция на основе содержимого, инициализированная действием <xref:System.ServiceModel.Activities.SendReply>. Набор <xref:System.ServiceModel.MessageQuerySet> указывает, что в качестве данных, применяемых для идентификации последующих сообщений для этой службы, используется `OrderId`.  
  
 [!code-csharp[CFX_ContentCorrelation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#2)]  
  
 Действие <xref:System.ServiceModel.Activities.Receive>, следующее за действием <xref:System.ServiceModel.Activities.SendReply> в рабочем процессе, соответствует корреляции, инициализированной действием <xref:System.ServiceModel.Activities.SendReply>. Оба действия используют один и тот же дескриптор <xref:System.ServiceModel.Activities.CorrelationHandle>, но для каждого из них используются отдельные <xref:System.ServiceModel.MessageQuerySet> и <xref:System.ServiceModel.XPathMessageQuery>, указывающие, где расположены идентифицирующие данные в определенном сообщении. Для действия, инициализирующего корреляцию, <xref:System.ServiceModel.MessageQuerySet> указывается в свойстве <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>, а для любого следующего действия <xref:System.ServiceModel.Activities.Receive> - в свойстве <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>.  
  
 [!code-csharp[CFX_ContentCorrelation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#3)]  
  
 Корреляция на основе содержимого может инициализироваться любым действием по обмену сообщениями (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.ReceiveReply>), если данные передаются в составе сообщения. Если определенные данные не являются частью сообщения, то корреляция может быть инициализирована явно с помощью действия <xref:System.ServiceModel.Activities.InitializeCorrelation>. Если для уникальной идентификации сообщения требуется несколько блоков данных, то в набор <xref:System.ServiceModel.MessageQuerySet> можно добавить несколько запросов. В этих примерах <xref:System.ServiceModel.Activities.CorrelationHandle> был явно указан для каждого действия с помощью свойств `CorrelatesWith` или `CorrelationHandle`, но, если для всего рабочего процесса требуется только одна корреляция, как в примере с корреляцией на основе `OrderId`, достаточно неявного управления дескриптором взаимосвязи с помощью <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
## <a name="using-the-initializecorrelation-activity"></a>Использование действия InitializeCorrelation  
 В предыдущем примере `OrderId` направлялся вызывающему объекту с помощью действия <xref:System.ServiceModel.Activities.SendReply>, которое служило для инициализации корреляции. Это поведение может выполняться с помощью действия <xref:System.ServiceModel.Activities.InitializeCorrelation>. Действие <xref:System.ServiceModel.Activities.InitializeCorrelation> использует дескриптор <xref:System.ServiceModel.Activities.CorrelationHandle> и словарь элементов, представляющий данные для сопоставления сообщения с правильным экземпляром. Чтобы использовать действие <xref:System.ServiceModel.Activities.InitializeCorrelation>, описанное в предыдущем образце, удалите <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> из действия <xref:System.ServiceModel.Activities.SendReply> и инициализируйте корреляцию с помощью действия <xref:System.ServiceModel.Activities.InitializeCorrelation>.  
  
 [!code-csharp[CFX_ContentCorrelation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#4)]  
  
 Затем действие <xref:System.ServiceModel.Activities.InitializeCorrelation> используется в рабочем процессе, после того как заполняются переменные, содержащие данные, но перед действием <xref:System.ServiceModel.Activities.Receive>, связанным с инициализированным <xref:System.ServiceModel.Activities.CorrelationHandle>.  
  
 [!code-csharp[CFX_ContentCorrelation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#5)]  
  
## <a name="configuring-xpath-queries-using-the-workflow-designer"></a>Настройка запросов XPath с помощью конструктора рабочих процессов  
 В предыдущих примерах действия и запросы XPath, используемые в запросах к сообщениям, были определены в коде. Конструктор рабочих процессов в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] также предоставляет возможность создавать выражения XPath из типов `DataContract` для корреляции на основе содержимого. Первый запрос Xpath, настроенный в предыдущем примере, был настроен для действия <xref:System.ServiceModel.Activities.SendReply>.  
  
 [!code-csharp[CFX_ContentCorrelation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#2)]  
  
 Чтобы настроить выражение XPath для действия по обмену сообщениями в конструкторе рабочих процессов, выберите действие в конструкторе рабочих процессов. Если действие вызывает корреляцию, как в предыдущем примере, нажмите кнопку с многоточием для **CorrelationInitializers** свойство в **свойства** окна. При этом отображаются **Добавление инициализаторов корреляции** диалоговое окно. В этом диалоговом окне можно указать тип корреляции и выбрать содержимое, применяемое для корреляции. <xref:System.ServiceModel.Activities.CorrelationHandle> Переменная, указанная в **добавить инициализатор** поле, а тип корреляции и данные, используемые для корреляции выбирается из **запросы XPath** раздел диалогового окна.  
  
 ![Диалоговое окно CorrelationInitializer](../../../../docs/framework/wcf/feature-details/media/correlationinitializerdlg.jpg "CorrelationInitializerDlg")  
  
 Второй запрос XPath в предыдущем примере был настроен в действии <xref:System.ServiceModel.Activities.Receive>.  
  
 [!code-csharp[CFX_ContentCorrelation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#3)]  
  
 Чтобы настроить запрос XPath для действия по обмену сообщениями, не инициализирующего корреляцию, выберите действие в конструкторе рабочих процессов и нажмите кнопку с многоточием для **CorrelatesOn** свойство в  **Свойства** окна. При этом отображаются **корреляция по определению** диалоговое окно.  
  
 ![Корреляция по определению](../../../../docs/framework/wcf/feature-details/media/correlatesondialog.jpg "CorrelatesOnDialog")  
  
 В этом диалоговом окне укажите <xref:System.ServiceModel.Activities.CorrelationHandle> и выбрать элементы в **запросы XPath** списка, чтобы создать запрос XPath.
