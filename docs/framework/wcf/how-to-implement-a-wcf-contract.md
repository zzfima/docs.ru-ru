---
title: Учебник. Реализация контракта службы Windows Communication Foundation
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fcf96af11bae701585acd92001c8000125858449
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410086"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Учебник. Реализация контракта службы Windows Communication Foundation

В данном учебнике второй из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF). Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).

Следующий шаг по созданию приложения WCF является добавление кода для реализации интерфейса службы WCF, созданный на предыдущем шаге. На этом шаге создается класс с именем `CalculatorService` , реализующий определяемый пользователем `ICalculator` интерфейс. Каждый метод в следующем коде вызывает операции калькулятора и записывает текст в консоль, чтобы проверить его. 

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> - Добавление кода для реализации контракта службы WCF.
> - Постройте решение.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Добавление кода для реализации контракта службы WCF

В **GettingStartedLib**откройте **Service1.cs** или **Service1.vb** файл и замените его код следующим кодом:

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

## <a name="edit-appconfig"></a>Редактирование App.config

Изменить **App.config** в **GettingStartedLib** для отражения изменений, внесенных в код.
   - Для визуального C# проектов:
       - Измените строку 14 `<service name="GettingStartedLib.CalculatorService">`
       - Измените строку 17 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
       - Измените строку 22 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

   - Для проектов Visual Basic:
       - Измените строку 14 `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
       - Измените строку 17 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
       - Измените строку 22 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`


## <a name="compile-the-code"></a>Компиляция кода

Постройте решение, чтобы убедиться, что отсутствуют ошибки компиляции. Если вы используете Visual Studio на **построения** меню выберите **построить решение** (или нажмите клавишу **Ctrl**+**Shift** + **B**).

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> - Добавление кода для реализации контракта службы WCF.
> - Постройте решение.

Перейдите к следующему руководству, чтобы узнать, как для запуска службы WCF.

> [!div class="nextstepaction"]
> [Учебник. Размещение и запуск базовой службы WCF](how-to-host-and-run-a-basic-wcf-service.md)
