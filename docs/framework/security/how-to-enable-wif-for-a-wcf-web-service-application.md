---
title: Практическое руководство. Включение WIF для приложения веб-службы WCF
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 71897299d68c2f0e43def8e70730ea456d6e9e24
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43564721"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a><span data-ttu-id="d222f-102">Практическое руководство. Включение WIF для приложения веб-службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-102">How To: Enable WIF for a WCF Web Service Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="d222f-103">Применение</span><span class="sxs-lookup"><span data-stu-id="d222f-103">Applies To</span></span>  
  
-   <span data-ttu-id="d222f-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="d222f-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="d222f-105">Microsoft® Windows® Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="d222f-105">Microsoft® Windows® Communication Foundation (WCF)</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d222f-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="d222f-106">Summary</span></span>  
 <span data-ttu-id="d222f-107">Это практическое руководство содержит пошаговые инструкции по включению WIF в веб-службе WCF.</span><span class="sxs-lookup"><span data-stu-id="d222f-107">This How-To provides detailed step-by-step procedures for enabling WIF in a WCF web service.</span></span> <span data-ttu-id="d222f-108">Оно также содержит инструкции по тестированию приложения для проверки того, что веб-служба правильно представляет утверждения во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="d222f-108">It also provides instructions for how to test the application to verify that the web service is correctly presenting claims when the application is run.</span></span> <span data-ttu-id="d222f-109">В этом практическом руководстве нет подробных инструкций по созданию службы токенов безопасности (STS); вместо этого используется служба Development STS, входящая в состав средства Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="d222f-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="d222f-110">Служба Development STS не выполняет фактическую аутентификацию и предназначена только для тестирования.</span><span class="sxs-lookup"><span data-stu-id="d222f-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="d222f-111">Для выполнения этого практического руководства необходимо установить средство Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="d222f-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="d222f-112">Его можно скачать на следующей странице: [Средство Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="d222f-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="d222f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d222f-113">Contents</span></span>  
  
-   <span data-ttu-id="d222f-114">Цели</span><span class="sxs-lookup"><span data-stu-id="d222f-114">Objectives</span></span>  
  
-   <span data-ttu-id="d222f-115">Обзор</span><span class="sxs-lookup"><span data-stu-id="d222f-115">Overview</span></span>  
  
-   <span data-ttu-id="d222f-116">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="d222f-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d222f-117">Шаг 1. Создание простой службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-117">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="d222f-118">Шаг 2. Создание клиентского приложения для службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-118">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="d222f-119">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="d222f-119">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="d222f-120">Цели</span><span class="sxs-lookup"><span data-stu-id="d222f-120">Objectives</span></span>  
  
-   <span data-ttu-id="d222f-121">Создание службы WCF, требующей выданных токенов</span><span class="sxs-lookup"><span data-stu-id="d222f-121">Create a WCF service that requires issued tokens</span></span>  
  
-   <span data-ttu-id="d222f-122">Создание клиента WCF, который запрашивает токен у службы STS и передает его в службу WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-122">Create a WCF client that requests a token from an STS and passes it to the WCF service</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d222f-123">Обзор</span><span class="sxs-lookup"><span data-stu-id="d222f-123">Overview</span></span>  
 <span data-ttu-id="d222f-124">Это практические предназначено для демонстрации порядка использования федеративной аутентификации при разработке служб WCF.</span><span class="sxs-lookup"><span data-stu-id="d222f-124">This How-To is intended to demonstrate how a developer can use federated authentication when developing WCF services.</span></span> <span data-ttu-id="d222f-125">К преимуществам использования федерации в службах WCF относятся:</span><span class="sxs-lookup"><span data-stu-id="d222f-125">Some of the benefits of using federation in WCF services include:</span></span>  
  
1.  <span data-ttu-id="d222f-126">Факторизация логики аутентификации из кода службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-126">Factoring authentication logic out of WCF service code</span></span>  
  
2.  <span data-ttu-id="d222f-127">Повторное использование существующих решений для управления удостоверениями</span><span class="sxs-lookup"><span data-stu-id="d222f-127">Re-using existing identity management solutions</span></span>  
  
3.  <span data-ttu-id="d222f-128">Взаимодействие с другими решениями для работы с удостоверениями</span><span class="sxs-lookup"><span data-stu-id="d222f-128">Interoperability with other identity solutions</span></span>  
  
