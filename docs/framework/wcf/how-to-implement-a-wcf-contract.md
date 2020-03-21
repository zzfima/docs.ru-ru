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
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="fe5b3-102">Учебник: Реализация контракта на обслуживание Фонда связи Windows</span><span class="sxs-lookup"><span data-stu-id="fe5b3-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="fe5b3-103">В этом уроке описана вторая из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fe5b3-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="fe5b3-104">Для обзора учебников [см.](getting-started-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="fe5b3-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="fe5b3-105">Следующим шагом для создания приложения WCF является добавление кода для реализации интерфейса службы WCF, созданного на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="fe5b3-106">На этом этапе вы `CalculatorService` создаете класс, названный, который реализует пользовательский `ICalculator` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="fe5b3-107">Каждый метод в следующем коде вызывает операцию калькулятора и записывает текст на консоль, чтобы протестировать его.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="fe5b3-108">В этом руководстве описано следующее:</span><span class="sxs-lookup"><span data-stu-id="fe5b3-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fe5b3-109">Добавьте код для реализации контракта на обслуживание WCF.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="fe5b3-110">Создайте решение.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="fe5b3-111">Добавление кода для реализации контракта на обслуживание WCF</span><span class="sxs-lookup"><span data-stu-id="fe5b3-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="fe5b3-112">В **GettingStartedLib**откройте файл **Service1.cs** или **Service1.vb** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="fe5b3-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="fe5b3-113">Edit App.config</span><span class="sxs-lookup"><span data-stu-id="fe5b3-113">Edit App.config</span></span>

<span data-ttu-id="fe5b3-114">Отображайте **App.config** в **GettingStartedLib,** чтобы отразить изменения, внесенные в код.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="fe5b3-115">Для проектов Visual C е:</span><span class="sxs-lookup"><span data-stu-id="fe5b3-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="fe5b3-116">Изменение строки 14 к`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="fe5b3-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="fe5b3-117">Изменение строки 17 к`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="fe5b3-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="fe5b3-118">Изменение строки от 22 до`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="fe5b3-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="fe5b3-119">Для проектов Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="fe5b3-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="fe5b3-120">Изменение строки 14 к`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="fe5b3-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="fe5b3-121">Изменение строки 17 к`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="fe5b3-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="fe5b3-122">Изменение строки от 22 до`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="fe5b3-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="fe5b3-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fe5b3-123">Compile the code</span></span>

<span data-ttu-id="fe5b3-124">Создайте решение для проверки ошибок компиляции.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="fe5b3-125">Если вы используете Visual Studio, в меню **Build** выберите **решение Build** (или нажмите **Ctrl**+**Shift**+**B).**</span><span class="sxs-lookup"><span data-stu-id="fe5b3-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe5b3-126">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fe5b3-126">Next steps</span></span>

<span data-ttu-id="fe5b3-127">В этом руководстве вы узнали, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="fe5b3-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fe5b3-128">Добавьте код для реализации контракта на обслуживание WCF.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="fe5b3-129">Создайте решение.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-129">Build the solution.</span></span>

<span data-ttu-id="fe5b3-130">Перейти к следующему учебнику, чтобы узнать, как запустить службу WCF.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fe5b3-131">Учебник: Хост и запустить базовую услугу WCF</span><span class="sxs-lookup"><span data-stu-id="fe5b3-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
