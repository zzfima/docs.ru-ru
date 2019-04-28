---
title: Практическое руководство. Службы доступа с дуплексным контрактом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: 366fd9d6aa220bcbec1ee8fb2a04d1b84755800a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855144"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Практическое руководство. Службы доступа с дуплексным контрактом

Одной из функций Windows Communication Foundation (WCF) предоставляет возможность создать службу, использующую дуплексный шаблон обмена сообщениями. Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова. В этом разделе показаны шаги для создания клиентского класса, реализующего интерфейс обратного вызова клиента WCF.

Двойная привязка предоставляет службе IP-адрес клиента. Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.

Инструкции по созданию базовой службы WCF и клиента, см. в разделе [Приступая к работе](../../../../docs/framework/wcf/getting-started-tutorial.md).

## <a name="to-access-a-duplex-service"></a>Доступ к дуплексной службе

1. Создайте службу, содержащую два интерфейса. Первый интерфейс предназначен для службы, второй - для обратного вызова. Дополнительные сведения о создании дуплексной службы см. в разделе [как: Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).

2. Запустите службу.

3. Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контрактов (интерфейсы) для клиента. Сведения о том, как это сделать, см. в разделе [как: Создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).

4. Реализуйте в классе клиента интерфейс обратного вызова, как показано в следующем примере.

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. Создайте экземпляр класса <xref:System.ServiceModel.InstanceContext>. Конструктору требуется экземпляр класса клиента.

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. Создайте экземпляр клиента WCF с помощью конструктора, который требует <xref:System.ServiceModel.InstanceContext> объекта. Вторым параметром конструктора является имя конечной точки, определенное в файле конфигурации.

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. Вызовите методы класса клиента WCF, при необходимости.

## <a name="example"></a>Пример

В следующем примере кода показано, как создать класс клиента, обращающийся к дуплексному контракту.

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a>См. также

- [Руководство по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [Практическое руководство. Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Практическое руководство. Создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Практическое руководство. Использование ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
