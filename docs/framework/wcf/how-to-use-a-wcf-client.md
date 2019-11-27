---
title: Учебник. Использование клиента Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d0ef525db16b2b2cedeea5fa03376fb4f3489a4a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346774"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Учебник. Использование клиента Windows Communication Foundation

В этом руководстве описываются пять задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Общие сведения о учебниках см. в разделе [учебник. Начало работы с Windows Communication Foundation приложениями](getting-started-tutorial.md).

После создания и настройки прокси-сервера Windows Communication Foundation (WCF) необходимо создать экземпляр клиента и скомпилировать клиентское приложение. Затем его можно использовать для взаимодействия со службой WCF. 

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
>
> - Добавьте код для использования клиента WCF.
> - Протестируйте клиент WCF.

## <a name="add-code-to-use-the-wcf-client"></a>Добавление кода для использования клиента WCF

Клиентский код выполняет следующие действия:

- Создает экземпляр клиента WCF.
- Вызывает операции службы из созданной учетной записи-посредника.
- Закрывает клиент после завершения вызова операции.

Откройте файл **Program.CS** или **Module1. vb** из проекта **GettingStartedClient** и замените его код следующим кодом:

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

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

Обратите внимание на инструкцию C#`using` (для Visual) или `Imports` (для Visual Basic), которая импортирует `GettingStartedClient.ServiceReference1`. Эта инструкция импортирует код, созданный Visual Studio с помощью функции **Добавление ссылки на службу** . Код создает прокси-сервер WCF и вызывает каждую из операций службы, предоставляемых службой калькулятора. Затем он закрывает прокси-сервер и завершает программу.

## <a name="test-the-wcf-client"></a>Тестирование клиента WCF

### <a name="test-the-application-from-visual-studio"></a>Тестирование приложения из Visual Studio

1. Сохраните и создайте решение.

2. Выберите папку **жеттингстартедлиб** , а затем в контекстном меню выберите **Назначить запускаемым проектом** .

3. В **меню запускаемые проекты**выберите **жеттингстартедлиб** из раскрывающегося списка, а затем выберите **выполнить** или нажмите клавишу **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Тестирование приложения из командной строки

1. Откройте командную строку от имени администратора и перейдите к каталогу решения Visual Studio. 

2. Чтобы запустить службу, введите *жеттингстартедхост\бин\дебуг\жеттингстартедхост.ЕКСЕ*.

3. Чтобы запустить клиент: Откройте еще одну командную строку, перейдите в каталог решения Visual Studio и введите *жеттингстартедклиент\бин\дебуг\жеттингстартедклиент.ЕКСЕ*.

   *GettingStartedHost. exe* выдает следующие выходные данные:

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   *GettingStartedClient. exe* выдает следующие выходные данные:

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>Следующие шаги

Теперь вы выполнили все задачи в руководстве по началу работы с WCF. В этом руководстве вы узнали, как:

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
>
> - Добавьте код для использования клиента WCF.
> - Протестируйте клиент WCF.

При возникновении проблем или ошибок во всех шагах выполните действия, описанные в статье Устранение неполадок, чтобы устранить их.

> [!div class="nextstepaction"]
> [Устранение неполадок в учебниках Приступая к работе с WCF](troubleshooting-the-getting-started-tutorial.md)
