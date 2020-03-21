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
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="6857d-102">Учебник: Используйте клиент Фонда связи Windows</span><span class="sxs-lookup"><span data-stu-id="6857d-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="6857d-103">В этом уроке описана последняя из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6857d-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="6857d-104">Для обзора учебников [см.](getting-started-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="6857d-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="6857d-105">После того как вы создали и настроили прокси-сервер Windows Communication Foundation (WCF), вы создаете экземпляр клиента и компилируете клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="6857d-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="6857d-106">Затем вы используете его для связи с службой WCF.</span><span class="sxs-lookup"><span data-stu-id="6857d-106">You then use it to communicate with the WCF service.</span></span>

<span data-ttu-id="6857d-107">В этом руководстве описано следующее:</span><span class="sxs-lookup"><span data-stu-id="6857d-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="6857d-108">Добавьте код для использования клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="6857d-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="6857d-109">Проверьте клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="6857d-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="6857d-110">Добавление кода для использования клиента WCF</span><span class="sxs-lookup"><span data-stu-id="6857d-110">Add code to use the WCF client</span></span>

<span data-ttu-id="6857d-111">Код клиента делает следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="6857d-111">The client code does the following steps:</span></span>

- <span data-ttu-id="6857d-112">Множец клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="6857d-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="6857d-113">Вызывает операции службы из созданной учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="6857d-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="6857d-114">Закрывает клиента после завершения вызова операции.</span><span class="sxs-lookup"><span data-stu-id="6857d-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="6857d-115">Откройте файл **Program.cs** или **Module1.vb** из проекта **GettingStartedClient** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="6857d-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

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

<span data-ttu-id="6857d-116">Обратите `using` внимание на (для `Imports` Visual C) или (для Visual Basic) заявление, импорткоторое `GettingStartedClient.ServiceReference1`.</span><span class="sxs-lookup"><span data-stu-id="6857d-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="6857d-117">Это заявление импортирует код, созданный Visual Studio с функцией **Справки добавленной службы.**</span><span class="sxs-lookup"><span data-stu-id="6857d-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="6857d-118">Код мгновенно вызывает прокси WCF и вызывает каждую из операций службы, которые предоставляет служба калькулятора.</span><span class="sxs-lookup"><span data-stu-id="6857d-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="6857d-119">Затем он закрывает прокси и завершает программу.</span><span class="sxs-lookup"><span data-stu-id="6857d-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="6857d-120">Протестуйте клиента WCF</span><span class="sxs-lookup"><span data-stu-id="6857d-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="6857d-121">Протестируйте приложение от Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6857d-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="6857d-122">Сохраните решение и выполните его построение.</span><span class="sxs-lookup"><span data-stu-id="6857d-122">Save and build the solution.</span></span>

2. <span data-ttu-id="6857d-123">Выберите папку **GettingStartedLib,** а затем выберите **Set as Startup Project** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="6857d-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="6857d-124">Из **startup Projects**выберите **GettingStartedLib** из списка выпадающих, а затем выберите **Run** или нажмите **F5.**</span><span class="sxs-lookup"><span data-stu-id="6857d-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="6857d-125">Проверить приложение с помощью командного запроса</span><span class="sxs-lookup"><span data-stu-id="6857d-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="6857d-126">Откройте запрос команды в качестве администратора, а затем перейдите в каталог решений Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6857d-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span>

2. <span data-ttu-id="6857d-127">Для запуска сервиса: Введите *GettingStartedHost-bin-Debug-GettingStartedHost.exe*.</span><span class="sxs-lookup"><span data-stu-id="6857d-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="6857d-128">Для запуска клиента: откройте другую команду, перейдите в каталог решений Visual Studio, а затем введите *GettingStartedClient-bin-Debug-GettingStartedClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="6857d-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="6857d-129">*GettingStartedHost.exe* производит следующий выход:</span><span class="sxs-lookup"><span data-stu-id="6857d-129">*GettingStartedHost.exe* produces the following output:</span></span>

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

   <span data-ttu-id="6857d-130">*GettingStartedClient.exe* производит следующие выходы:</span><span class="sxs-lookup"><span data-stu-id="6857d-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="6857d-131">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="6857d-131">Next steps</span></span>

<span data-ttu-id="6857d-132">Теперь вы завершили все задачи в WCF начать учебник.</span><span class="sxs-lookup"><span data-stu-id="6857d-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="6857d-133">В этом руководстве вы узнали, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="6857d-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="6857d-134">В этом руководстве описано следующее:</span><span class="sxs-lookup"><span data-stu-id="6857d-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="6857d-135">Добавьте код для использования клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="6857d-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="6857d-136">Проверьте клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="6857d-136">Test the WCF client.</span></span>

<span data-ttu-id="6857d-137">Если у вас есть проблемы или ошибки в любом из шагов, выполните шаги в статье устранения неполадок, чтобы исправить их.</span><span class="sxs-lookup"><span data-stu-id="6857d-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6857d-138">Troubleshoot Начало начать с WCF учебники</span><span class="sxs-lookup"><span data-stu-id="6857d-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
