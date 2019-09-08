---
title: Практическое руководство. Проверка и изменение сообщений в службе
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 1356983361c483170d9d7365932b788f2421bf09
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795603"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>Практическое руководство. Проверка и изменение сообщений в службе
Вы можете проверять или изменять входящие или исходящие сообщения в клиенте Windows Communication Foundation (WCF), реализовав <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> и вставив его в среду выполнения службы. Дополнительные сведения см. в разделе [Расширение диспетчеров](extending-dispatchers.md). Эквивалентную функцию в службе выполняет интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
### <a name="to-inspect-or-modify-messages"></a>Проверка или изменение сообщений  
  
1. Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.  
  
2. Реализуйте интерфейс <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> в зависимости от области, в которую нужно легко вставить инспектор сообщений служб.  
  
3. Вставьте поведение до вызова метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> в класс <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>. Дополнительные сведения см. [в разделе Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Пример  
 В следующих примерах кода показаны, по порядку:  
  
- реализация инспектора службы;  
  
- поведение службы, вставляющее инспектор;  
  
- файл конфигурации, загружающий и запускающий поведение в приложении службы.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md)