4.  <span data-ttu-id="d222f-129">Гибкость и адаптивность к будущим изменениям</span><span class="sxs-lookup"><span data-stu-id="d222f-129">Flexibility and resilience to future changes</span></span>  
  
 <span data-ttu-id="d222f-130">Платформа WIF и связанное с ней средство Identity and Access Tool упрощают разработку и тестирование службы WCF, использующей федеративную аутентификацию, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d222f-130">WIF and the associated Identity and Access tool make it easier to develop and test a WCF service using federated authentication, as the following steps demonstrate.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="d222f-131">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="d222f-131">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d222f-132">Шаг 1. Создание простой службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-132">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="d222f-133">Шаг 2. Создание клиентского приложения для службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-133">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="d222f-134">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="d222f-134">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-wcf-service"></a><span data-ttu-id="d222f-135">Шаг 1. Создание простой службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-135">Step 1 – Create a Simple WCF Service</span></span>  
 <span data-ttu-id="d222f-136">На этом шаге необходимо создать новую службу WCF, которая использует службу Development STS, входящую в средство Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="d222f-136">In this step, you will create a new WCF service that uses the Development STS that is included with the Identity and Access tool.</span></span>  
  
#### <a name="to-create-a-simple-wcf-service"></a><span data-ttu-id="d222f-137">Создание простой службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-137">To create a simple WCF service</span></span>  
  
1.  <span data-ttu-id="d222f-138">Запустите Visual Studio от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="d222f-138">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="d222f-139">В Visual Studio в меню **Файл** последовательно выберите пункты **Создать** и **Проект**.</span><span class="sxs-lookup"><span data-stu-id="d222f-139">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d222f-140">В окне **Новый проект** выберите **Приложение службы WCF**.</span><span class="sxs-lookup"><span data-stu-id="d222f-140">In the **New Project** window, click **WCF Service Application**.</span></span>  
  
4.  <span data-ttu-id="d222f-141">В поле **Имя** введите `TestService` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d222f-141">In **Name**, enter `TestService` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="d222f-142">В **обозревателе решений** щелкните правой кнопкой мыши проект **TestService**, а затем выберите **Идентификация и доступ**.</span><span class="sxs-lookup"><span data-stu-id="d222f-142">Right-click the **TestService** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="d222f-143">Откроется окно **Идентификация и доступ**.</span><span class="sxs-lookup"><span data-stu-id="d222f-143">The **Identity and Access** window appears.</span></span> <span data-ttu-id="d222f-144">В поле **Поставщики** выберите **Протестировать приложение с помощью локальной службы Development STS** и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="d222f-144">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span> <span data-ttu-id="d222f-145">Средство Identity and Access Tool настроит службу для использования WIF и передачи проверки подлинности локальной службе Development STS (**LocalSTS**), добавив необходимые параметры в файл конфигурации *Web.config*.</span><span class="sxs-lookup"><span data-stu-id="d222f-145">The Identity and Access Tool configures the service to use WIF and to outsource authentication to the local development STS (**LocalSTS**) by adding configuration elements to the *Web.config* file.</span></span>  
  
7.  <span data-ttu-id="d222f-146">В файле *Service1.svc.cs* добавьте директиву `using` для пространства имен **System.Security.Claims** и замените существующий код на следующий, а затем сохраните файл:</span><span class="sxs-lookup"><span data-stu-id="d222f-146">In the *Service1.svc.cs* file, add a `using` directive for the **System.Security.Claims** namespace and replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     <span data-ttu-id="d222f-147">Метод `ComputeResponse` используется для отображения свойств различных утверждений, выдаваемых службой **LocalSTS**.</span><span class="sxs-lookup"><span data-stu-id="d222f-147">The `ComputeResponse` method displays the properties of various claims that are issued by **LocalSTS**.</span></span>  
  
8.  <span data-ttu-id="d222f-148">В файле *IService1.cs* замените существующий код на следующий, а затем сохраните файл:</span><span class="sxs-lookup"><span data-stu-id="d222f-148">In the *IService1.cs* file, replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. <span data-ttu-id="d222f-149">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="d222f-149">Build the project.</span></span>  
  
