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
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="5cdf0-102">Учебник. Реализация контракта службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5cdf0-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="5cdf0-103">В данном учебнике второй из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5cdf0-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="5cdf0-104">Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="5cdf0-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="5cdf0-105">Следующий шаг по созданию приложения WCF является добавление кода для реализации интерфейса службы WCF, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="5cdf0-106">На этом шаге создается класс с именем `CalculatorService` , реализующий определяемый пользователем `ICalculator` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="5cdf0-107">Каждый метод в следующем коде вызывает операции калькулятора и записывает текст в консоль, чтобы проверить его.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="5cdf0-108">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="5cdf0-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="5cdf0-109">Добавление кода для реализации контракта службы WCF.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="5cdf0-110">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="5cdf0-111">Добавление кода для реализации контракта службы WCF</span><span class="sxs-lookup"><span data-stu-id="5cdf0-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="5cdf0-112">В **GettingStartedLib**откройте **Service1.cs** или **Service1.vb** файл и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="5cdf0-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="5cdf0-113">Редактирование App.config</span><span class="sxs-lookup"><span data-stu-id="5cdf0-113">Edit App.config</span></span>

<span data-ttu-id="5cdf0-114">Изменить **App.config** в **GettingStartedLib** для отражения изменений, внесенных в код.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>
   - <span data-ttu-id="5cdf0-115">Для визуального C# проектов:</span><span class="sxs-lookup"><span data-stu-id="5cdf0-115">For Visual C# projects:</span></span>
       - <span data-ttu-id="5cdf0-116">Измените строку 14 `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="5cdf0-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
       - <span data-ttu-id="5cdf0-117">Измените строку 17 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="5cdf0-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
       - <span data-ttu-id="5cdf0-118">Измените строку 22 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="5cdf0-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

   - <span data-ttu-id="5cdf0-119">Для проектов Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="5cdf0-119">For Visual Basic projects:</span></span>
       - <span data-ttu-id="5cdf0-120">Измените строку 14 `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="5cdf0-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
       - <span data-ttu-id="5cdf0-121">Измените строку 17 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="5cdf0-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
       - <span data-ttu-id="5cdf0-122">Измените строку 22 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="5cdf0-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>


## <a name="compile-the-code"></a><span data-ttu-id="5cdf0-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5cdf0-123">Compile the code</span></span>

<span data-ttu-id="5cdf0-124">Постройте решение, чтобы убедиться, что отсутствуют ошибки компиляции.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="5cdf0-125">Если вы используете Visual Studio на **построения** меню выберите **построить решение** (или нажмите клавишу **Ctrl**+**Shift** + **B**).</span><span class="sxs-lookup"><span data-stu-id="5cdf0-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5cdf0-126">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="5cdf0-126">Next steps</span></span>

<span data-ttu-id="5cdf0-127">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="5cdf0-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="5cdf0-128">Добавление кода для реализации контракта службы WCF.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="5cdf0-129">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-129">Build the solution.</span></span>

<span data-ttu-id="5cdf0-130">Перейдите к следующему руководству, чтобы узнать, как для запуска службы WCF.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5cdf0-131">Учебник. Размещение и запуск базовой службы WCF</span><span class="sxs-lookup"><span data-stu-id="5cdf0-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
