---
title: Практическое руководство. Создание конечной точки службы в коде
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
ms.openlocfilehash: 65d26c0b9a41a6825108b73f822add4d91400055
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787690"
---
# <a name="how-to-create-a-service-endpoint-in-code"></a>Практическое руководство. Создание конечной точки службы в коде
В этом примере контракт `ICalculator` определен для службы калькулятора, служба реализуется в классе `CalculatorService`, а затем ее конечная точка задается в коде с указанием того, что служба должна использовать класс <xref:System.ServiceModel.BasicHttpBinding>.  
  
 В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде. Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы. В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.  
  
#### <a name="to-create-a-service-endpoint-in-code"></a>Создание конечной точки службы в коде  
  
1. Создайте интерфейс, определяющий контракт службы.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. Реализуйте контракт службы, определенный на шаге 1.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. В ведущем приложении создайте базовый адрес для службы и привязку, которая используется со службой.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. Создайте основное приложение и вызовите <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> или одну из других перегрузок, чтобы добавить конечную точку службы для основного приложения.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     Чтобы указать привязку в коде, но использовать конечные точки по умолчанию, предоставляемые средой выполнения, передайте базовый адрес в конструктор при создании <xref:System.ServiceModel.ServiceHost> и не вызывайте метод <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     Дополнительные сведения о конечных точках по умолчанию, см. в разделе [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Указание привязки службы в коде](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)
