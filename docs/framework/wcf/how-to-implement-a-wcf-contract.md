---
title: 'Учебник: Реализация контракта на обслуживание Фонда связи Windows'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184072"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Учебник: Реализация контракта на обслуживание Фонда связи Windows

В этом уроке описана вторая из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Для обзора учебников [см.](getting-started-tutorial.md)

Следующим шагом для создания приложения WCF является добавление кода для реализации интерфейса службы WCF, созданного на предыдущем этапе. На этом этапе вы `CalculatorService` создаете класс, названный, который реализует пользовательский `ICalculator` интерфейс. Каждый метод в следующем коде вызывает операцию калькулятора и записывает текст на консоль, чтобы протестировать его.

В этом руководстве описано следующее:
> [!div class="checklist"]
>
> - Добавьте код для реализации контракта на обслуживание WCF.
> - Создайте решение.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Добавление кода для реализации контракта на обслуживание WCF

В **GettingStartedLib**откройте файл **Service1.cs** или **Service1.vb** и замените его код следующим кодом:

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a>Edit App.config

Отображайте **App.config** в **GettingStartedLib,** чтобы отразить изменения, внесенные в код.

- Для проектов Visual C е:
  - Изменение строки 14 к`<service name="GettingStartedLib.CalculatorService">`
  - Изменение строки 17 к`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Изменение строки от 22 до`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Для проектов Visual Basic:
  - Изменение строки 14 к`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Изменение строки 17 к`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Изменение строки от 22 до`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Компиляция кода

Создайте решение для проверки ошибок компиляции. Если вы используете Visual Studio, в меню **Build** выберите **решение Build** (или нажмите **Ctrl**+**Shift**+**B).**

## <a name="next-steps"></a>Дальнейшие действия

В этом руководстве вы узнали, как выполнять следующие задачи:
> [!div class="checklist"]
>
> - Добавьте код для реализации контракта на обслуживание WCF.
> - Создайте решение.

Перейти к следующему учебнику, чтобы узнать, как запустить службу WCF.

> [!div class="nextstepaction"]
> [Учебник: Хост и запустить базовую услугу WCF](how-to-host-and-run-a-basic-wcf-service.md)
