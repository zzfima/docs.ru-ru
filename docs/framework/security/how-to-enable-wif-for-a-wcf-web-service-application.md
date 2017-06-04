---
title: "Практическое руководство. Включение WIF для приложения веб-службы WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Практическое руководство. Включение WIF для приложения веб-службы WCF
## Применение  
  
-   Microsoft® Windows® Identity Foundation \(WIF\)  
  
-   Microsoft® Windows® Communication Foundation \(WCF\)  
  
## Сводка  
 Это практическое руководство содержит пошаговые инструкции по включению WIF в веб\-службе WCF.  Оно также содержит инструкции по тестированию приложения для проверки того, что веб\-служба правильно представляет утверждения во время выполнения приложения.  В этом практическом руководстве нет подробных инструкций по созданию службы токенов безопасности \(STS\); вместо этого используется служба Development STS, входящая в состав средства Identity and Access Tool.  Служба Development STS не выполняет фактическую аутентификацию и предназначена только для тестирования.  Для выполнения этого практического руководства необходимо установить средство Identity and Access Tool.  Его можно загрузить на следующей странице: [Средство Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## Содержание  
  
-   Цели  
  
-   Обзор  
  
-   Сводка действий  
  
-   Шаг 1. Создание простой службы WCF  
  
-   Шаг 2. Создание клиентского приложения для службы WCF  
  
-   Шаг 3. Тестирование решения  
  
## Цели  
  
-   Создание службы WCF, требующей выданных токенов  
  
-   Создание клиента WCF, который запрашивает токен у службы STS и передает его в службу WCF  
  
## Обзор  
 Это практические предназначено для демонстрации порядка использования федеративной аутентификации при разработке служб WCF.  К преимуществам использования федерации в службах WCF относятся:  
  
1.  Факторизация логики аутентификации из кода службы WCF  
  
2.  Повторное использование существующих решений для управления удостоверениями  
  
3.  Взаимодействие с другими решениями для работы с удостоверениями  
  
4.  Гибкость и адаптивность к будущим изменениям  
  
 Платформа WIF и связанное с ней средство Identity and Access Tool упрощают разработку и тестирование службы WCF, использующей федеративную аутентификацию, как показано ниже.  
  
## Сводка действий  
  
-   Шаг 1. Создание простой службы WCF  
  
-   Шаг 2. Создание клиентского приложения для службы WCF  
  
-   Шаг 3. Тестирование решения  
  
## Шаг 1. Создание простой службы WCF  
 На этом шаге необходимо создать новую службу WCF, которая использует службу Development STS, входящую в средство Identity and Access Tool.  
  
#### Создание простой службы WCF  
  
1.  Запустите Visual Studio от имени администратора.  
  
2.  В Visual Studio в меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
3.  В окне **Новый проект** выберите **Приложение службы WCF**.  
  
4.  В поле **Имя** введите `TestService` и нажмите **ОК**.  
  
5.  В **Обозревателе решений** щелкните правой кнопкой мыши проект **TestService**, а затем выберите **Identity and Access**.  
  
6.  Будет открыто окно **Identity and Access**.  В поле **Providers** выберите **Test your application with the Local Development STS** и щелкните **Применить**.  Средство Identity and Access Tool настроит службу на использование WIF и на передачу аутентификации локальной службе Development STS \(**LocalSTS**\) путем добавления элементов конфигурации в файл *web.config*.  
  
7.  В файле *Service1.svc.cs* добавьте директиву `using` для пространства имен **System.Security.Claims** и замените существующий код следующим, а затем сохраните файл.  
  
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
  
     Метод `ComputeResponse` используется для отображения свойств различных утверждений, выдаваемых службой **LocalSTS**.  
  
8.  В файле *IService1.cs* замените существующий код следующим, а затем сохраните файл.  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. Выполните построение проекта.  
  
10. Нажмите сочетание клавиш **CTRL\+F5**, чтобы запустить службу без запуска отладчика.  Должна открыться веб\-страница службы; при этом можно убедиться, что запущена служба **LocalSTS**, проверив область уведомлений.  
  
    > [!IMPORTANT]
    >  Службы **TestService** и **LocalSTS** должны быть запущены при добавлении ссылки на службу в клиентское приложение на следующем шаге.  
  
## Шаг 2. Создание клиентского приложения для службы WCF  
 На этом шаге вы создадите консольное приложение, которое использует службу Development STS для аутентификации с использованием службы WCF, созданной на предыдущем шаге.  
  
#### Создание клиентского приложения  
  
1.  В Visual Studio щелкните решение правой кнопкой мыши, выберите команду **Добавить** и выберите пункт **Новый проект**.  
  
2.  В окне **Добавить новый проект** выберите **Консольное приложение** в списке шаблонов **Visual C\#**, введите `Client` и нажмите кнопку **ОК**.  В папке решения будет создан новый проект.  
  
3.  Щелкните правой кнопкой мыши элемент **Ссылки** в проекте **Клиент** и выберите **Добавить ссылку на службу**.  
  
4.  В окне **Добавление ссылки на службу** щелкните стрелку раскрывающегося списка на кнопке **Найти** и выберите пункт **Службы в решении**.  В поле **Адрес** будет автоматически подставлена созданная ранее служба WCF, а в поле **Пространство имен** будет подставлено значение **ServiceReference1**.  Нажмите кнопку **ОК**.  
  
    > [!IMPORTANT]
    >  Службы **TestService** и **LocalSTS** должны быть запущены при добавлении в клиент ссылки на службу.  
  
5.  Среда Visual Studio создаст прокси\-классы для службы WCF и добавит все необходимые ссылки.  Она также добавит элементы в файл *App.config*, чтобы настроить клиент на получение токена у службы STS для аутентификации в службе.  По завершении этого процесса будет открыт файл **Program.cs**.  Добавьте директиву `using` для пространств имен **System.ServiceModel** и **Client.ServiceReference1**, замените метод **Main** следующим кодом, а затем сохраните файл.  
  
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
  
6.  Откройте файл *App.config* и добавьте следующий код XML в качестве первого дочернего элемента внутри элемента `<system.serviceModel>`, а затем сохраните файл.  
  
    ```  
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
  
     Это приведет к отключению проверки сертификата.  
  
7.  Щелкните правой кнопкой мыши решение **TestService**, а затем выберите команду **Задать автозагружаемые проекты**.  Будет открыта страница свойств **Запускаемый проект**.  На странице свойств **Запускаемый проект** выберите **Несколько запускаемых проектов**, затем щелкните поле **Действие** для каждого проекта и выберите в раскрывающемся меню пункт **Запуск**.  Нажмите кнопку **ОК** для сохранения настроек.  
  
8.  Выполните сборку решения.  
  
## Шаг 3. Тестирование решения  
 На этом шаге вам предстоит протестировать приложение WCF с поддержкой WIF и убедиться, что утверждения представляются.  
  
#### Тестирование приложения WCF с поддержкой WIF на наличие утверждений  
  
1.  Нажмите клавишу **F5** для построения и запуска приложения.  Должно появиться окно консоли со следующим текстом: **Press Enter key to invoke service, any other key to quit application**.  
  
2.  Нажмите клавишу **ВВОД** и на консоли должна появиться следующая информация об утверждениях.  
  
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
    >  На момент нажатия клавиши **ВВОД** должны быть запущены службы **TestService** и **LocalSTS**.  Должна открыться веб\-страница службы; при этом можно убедиться, что запущена служба **LocalSTS**, проверив область уведомлений.  
  
3.  Если эти утверждения службы WCF отображаются на консоли, аутентификация в службе STS прошла успешно.