10. <span data-ttu-id="d222f-150">Нажмите **CTRL+F5**, чтобы запустить службу без запуска отладчика.</span><span class="sxs-lookup"><span data-stu-id="d222f-150">Press **Ctrl-F5** to run the service without starting the debugger.</span></span> <span data-ttu-id="d222f-151">Должна открыться веб-страница службы; в области уведомлений можно убедиться, что запущена служба **LocalSTS**.</span><span class="sxs-lookup"><span data-stu-id="d222f-151">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d222f-152">Службы **TestService** и **LocalSTS** должны быть запущены во время добавления ссылки на службу в клиентское приложение на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="d222f-152">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client application in the next step.</span></span>  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a><span data-ttu-id="d222f-153">Шаг 2. Создание клиентского приложения для службы WCF</span><span class="sxs-lookup"><span data-stu-id="d222f-153">Step 2 – Create a Client Application for the WCF Service</span></span>  
 <span data-ttu-id="d222f-154">На этом шаге вы создадите консольное приложение, которое использует службу Development STS для аутентификации с использованием службы WCF, созданной на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="d222f-154">In this step, you will create a console application that uses the Development STS to authenticate with the WCF service you created in the previous step.</span></span>  
  
#### <a name="to-create-a-client-application"></a><span data-ttu-id="d222f-155">Создание клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="d222f-155">To create a client application</span></span>  
  
1.  <span data-ttu-id="d222f-156">В Visual Studio щелкните решение правой кнопкой мыши, выберите **Добавить** и затем **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="d222f-156">In Visual Studio, right-click on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="d222f-157">В окне **Добавление нового проекта** выберите **Консольное приложение** в списке шаблонов **Visual C#**, введите `Client` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d222f-157">In the **Add New Project** window, select **Console Application** from the **Visual C#** templates list, enter `Client`, and then press **OK**.</span></span> <span data-ttu-id="d222f-158">В папке решения будет создан новый проект.</span><span class="sxs-lookup"><span data-stu-id="d222f-158">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="d222f-159">Щелкните правой кнопкой мыши элемент **Ссылки** в проекте **Клиент** и выберите **Добавить ссылку на службу**.</span><span class="sxs-lookup"><span data-stu-id="d222f-159">Right-click on **References** under the **Client** project, and then click **Add Service Reference**.</span></span>  
  
4.  <span data-ttu-id="d222f-160">В окне **Добавление ссылки на службу** щелкните стрелку раскрывающегося списка на кнопке **Найти** и выберите **Службы в решении**.</span><span class="sxs-lookup"><span data-stu-id="d222f-160">In the **Add Service Reference** window, click the drop-down arrow on the **Discover** button and click **Services in Solution**.</span></span> <span data-ttu-id="d222f-161">В поле **Адрес** будет автоматически указана созданная ранее служба WCF, а в поле **Пространство имен** будет указано значение **ServiceReference1**.</span><span class="sxs-lookup"><span data-stu-id="d222f-161">The **Address** will automatically populate with the WCF service you created earlier, and the **Namespace** will be set to **ServiceReference1**.</span></span> <span data-ttu-id="d222f-162">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d222f-162">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d222f-163">Службы **TestService** и **LocalSTS** должны быть запущены во время добавления ссылки на службу в клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="d222f-163">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client.</span></span>  
  
5.  <span data-ttu-id="d222f-164">Среда Visual Studio создаст прокси-классы для службы WCF и добавит все необходимые ссылки.</span><span class="sxs-lookup"><span data-stu-id="d222f-164">Visual Studio will generate proxy classes for the WCF service, and add all of the necessary reference information.</span></span> <span data-ttu-id="d222f-165">Она также добавит необходимые параметры в файл *App.config*, чтобы клиент получал маркер у службы STS для проверки подлинности в службе.</span><span class="sxs-lookup"><span data-stu-id="d222f-165">It will also add elements to the *App.config* file to configure the client to get a token from the STS to authenticate with the service.</span></span> <span data-ttu-id="d222f-166">После окончания этого процесса будет открыт файл **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="d222f-166">When this process is finished, the **Program.cs** file will open.</span></span> <span data-ttu-id="d222f-167">Добавьте директиву `using` для пространств имен **System.ServiceModel** и **Client.ServiceReference1**, замените метод **Main** на следующий код, а затем сохраните файл:</span><span class="sxs-lookup"><span data-stu-id="d222f-167">Add a `using` directive for **System.ServiceModel** and another for **Client.ServiceReference1**, replace the **Main** method with the following code, then save the file:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  <span data-ttu-id="d222f-168">Откройте файл *App.config* и добавьте следующий код XML в качестве первого дочернего элемента внутри элемента `<system.serviceModel>`, а затем сохраните файл:</span><span class="sxs-lookup"><span data-stu-id="d222f-168">Open the *App.config* file and add the following XML as the first child element under the `<system.serviceModel>` element, then save the file:</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     <span data-ttu-id="d222f-169">Это приведет к отключению проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="d222f-169">This disables certificate validation.</span></span>  
  
