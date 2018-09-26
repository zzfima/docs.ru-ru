---
title: Практическое руководство. Использование клиента Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 12e911fb899cb85121c129b762828cdda01e64f1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112670"
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>Практическое руководство. Использование клиента Windows Communication Foundation

Это последняя из шести задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).

После создания и настройки прокси-сервера Windows Communication Foundation (WCF) можно создать экземпляр клиента и клиентское приложение можно скомпилировать и использовать для взаимодействия со службой WCF. В этом разделе описаны процедуры создания и использования клиента WCF. Эта процедура выполняет три операции.

1.  Создает экземпляр клиента WCF.

2.  Вызывает операции службы из созданной учетной записи-посредника.

3.  Закрывает клиент после завершения вызова операции.

## <a name="use-a-windows-communication-foundation-client"></a>Использование клиента Windows Communication Foundation

Откройте файл Program.cs или Program.vb из проекта GettingStartedClient и замените существующий код в файлах следующим:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            //Step 3: Closing the client gracefully closes the connection and cleans up resources.
            client.Close();
        }
    }
}
```

```vb
Imports System
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClientVB2.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy
        Dim Client As New CalculatorClient()

        'Step 2: Call the service operations.
        'Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        'Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        'Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        'Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Closing the client gracefully closes the connection and cleans up resources.
        Client.Close()

        Console.WriteLine()
        Console.WriteLine("Press <ENTER> to terminate client.")
        Console.ReadLine()

    End Sub

End Module
```

Обратите внимание, что `using` или `Imports` инструкцию, которая импортирует `GettingStartedClient.ServiceReference1`. Он импортирует код, сгенерированный **Add Service Reference** в Visual Studio. Код создает WCF-прокси и затем вызывает каждый из операции службы, предоставленные службой калькулятора, закрывает прокси и завершает.

Вы завершили работу с учебником. Был определен и реализован контракт службы, создан WCF-прокси, настроено клиентское приложение WCF, и использованы прокси для вызова операций службы. Чтобы проверить приложение, сначала запустите GettingStartedHost для запуска службы, а затем запустите GettingStartedClient.

Вывод из GettingStartedHost должен выглядеть следующим образом:

```text
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714
```

Вывод GettingStartedClient должен выглядеть следующим образом:

```text
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.
```

## <a name="see-also"></a>См. также

- [Создание клиентов](../../../docs/framework/wcf/building-clients.md)
- [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Руководство по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md)
- [Базовое программирование для WCF](../../../docs/framework/wcf/basic-wcf-programming.md)
- [Практическое руководство. Создание дуплексного контракта](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Практическое руководство. Доступ к службам с дуплексным контрактом](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)