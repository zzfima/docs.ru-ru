---
title: "Практическое руководство. Проверка и изменение сообщений в службе"
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
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c919083b165233614a01faf3d63dacd6712fbd01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>Практическое руководство. Проверка и изменение сообщений в службе
Проверять или изменять входящие или исходящие сообщения клиента [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно путем реализации интерфейса <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> и его вставки в среду выполнения службы. Дополнительные сведения см. в разделе [расширение диспетчеров](../../../../docs/framework/wcf/extending/extending-dispatchers.md). Эквивалентную функцию в службе выполняет интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
### <a name="to-inspect-or-modify-messages"></a>Проверка или изменение сообщений  
  
1.  Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.  
  
2.  Реализуйте интерфейс <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> в зависимости от области, в которую нужно легко вставить инспектор сообщений служб.  
  
3.  Вставьте поведение до вызова метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> в класс <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Пример  
 В следующих примерах кода показаны, по порядку:  
  
-   реализация инспектора службы;  
  
-   поведение службы, вставляющее инспектор;  
  
-   файл конфигурации, загружающий и запускающий поведение в приложении службы.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [Настройка и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
