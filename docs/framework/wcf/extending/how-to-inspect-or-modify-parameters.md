---
title: Практическое руководство. Проверка или изменение параметров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: ddf6ad667eb131ec6fa4f12ed112c57368c43d9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-inspect-or-modify-parameters"></a>Практическое руководство. Проверка или изменение параметров
Может проверять или изменять входящие или исходящие сообщения для отдельной операции в объекте клиента Windows Communication Foundation (WCF) или [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы путем реализации <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> интерфейса и их вставка в клиенте или в службе Среда выполнения. Как правило, для добавления инспекторов параметров для отдельной операции используется поведение операции; другие поведения могут использоваться для обеспечения быстрого доступа к среде выполнения в более широкой области действия. Дополнительные сведения см. в разделе [расширение клиентов](../../../../docs/framework/wcf/extending/extending-clients.md) и [расширение диспетчеров](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Проверка или изменение параметров  
  
1.  Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.  
  
2.  Реализуйте поведение <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (в зависимости от того, какая требуется область действия), чтобы добавить инспектор параметров в свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.  
  
3.  Вставьте поведение до вызова метода <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> в производство каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Пример  
 В следующих примерах кода показаны, по порядку:  
  
-   реализация инспектора параметров;  
  
-   реализация поведения, вставляющего инспектор параметров с помощью <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> и <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>;  
  
-   файл конфигурации, который загружает и запускает поведение конечной точки в клиентском приложении для вставки инспектора параметров в клиент.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a>См. также  
 [Настройка и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
