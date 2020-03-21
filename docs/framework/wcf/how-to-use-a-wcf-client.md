---
title: 'Учебник: Используйте клиент Фонда связи Windows'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d2357c134aef8da204dcdb19d6c1fc93cfdc068c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184012"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Учебник: Используйте клиент Фонда связи Windows

В этом уроке описана последняя из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Для обзора учебников [см.](getting-started-tutorial.md)

После того как вы создали и настроили прокси-сервер Windows Communication Foundation (WCF), вы создаете экземпляр клиента и компилируете клиентское приложение. Затем вы используете его для связи с службой WCF.

В этом руководстве описано следующее:
> [!div class="checklist"]
>
> - Добавьте код для использования клиента WCF.
> - Проверьте клиента WCF.

## <a name="add-code-to-use-the-wcf-client"></a>Добавление кода для использования клиента WCF

Код клиента делает следующие шаги:

- Множец клиента WCF.
- Вызывает операции службы из созданной учетной записи-посредника.
- Закрывает клиента после завершения вызова операции.

Откройте файл **Program.cs** или **Module1.vb** из проекта **GettingStartedClient** и замените его код следующим кодом:

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

Обратите `using` внимание на (для `Imports` Visual C) или (для Visual Basic) заявление, импорткоторое `GettingStartedClient.ServiceReference1`. Это заявление импортирует код, созданный Visual Studio с функцией **Справки добавленной службы.** Код мгновенно вызывает прокси WCF и вызывает каждую из операций службы, которые предоставляет служба калькулятора. Затем он закрывает прокси и завершает программу.

## <a name="test-the-wcf-client"></a>Протестуйте клиента WCF

### <a name="test-the-application-from-visual-studio"></a>Протестируйте приложение от Visual Studio

1. Сохраните решение и выполните его построение.

2. Выберите папку **GettingStartedLib,** а затем выберите **Set as Startup Project** из меню ярлыка.

3. Из **startup Projects**выберите **GettingStartedLib** из списка выпадающих, а затем выберите **Run** или нажмите **F5.**

### <a name="test-the-application-from-a-command-prompt"></a>Проверить приложение с помощью командного запроса

1. Откройте запрос команды в качестве администратора, а затем перейдите в каталог решений Visual Studio.

2. Для запуска сервиса: Введите *GettingStartedHost-bin-Debug-GettingStartedHost.exe*.

3. Для запуска клиента: откройте другую команду, перейдите в каталог решений Visual Studio, а затем введите *GettingStartedClient-bin-Debug-GettingStartedClient.exe*.

   *GettingStartedHost.exe* производит следующий выход:

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

   *GettingStartedClient.exe* производит следующие выходы:

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>Дальнейшие действия

Теперь вы завершили все задачи в WCF начать учебник. В этом руководстве вы узнали, как выполнять следующие задачи:

В этом руководстве описано следующее:
> [!div class="checklist"]
>
> - Добавьте код для использования клиента WCF.
> - Проверьте клиента WCF.

Если у вас есть проблемы или ошибки в любом из шагов, выполните шаги в статье устранения неполадок, чтобы исправить их.

> [!div class="nextstepaction"]
> [Troubleshoot Начало начать с WCF учебники](troubleshooting-the-getting-started-tutorial.md)
