---
title: Практическое руководство. Задание привязки клиента в коде
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: c95e30c65c6096140fca0c1241e76fbc7af4df3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929133"
---
# <a name="how-to-specify-a-client-binding-in-code"></a>Практическое руководство. Задание привязки клиента в коде
В этом примере создается клиент, предназначенный для использования службы калькулятора, и привязка этого клиента задается императивно в коде. Клиент обращается к службе `CalculatorService`, которая реализует интерфейс `ICalculator`; как служба, так и клиент используют класс <xref:System.ServiceModel.BasicHttpBinding>.  
  
 В приведенной процедуре предполагается, что служба калькулятора выполняется. Сведения о создании службы, см. в разделе [как: Указание привязки службы в конфигурации](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md). Он также использует [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) предоставляет для автоматического создания компонентов клиента. Этот инструмент создает код клиента для доступа к службе.  
  
 Клиент создается в два этапа. Программа Svcutil.exe генерирует класс `ClientCalculator`, реализующий интерфейс `ICalculator`. Затем данное клиентское приложение создается путем создания экземпляра класса `ClientCalculator` и задания привязки и адреса для службы в коде.  
  
 Копию исходного кода в этом примере, см. в разделе [basicbinding обеспечением](../../../docs/framework/wcf/samples/basicbinding.md) образца.  
  
### <a name="to-specify-a-custom-binding-in-code"></a>Задание пользовательской привязки в коде  
  
1. Из командной строки запустите программу Svcutil.exe, чтобы создать код из метаданных службы.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2. Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. Создаваемый клиент также содержит реализацию класса `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. Создайте экземпляр класса `ClientCalculator`, использующего класс <xref:System.ServiceModel.BasicHttpBinding> в клиентском приложении, и вызовите операции службы по указанному адресу.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. Скомпилируйте и запустите клиент.  
  
## <a name="see-also"></a>См. также

- [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