7.  <span data-ttu-id="d222f-170">Щелкните правой кнопкой мыши решение **TestService**, а затем выберите команду **Назначить запускаемые проекты**.</span><span class="sxs-lookup"><span data-stu-id="d222f-170">Right-click the **TestService** solution and click on **Set StartUp Projects**.</span></span> <span data-ttu-id="d222f-171">Будет открыта страница свойств **Запускаемый проект**.</span><span class="sxs-lookup"><span data-stu-id="d222f-171">The **Startup Project** property page opens.</span></span> <span data-ttu-id="d222f-172">На странице свойств **Запускаемый проект** выберите **Несколько запускаемых проектов**, затем щелкните поле **Действие** для каждого проекта и выберите **Запуск** в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="d222f-172">In the **Startup Project** property page, select **Multiple startup projects** then click in the **Action** field for each project and select **Start** from the drop-down menu.</span></span> <span data-ttu-id="d222f-173">Нажмите кнопку **ОК**, чтобы сохранить параметры.</span><span class="sxs-lookup"><span data-stu-id="d222f-173">Click **OK** to save the settings.</span></span>  
  
8.  <span data-ttu-id="d222f-174">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="d222f-174">Build the solution.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="d222f-175">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="d222f-175">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="d222f-176">На этом шаге вам предстоит протестировать приложение WCF с поддержкой WIF и убедиться, что утверждения представляются.</span><span class="sxs-lookup"><span data-stu-id="d222f-176">In this step you will test your WIF-enabled WCF application and verify that claims are presented.</span></span>  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a><span data-ttu-id="d222f-177">Тестирование приложения WCF с поддержкой WIF на наличие утверждений</span><span class="sxs-lookup"><span data-stu-id="d222f-177">To test your WIF-enabled WCF application for claims</span></span>  
  
1.  <span data-ttu-id="d222f-178">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d222f-178">Press **F5** to build and run the application.</span></span> <span data-ttu-id="d222f-179">Должно появиться окно консоли со следующим текстом: **Нажмите клавишу ВВОД, чтобы вызвать службу, или любую другую клавишу для выхода из приложения:**</span><span class="sxs-lookup"><span data-stu-id="d222f-179">You should be presented with a console window, and the following text: **Press Enter key to invoke service, any other key to quit application:**</span></span>  
  
2.  <span data-ttu-id="d222f-180">Нажмите клавишу **ВВОД**, и в окне консоли появится следующая информация об утверждениях:</span><span class="sxs-lookup"><span data-stu-id="d222f-180">Press **Enter**, and the following claims information should appear in the console:</span></span>  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d222f-181">Перед нажатием клавиши **ВВОД** должны быть запущены службы **TestService** и **LocalSTS**.</span><span class="sxs-lookup"><span data-stu-id="d222f-181">Both **TestService** and **LocalSTS** must be running before you press **Enter**.</span></span> <span data-ttu-id="d222f-182">Должна открыться веб-страница службы; в области уведомлений можно убедиться, что запущена служба **LocalSTS**.</span><span class="sxs-lookup"><span data-stu-id="d222f-182">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
3.  <span data-ttu-id="d222f-183">Если эти утверждения службы WCF отображаются на консоли, аутентификация в службе STS прошла успешно.</span><span class="sxs-lookup"><span data-stu-id="d222f-183">If these claims appear in the console, you have successfully authenticated with the STS to display claims from the WCF service.</span></span>
