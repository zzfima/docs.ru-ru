---
title: Учебник. Использование клиента Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: fa9aa3612a8dc72623fc4ea4b1ea337ac773fa26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928847"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Учебник. Использование клиента Windows Communication Foundation

В данном учебнике последнего из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF). Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).

После создания и настройки прокси-сервера Windows Communication Foundation (WCF) можно создать экземпляр клиента и Скомпилируйте клиентское приложение. Затем используется для взаимодействия со службой WCF. 

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> - Добавьте код, чтобы использовать клиент WCF.
> - Тестовый клиент WCF.

## <a name="add-code-to-use-the-wcf-client"></a>Добавьте код, чтобы использовать клиент WCF

Клиентский код выполняет следующие действия:
- Создает экземпляр клиента WCF.
- Вызывает операции службы из созданной учетной записи-посредника.
- Закрывает клиент после завершения вызова операции.

Откройте **Program.cs** или **Module1.vb** файла из **GettingStartedClient** проекта и замените его код следующим кодом:

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
Imports System
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

Обратите внимание, что `using` (для визуального C#) или `Imports` (для Visual Basic) инструкцию, которая импортирует `GettingStartedClient.ServiceReference1`. Эта инструкция импортирует код, созданный средой Visual Studio с **Add Service Reference** функции. Этот код создает экземпляр прокси-сервер WCF и вызывает каждый из операции службы, которые предоставляет служба калькулятора. Затем закрывает прокси и завершает выполнение программы.

## <a name="test-the-wcf-client"></a>Тестовый клиент WCF

### <a name="test-the-application-from-visual-studio"></a>Тестирование приложения из Visual Studio

1. Сохраните и выполните сборку решения.

2. Выберите **GettingStartedLib** папку, а затем выберите **Назначить запускаемым проектом** в контекстном меню.

3. Из **запускаемых проектов**выберите **GettingStartedLib** стрелку раскрывающегося списка, а затем нажмите **запуска** или нажмите клавишу **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Тестирование приложения из командной строки

1. Откройте командную строку от имени администратора и перейдите в каталог решения Visual Studio. 

2. Чтобы запустить службу: Введите *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.

3. Чтобы запустить клиент: Откройте другую командную строку, перейдите в каталог решения Visual Studio, а затем введите *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.

   *GettingStartedHost.exe* выводит следующие результаты:

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

   *GettingStartedClient.exe* выводит следующие результаты:

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>Следующие шаги

Теперь вы выполнили все задачи в WCF пособие по началу работы. В этом руководстве вы узнали, как:

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> - Добавьте код, чтобы использовать клиент WCF.
> - Тестовый клиент WCF.

При наличии проблем или ошибок в любом из шагов, следуйте указаниям в статье об устранении неполадок для их исправления.

> [!div class="nextstepaction"]
> [Устранение неполадок с Get к работе с WCF учебники](troubleshooting-the-getting-started-tutorial.md)
