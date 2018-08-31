---
title: Как создать службу рабочих процессов, которая вызывает другую службу рабочих процессов
ms.date: 03/30/2017
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
ms.openlocfilehash: 1b30da34f7c85cccd98b18cd32b81c83630989b2
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258362"
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="8b1b8-102">Как создать службу рабочих процессов, которая вызывает другую службу рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8b1b8-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>

<span data-ttu-id="8b1b8-103">Иногда службе рабочего процесса требуется получить данные от другой службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span> <span data-ttu-id="8b1b8-104">В этом разделе описывается, как вызвать одну службу рабочего процесса из другой.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="8b1b8-105">В этом разделе мы создадим две службы рабочего процесса (одну с методом, который обращает входную строку, и вторую, которая преобразует входную строку в верхний регистр после обращения строки, которая использует первую службу).</span><span class="sxs-lookup"><span data-stu-id="8b1b8-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>

### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="8b1b8-106">Создание службы рабочего процесса Reverser</span><span class="sxs-lookup"><span data-stu-id="8b1b8-106">To create the Reverser workflow service</span></span>

1.  <span data-ttu-id="8b1b8-107">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-107">Open Visual Studio.</span></span>

2.  <span data-ttu-id="8b1b8-108">Выберите **файл** > **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-108">Select **File** > **New Project**.</span></span> <span data-ttu-id="8b1b8-109">В разделе **рабочего процесса** узел в **установленные шаблоны** области выберите **приложение службы рабочего процесса WCF**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="8b1b8-110">Назовите решение `NestedServices` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-110">Name the solution `NestedServices` and then click **OK**.</span></span>

3.  <span data-ttu-id="8b1b8-111">В разделе **серверы**, убедитесь, что **использовать локальный веб-сервер IIS** выбран.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="8b1b8-112">Нажмите кнопку **создать виртуальный каталог**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="8b1b8-113">Нажмите кнопку **ОК** в диалоговое окно с предупреждением, виртуальный каталог был успешно создан.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>

