---
title: Олицетворение клиента
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: e9e85729b10d1c992a22f6c0bea65dfd1e21e7e4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742551"
---
# <a name="impersonating-the-client"></a><span data-ttu-id="cfe4d-102">Олицетворение клиента</span><span class="sxs-lookup"><span data-stu-id="cfe4d-102">Impersonating the Client</span></span>
<span data-ttu-id="cfe4d-103">Пример олицетворения демонстрирует, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-103">The Impersonation sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>  
  
 <span data-ttu-id="cfe4d-104">Этот пример основан на образце с использованием [самообслуживания.](../../../../docs/framework/wcf/samples/self-host.md)</span><span class="sxs-lookup"><span data-stu-id="cfe4d-104">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span> <span data-ttu-id="cfe4d-105">Файлы конфигурации службы и клиента те же, что и в примере с [самостоятельным размещением](../../../../docs/framework/wcf/samples/self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="cfe4d-105">The service and client configuration files are the same as that of the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfe4d-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="cfe4d-107">Код службы был изменен таким образом, чтобы метод `Add` службы олицетворял абонента с помощью атрибута <xref:System.ServiceModel.OperationBehaviorAttribute>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-107">The service code has been modified such that the `Add` method on the service impersonates the caller using the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="cfe4d-108">В результате контекст безопасности выполняющегося потока переключается на олицетворение абонента перед вводом метода `Add` и возврата к выходу из метода.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-108">As a result, the security context of the executing thread is switched to impersonate the caller before entering the `Add` method and reverted on exiting the method.</span></span>  
  
 <span data-ttu-id="cfe4d-109">Метод `DisplayIdentityInformation`, показанный в следующем примере кода, является служебной функцией, отображающей идентификацию абонента.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-109">The `DisplayIdentityInformation` method shown in the following sample code is a utility function that displays the caller's identity.</span></span>  
  
```csharp
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",   
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 <span data-ttu-id="cfe4d-110">Метод `Subtract` службы олицетворяет абонента с помощью принудительных вызовов, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-110">The `Subtract` method on the service impersonates the caller using imperative calls as shown in the following sample code.</span></span>  
  
```csharp
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    Console.WriteLine("Before impersonating");  
    DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs   
            // on the system resource are enforced in the caller's context.   
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
    Console.WriteLine("After reverting");  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="cfe4d-111">Обратите внимание, что в данном случае абонент не олицетворяется для всего звонка, а только для его части.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-111">Note that in this case the caller is not impersonated for the entire call but is only impersonated for a portion of the call.</span></span> <span data-ttu-id="cfe4d-112">В общем, олицетворение небольшой части операции предпочтительнее, чем олицетворение всей операции.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-112">In general, impersonating for the smallest scope is preferable to impersonating for the entire operation.</span></span>  
  
 <span data-ttu-id="cfe4d-113">Другие методы не олицетворяют абонента.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-113">The other methods do not impersonate the caller.</span></span>  
  
 <span data-ttu-id="cfe4d-114">Клиентский код изменен, чтобы уровень олицетворения был установлен в значение <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-114">The client code has been modified to set the impersonation level to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span></span> <span data-ttu-id="cfe4d-115">Клиент задает уровень олицетворения, который будет использоваться службой с помощью перечисления <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-115">The client specifies the impersonation level to be used by the service, by using the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration.</span></span> <span data-ttu-id="cfe4d-116">Перечисление поддерживает следующие значения: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> и <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-116">The enumeration supports the following values: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> and <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span></span> <span data-ttu-id="cfe4d-117">Чтобы выполнить проверку доступа при получении доступа к ресурсу системы на локальном компьютере, защищенном с помощью Windows ACL, уровень олицетворения должен быть установлен в значение <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-117">To perform an access check when accessing a system resource on the local machine that is protected using Windows ACLs, the impersonation level must be set to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, as shown in the following sample code.</span></span>  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 <span data-ttu-id="cfe4d-118">При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-118">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="cfe4d-119">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-119">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfe4d-120">Служба должна быть запущена с учетной записью администратора или учетной записью, под которой он выполняется, должны быть предоставлены права на регистрацию `http://localhost:8000/ServiceModelSamples` URI на уровне HTTP.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-120">The service must either run under an administrative account or the account it runs under must be granted rights to register the `http://localhost:8000/ServiceModelSamples` URI with the HTTP layer.</span></span> <span data-ttu-id="cfe4d-121">Такие права можно предоставить, настроив [резервирование пространства имен](/windows/win32/http/namespace-reservations-registrations-and-routing) с помощью [средства Httpcfg. exe](/windows/win32/http/httpcfg-exe).</span><span class="sxs-lookup"><span data-stu-id="cfe4d-121">Such rights can be granted by setting up a [Namespace Reservation](/windows/win32/http/namespace-reservations-registrations-and-routing) using the [Httpcfg.exe tool](/windows/win32/http/httpcfg-exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfe4d-122">На компьютерах под управлением Windows Server 2003 олицетворение поддерживается только в том случае, если приложение Host. exe имеет привилегию олицетворения.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-122">On computers running Windows Server 2003, impersonation is supported only if the Host.exe application has the Impersonation privilege.</span></span> <span data-ttu-id="cfe4d-123">(По умолчанию это разрешение имеют только администраторы.) Чтобы добавить эту привилегию к учетной записи, от имени которой запущена служба, перейдите в раздел **Администрирование**, откройте **локальную политику безопасности**, откройте **локальные**политики, щелкните **Назначение прав пользователя**и выберите **Олицетворять клиента после проверки подлинности** и дважды щелкните **Свойства** , чтобы добавить пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-123">(By default, only administrators have this permission.) To add this privilege to an account the service is running as, go to **Administrative Tools**, open **Local Security Policy**, open **Local Policies**, click **User Rights Assignment**, and select **Impersonate a Client after Authentication** and double-click **Properties** to add a user or group.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cfe4d-124">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cfe4d-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="cfe4d-125">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cfe4d-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="cfe4d-126">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cfe4d-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="cfe4d-127">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cfe4d-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="cfe4d-128">Для демонстрации олицетворения абонента службой, запустите клиент под другой учетной записью, отличной от той, под которой работает служба.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-128">To demonstrate that the service impersonates the caller, run the client under a different account than the one the service is running under.</span></span> <span data-ttu-id="cfe4d-129">Чтобы сделать это, введите в командной строке следующую команду.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-129">To do so, at the command prompt, type:</span></span>  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     <span data-ttu-id="cfe4d-130">После этого будет запрошен ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-130">You are then prompted for a password.</span></span> <span data-ttu-id="cfe4d-131">Введите пароль для ранее указанной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-131">Enter the password for the account you previously specified.</span></span>  
  
5. <span data-ttu-id="cfe4d-132">При запуске клиента обратите внимание, что идентификация до и после его запуска будет иметь разные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="cfe4d-132">When you run the client, note the identity before and after running it with different credentials.</span></span>  