4.  <span data-ttu-id="8b1b8-114">В обозревателе решений переименуйте файл Service1.xamlx в `StringReverserService.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>

5.  <span data-ttu-id="8b1b8-115">На **свойства проекта** для нового проекта и щелкните **Web** вкладки. Задайте **действие при запуске** для **определенную страницу**и выберите StringReverserService.xamlx в качестве стартовой страницы.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>

6.  <span data-ttu-id="8b1b8-116">Откройте файл StringReverserService.xamlx в конструкторе и удалите существующие действия `ReceiveRequest` и `SendReply`, затем перетащите действие `ReceiveAndSendReply` в существующее действие последовательности.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>

    1.  <span data-ttu-id="8b1b8-117">Задайте **Имя_операции** задайте значение ReverseString.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-117">Set the **OperationName** to ReverseString.</span></span>

    2.  <span data-ttu-id="8b1b8-118">Задайте **ServiceContractName** задайте значение IReverseString.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-118">Set the **ServiceContractName** to IReverseString.</span></span>

    3.  <span data-ttu-id="8b1b8-119">Выберите **CanCreateInstance** "флажок".</span><span class="sxs-lookup"><span data-stu-id="8b1b8-119">Select the **CanCreateInstance** check box.</span></span>

7.  <span data-ttu-id="8b1b8-120">Выберите **SequentialService** действия, а затем щелкните **переменных** вкладку в нижней части конструктора.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="8b1b8-121">Создайте две новые переменные типа String с именами StringToReverse и ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>

8.  <span data-ttu-id="8b1b8-122">Нажмите кнопку **определить** ссылку в **Receive** действия.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="8b1b8-123">Нажмите кнопку **параметры**и создайте параметр с именем InputString, назначенный StringToReverse строкового типа.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>

9. <span data-ttu-id="8b1b8-124">Нажмите кнопку **определить** ссылку в **SendReplyToReceive** действия.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="8b1b8-125">Нажмите кнопку **параметры**и создайте параметр с именем ReversedString типа String, назначенный ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>

10. <span data-ttu-id="8b1b8-126">Чтобы реализовать логику для службы, создайте в проекте новый класс с именем StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="8b1b8-127">Замените определение класса на следующий код.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-127">Replace the class definition with the following code.</span></span>

    ```
    public class StringLibrary
        {
            public static String ReverseString(string StringToReverse)
            {
                char[] charArray = StringToReverse.ToCharArray();
                Array.Reverse(charArray);
                return new String(charArray);
            }
        }
    ```

11. <span data-ttu-id="8b1b8-128">Чтобы вызвать метод reversestring при вводе, перетащите **InvokeMethod** действия из области элементов в пространство между **Receive** и **SendReply** действий.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="8b1b8-129">Установите свойства действия следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-129">Set the properties of the activity as follows:</span></span>

    1.  <span data-ttu-id="8b1b8-130">**Имя_метода**: значение ReverseString</span><span class="sxs-lookup"><span data-stu-id="8b1b8-130">**MethodName**: ReverseString</span></span>

    2.  <span data-ttu-id="8b1b8-131">**Результат**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="8b1b8-131">**Result**: ReversedStringToReturn</span></span>

    3.  <span data-ttu-id="8b1b8-132">**Параметры**: создайте новый параметр, где **направление** имеет значение In, **тип** строки и **значение** ― StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>

    4.  <span data-ttu-id="8b1b8-133">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="8b1b8-133">**TargetType**: NestedServices.StringLibrary</span></span>

12. <span data-ttu-id="8b1b8-134">Проверьте службу, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-134">Test the service by pressing F5.</span></span> <span data-ttu-id="8b1b8-135">В открывшемся клиенте теста WCF дважды щелкните метод ReverseString().</span><span class="sxs-lookup"><span data-stu-id="8b1b8-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="8b1b8-136">В области запросов введите `Sample` для значения параметра InputString.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="8b1b8-137">Нажмите кнопку **вызова**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-137">Click **Invoke**.</span></span> <span data-ttu-id="8b1b8-138">Служба должна вернуть «elpmaS».</span><span class="sxs-lookup"><span data-stu-id="8b1b8-138">The service should return "elpmaS".</span></span>

### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="8b1b8-139">Создание службы рабочего процесса UpperCaser</span><span class="sxs-lookup"><span data-stu-id="8b1b8-139">To create the UpperCaser workflow service</span></span>

1.  <span data-ttu-id="8b1b8-140">Щелкните проект NestedServices правой кнопкой мыши и выберите **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-140">Right-click the NestedServices project and select **Add** > **New Item**.</span></span> <span data-ttu-id="8b1b8-141">В **рабочего процесса** выберите **службы WCF Workflow Service**и присвойте имя новой службы `UpperCaserService`.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="8b1b8-142">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-142">Click **Add**.</span></span> <span data-ttu-id="8b1b8-143">После этого в проект должна будет быть добавлена новая служба рабочего процесса с именем UpperCaserService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>

2.  <span data-ttu-id="8b1b8-144">Откройте файл UpperCaserService.xamlx в конструкторе и удалите существующие **ReceiveRequest** и `SendReply` , после чего перетащите `ReceiveAndSendReply` действия в существующее действие последовательности.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>

    1.  <span data-ttu-id="8b1b8-145">Задайте **Имя_операции** задайте значение UpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-145">Set the **OperationName** to UpperCaseString.</span></span>

    2.  <span data-ttu-id="8b1b8-146">Задайте **ServiceContractName** задайте значение IUpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>

    3.  <span data-ttu-id="8b1b8-147">Выберите **CanCreateInstance** "флажок".</span><span class="sxs-lookup"><span data-stu-id="8b1b8-147">Select the **CanCreateInstance** check box.</span></span>

3.  <span data-ttu-id="8b1b8-148">Выберите действие SequentialService, затем нажмите кнопку **переменных** вкладку в нижней части конструктора.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="8b1b8-149">Создайте три новые переменные типа String с именами StringToUpper, StringToReverse и StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>

4.  <span data-ttu-id="8b1b8-150">Нажмите кнопку **определить** ссылку в **Receive** действия.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="8b1b8-151">Нажмите кнопку **параметры**и создайте параметр с именем InputString, назначенный StringToUpper строкового типа.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>

5.  <span data-ttu-id="8b1b8-152">Нажмите кнопку **определить** ссылку в **SendReplyToReceive** действия.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="8b1b8-153">Нажмите кнопку **параметры**и создайте параметр с именем ModifiedString типа String, назначенный StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>

6.  <span data-ttu-id="8b1b8-154">Чтобы реализовать логику для службы, создайте в проекте с помощью следующего кода новый метод в классе StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>

    ```
    public static String UpperCaseString(string StringToUpperCase)
    {
         return StringToUpperCase.ToUpper();

    }
    ```

7.  <span data-ttu-id="8b1b8-155">Чтобы вызвать метод uppercasestring при вводе, перетащите **InvokeMethod** действия из области элементов в пространство между **Receive** и **SendReply** действий.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="8b1b8-156">Установите свойства действия следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-156">Set the properties of the activity as follows:</span></span>

    1.  <span data-ttu-id="8b1b8-157">**Имя_метода**: значение UpperCaseString</span><span class="sxs-lookup"><span data-stu-id="8b1b8-157">**MethodName**: UpperCaseString</span></span>

    2.  <span data-ttu-id="8b1b8-158">**Результат**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="8b1b8-158">**Result**: StringToReverse</span></span>

    3.  <span data-ttu-id="8b1b8-159">**Параметры**: создайте новый параметр, где **направление** имеет значение In, **тип** строки и **значение** ― StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>

    4.  <span data-ttu-id="8b1b8-160">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="8b1b8-160">**TargetType**: NestedServices.StringLibrary</span></span>

8.  <span data-ttu-id="8b1b8-161">Теперь для измененной строки мы вызовем первую службу.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="8b1b8-162">Щелкните правой кнопкой мыши проект и выберите **добавить** > **ссылки на службу**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-162">Right-click the project and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="8b1b8-163">Добавьте ссылку на службу http://localhost/NestedServices/StringReverserService.xamlx и постройте проект, чтобы создать настраиваемое действие для доступа к первой веб-службе.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>

9. <span data-ttu-id="8b1b8-164">Перетащите экземпляр нового действия рабочего процесса, между **InvokeMethod** действия и **SendReplyToReceive** действий.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="8b1b8-165">Назначьте переменную StringToReverse свойству InputString нового действия, а переменную StringToReturn ― свойству StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>

10. <span data-ttu-id="8b1b8-166">Откройте страницу свойств для проекта NestedServices и измените **определенную страницу** в **Web** вкладке значение uppercaserservice.xamlx.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>

11. <span data-ttu-id="8b1b8-167">Проверьте службу, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-167">Test the service by pressing F5.</span></span> <span data-ttu-id="8b1b8-168">В открывшемся клиенте теста WCF дважды щелкните метод ReverseString().</span><span class="sxs-lookup"><span data-stu-id="8b1b8-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="8b1b8-169">В области запросов введите `Sample` для значения параметра InputString.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="8b1b8-170">Нажмите кнопку **вызова**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-170">Click **Invoke**.</span></span> <span data-ttu-id="8b1b8-171">Служба должна вернуть «ELPMAS».</span><span class="sxs-lookup"><span data-stu-id="8b1b8-171">The service should return "ELPMAS".</span></span>

### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="8b1b8-172">Создание клиента для вызова служб</span><span class="sxs-lookup"><span data-stu-id="8b1b8-172">To create a client to call the services</span></span>

1.  <span data-ttu-id="8b1b8-173">Добавьте в решение новый проект консольного приложения с именем Client.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-173">Add a new Console application project called Client to the solution.</span></span>

2.  <span data-ttu-id="8b1b8-174">Щелкните правой кнопкой мыши клиентский проект и выберите **добавить** > **ссылки на службу**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-174">Right-click the Client project and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="8b1b8-175">В открывшемся окне щелкните **Discover**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="8b1b8-176">Выберите StringReverserService.xamlx и в качестве пространства имен введите ReverseService.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="8b1b8-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-177">Click **OK**.</span></span>

3.  <span data-ttu-id="8b1b8-178">Замените метод Main в файле Program.cs следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="8b1b8-178">Replace the Main method in Program.cs with the following code.</span></span>

    ```
    static void Main(string[] args)
    {
        Console.Write("Input string to process:");
        String input = Console.ReadLine();
        var service = new ReverseService.ReverseStringClient();
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));
        Console.ReadKey();
    }
    ```