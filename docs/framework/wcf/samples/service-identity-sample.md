---
title: Образец идентификации службы
ms.date: 03/30/2017
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
ms.openlocfilehash: eb2dd3c6392164905cf755075856608ec5fcaf30
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837796"
---
# <a name="service-identity-sample"></a><span data-ttu-id="74d04-102">Образец идентификации службы</span><span class="sxs-lookup"><span data-stu-id="74d04-102">Service Identity Sample</span></span>
<span data-ttu-id="74d04-103">В этом образце удостоверения службы демонстрируется, как назначить удостоверение для службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-103">This service identity sample demonstrates how to set the identity for a service.</span></span> <span data-ttu-id="74d04-104">Во время проектирования клиент может извлечь удостоверение используя метаданные службы, а затем в среде выполнения клиент может проверить подлинность удостоверения службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-104">At design time, a client can retrieve the identity using the service's metadata and then at runtime the client can authenticate the service's identity.</span></span> <span data-ttu-id="74d04-105">Концепция удостоверения службы позволяет клиенту проверять подлинность службы перед вызовом любых ее операций, защищая таким образом клиента от вызовов, не прошедших проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="74d04-105">The concept of service identity is to allow a client to authenticate a service before calling any of its operations, thereby protecting the client from unauthenticated calls.</span></span> <span data-ttu-id="74d04-106">При безопасном подключении служба также проводит проверку подлинности учетных данных клиента перед тем, как предоставить им доступ. Однако это выходит за рамки данного образца.</span><span class="sxs-lookup"><span data-stu-id="74d04-106">On a secure connection the service also authenticates a client's credentials before allowing it access, but this is not the focus of this sample.</span></span> <span data-ttu-id="74d04-107">Ознакомьтесь с примерами в разделе [клиент](../../../../docs/framework/wcf/samples/client.md) , которые показывают проверку подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="74d04-107">See the samples in [Client](../../../../docs/framework/wcf/samples/client.md) that show server authentication.</span></span>

> [!NOTE]
> <span data-ttu-id="74d04-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="74d04-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="74d04-109">В этом образце демонстрируются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="74d04-109">This sample illustrates the following features:</span></span>

- <span data-ttu-id="74d04-110">Как задать различные типы удостоверения для службы на различных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="74d04-110">How to set the different types of identity on different endpoints for a service.</span></span> <span data-ttu-id="74d04-111">Каждый тип удостоверения обладает различным возможностями.</span><span class="sxs-lookup"><span data-stu-id="74d04-111">Each type of identity has different capabilities.</span></span> <span data-ttu-id="74d04-112">Используемый тип удостоверения зависит от типа учетных данных безопасности, используемых для привязки в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="74d04-112">The type of identity to use is dependent on the type of security credentials used on the endpoint's binding.</span></span>

- <span data-ttu-id="74d04-113">Удостоверение может быть задано как декларативно в конфигурации, так и императивно в коде.</span><span class="sxs-lookup"><span data-stu-id="74d04-113">Identity can either be set declaratively in configuration or imperatively in code.</span></span> <span data-ttu-id="74d04-114">Обычно используется конфигурация для назначения удостоверения как для клиента, так и для службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-114">Typically for both the client and the service you should use configuration to set the identity.</span></span>

- <span data-ttu-id="74d04-115">Как назначить пользовательское удостоверение клиенту.</span><span class="sxs-lookup"><span data-stu-id="74d04-115">How to set a custom identity on the client.</span></span> <span data-ttu-id="74d04-116">Пользовательское удостоверение обычно представляет собой настройку существующего типа удостоверения, которое позволяет клиенту анализировать оставшуюся информацию об утверждениях, передаваемых в учетных данных службы, позволяя принимать решение об авторизации до момента вызова службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-116">A custom identity is typically a customization of an existing type of identity that enables the client to examine other claim information provided in the service's credentials to make authorization decisions before calling the service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74d04-117">Этот образец проверяет удостоверение конкретного сертификата identity.com и ключ RSA, который содержится в этом сертификате.</span><span class="sxs-lookup"><span data-stu-id="74d04-117">This sample checks the identity of a specific certificate called identity.com and the RSA key contained within this certificate.</span></span> <span data-ttu-id="74d04-118">При использовании типов удостоверений Certificate и RSA в конфигурации клиента самый простой способ получить эти значения - проверить WSDL для службы, где эти значения сериализуются.</span><span class="sxs-lookup"><span data-stu-id="74d04-118">When using the Certificate and RSA identity types in configuration on the client, an easy way to get these values is to inspect the WSDL for the service where these values are serialized.</span></span>

 <span data-ttu-id="74d04-119">В следующем образце кода показано, как сконфигурировать удостоверение конечной точки службы с сервером доменных имен (DNS) сертификата, используя WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="74d04-119">The following sample code shows how to configure the identity of a service endpoint with the Domain Name Server (DNS) of a certificate using a WSHttpBinding.</span></span>

```csharp
//Create a service endpoint and set its identity to the certificate's DNS
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);
// Client are Anonymous to the service
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));
ep.Address = epa;
```

 <span data-ttu-id="74d04-120">Удостоверение может быть также задано в конфигурации в файле App.config.</span><span class="sxs-lookup"><span data-stu-id="74d04-120">The identity can also be specified in configuration in the App.config file.</span></span> <span data-ttu-id="74d04-121">В следующем примере показано, как задать удостоверение "имя участника-пользователя" (UPN) для конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-121">The following example shows how to set the UPN (User Principal Name) identity for a service endpoint.</span></span>

```xml
<endpoint address="upnidentity"
        behaviorConfiguration=""
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_Windows"
        name="WSHttpBinding_ICalculator_Windows"
        contract="Microsoft.ServiceModel.Samples.ICalculator">
  <!-- Set the UPN identity for this endpoint -->
  <identity>
      <userPrincipalName value="host\myservice.com" />
  </identity >
</endpoint>
```

 <span data-ttu-id="74d04-122">Пользовательское удостоверение может быть создано на клиенте путем наследования от классов <xref:System.ServiceModel.EndpointIdentity> и <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="74d04-122">A custom identity can be set on the client by deriving from the <xref:System.ServiceModel.EndpointIdentity> and the <xref:System.ServiceModel.Security.IdentityVerifier> classes.</span></span> <span data-ttu-id="74d04-123">В принципе, класс <xref:System.ServiceModel.Security.IdentityVerifier> может рассматриваться в качестве клиента, эквивалентного классу службы `AuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="74d04-123">Conceptually the <xref:System.ServiceModel.Security.IdentityVerifier> class can be considered to be the client equivalent of the service's `AuthorizationManager` class.</span></span> <span data-ttu-id="74d04-124">В следующем примере кода показана реализация метода `OrgEndpointIdentity`, хранящего имя организации, которому должно соответствовать имя субъекта сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="74d04-124">The following code example shows an implementation of `OrgEndpointIdentity`, which stores an organization name to match in the subject name of the server's certificate.</span></span> <span data-ttu-id="74d04-125">Авторизация проверяет появление имени организации в методе `CheckAccess` в классе `CustomIdentityVerifier`.</span><span class="sxs-lookup"><span data-stu-id="74d04-125">The authorization check for the organization name occurs in the `CheckAccess` method on the `CustomIdentityVerifier` class.</span></span>

```csharp
// This custom EndpointIdentity stores an organization name
public class OrgEndpointIdentity : EndpointIdentity
{
    private string orgClaim;
    public OrgEndpointIdentity(string orgName)
    {
        orgClaim = orgName;
    }
    public string OrganizationClaim
    {
        get { return orgClaim; }
        set { orgClaim = value; }
    }
}

//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to
//check that X.509 certificate's distinguished name claim contains
//the organization name e.g. the string value "O=Contoso"
class CustomIdentityVerifier : IdentityVerifier
{
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)
    {
        bool returnvalue = false;
        foreach (ClaimSet claimset in authContext.ClaimSets)
        {
            foreach (Claim claim in claimset)
            {
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")
                {
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))
                    {
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);
                        Console.WriteLine("Right: {0}", claim.Right);
                        Console.WriteLine("Resource: {0}",claim.Resource);
                        Console.WriteLine();
                        returnvalue = true;
                    }
                }
            }
        }
        return returnvalue;
    }
}
```

 <span data-ttu-id="74d04-126">Этот образец использует сертификат identity.com, который находится в соответствующей языковой папке решения для идентификации.</span><span class="sxs-lookup"><span data-stu-id="74d04-126">This sample uses a certificate called identity.com which is in the language-specific Identity solution folder.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="74d04-127">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="74d04-127">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="74d04-128">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="74d04-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="74d04-129">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="74d04-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="74d04-130">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="74d04-130">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="74d04-131">Запуск образца на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="74d04-131">To run the sample on the same computer</span></span>

1. <span data-ttu-id="74d04-132">В [!INCLUDE[wxp](../../../../includes/wxp-md.md)] или Windows Vista импортируйте файл сертификата Identity. pfx в папку решения Identity в хранилище сертификатов LocalMachine/My (личное) с помощью оснастки MMC.</span><span class="sxs-lookup"><span data-stu-id="74d04-132">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or Windows Vista, import the Identity.pfx certificate file in the Identity solution folder into the LocalMachine/My (Personal) certificate store using the MMC snap-in tool.</span></span> <span data-ttu-id="74d04-133">Этот файл защищен паролем.</span><span class="sxs-lookup"><span data-stu-id="74d04-133">This file is password protected.</span></span> <span data-ttu-id="74d04-134">Во время импорта будет запрошен пароль.</span><span class="sxs-lookup"><span data-stu-id="74d04-134">During the import you are asked for a password.</span></span> <span data-ttu-id="74d04-135">Введите `xyz` в поле пароль.</span><span class="sxs-lookup"><span data-stu-id="74d04-135">Type `xyz` into the password box.</span></span> <span data-ttu-id="74d04-136">Дополнительные сведения см. в разделе [инструкции. Просмотр сертификатов с помощью оснастки MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) .</span><span class="sxs-lookup"><span data-stu-id="74d04-136">For more information, see the [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="74d04-137">После этого запустите Setup. bat в Командная строка разработчика для Visual Studio с правами администратора, который скопирует этот сертификат в хранилище CurrentUser/Trusted Peoples для использования на клиенте.</span><span class="sxs-lookup"><span data-stu-id="74d04-137">Once this is done, run Setup.bat in a Developer Command Prompt for Visual Studio with administrator privileges, which copies this certificate to the CurrentUser/Trusted People store for use on the client.</span></span>

2. <span data-ttu-id="74d04-138">На [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]запустите программу Setup. bat из папки примера установки в командной строке Visual Studio 2012 с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="74d04-138">On [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt with administrator privileges.</span></span> <span data-ttu-id="74d04-139">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="74d04-139">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74d04-140">Пакетный файл Setup. bat предназначен для запуска из командной строки Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="74d04-140">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="74d04-141">Переменная среды PATH, заданная в командной строке Visual Studio 2012, указывает на каталог, содержащий исполняемые файлы, необходимые для сценария Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="74d04-141">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="74d04-142">После завершения работы образца выполните в папке образца файл Cleanup.bat, чтобы удалить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="74d04-142">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="74d04-143">В других образцах обеспечения безопасности используются те же сертификаты.</span><span class="sxs-lookup"><span data-stu-id="74d04-143">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="74d04-144">Запустите программу Service.exe из каталога \service\bin.</span><span class="sxs-lookup"><span data-stu-id="74d04-144">Launch Service.exe from the \service\bin directory.</span></span> <span data-ttu-id="74d04-145">Убедитесь, что служба указывает, что она готова, и отобразится запрос на нажатие кнопки \<ввод > для завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-145">Ensure that the service indicates that it is ready and displays a prompt to Press \<Enter> to terminate the service.</span></span>  
  
4. <span data-ttu-id="74d04-146">Запустите файл Client.exe из каталога \client\bin, или нажав F5 в Visual Studio для построения и выполнения примера.</span><span class="sxs-lookup"><span data-stu-id="74d04-146">Launch Client.exe from \client\bin directory or by pressing F5 in Visual Studio to build and run.</span></span> <span data-ttu-id="74d04-147">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="74d04-147">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="74d04-148">Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="74d04-148">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="74d04-149">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="74d04-149">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="74d04-150">Перед тем как построить клиентскую часть образца, убедитесь в изменении значения адреса конечной точки службы в файле Client.cs в методе `CallServiceCustomClientIdentity`.</span><span class="sxs-lookup"><span data-stu-id="74d04-150">Before building the client part of the sample, be sure to change the value for the service's endpoint address in the Client.cs file in the `CallServiceCustomClientIdentity` method.</span></span> <span data-ttu-id="74d04-151">После этого постройте образец.</span><span class="sxs-lookup"><span data-stu-id="74d04-151">Then build the sample.</span></span>  
  
2. <span data-ttu-id="74d04-152">Создайте каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-152">Create a directory on the service computer.</span></span>  
  
3. <span data-ttu-id="74d04-153">Скопируйте файлы служебной программ из каталога service\bin в каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-153">Copy the service program files from service\bin to the directory on the service computer.</span></span> <span data-ttu-id="74d04-154">Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-154">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
4. <span data-ttu-id="74d04-155">Создайте на клиентском компьютере каталог для двоичных файлов клиента.</span><span class="sxs-lookup"><span data-stu-id="74d04-155">Create a directory on the client computer for the client binaries.</span></span>  
  
5. <span data-ttu-id="74d04-156">Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.</span><span class="sxs-lookup"><span data-stu-id="74d04-156">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="74d04-157">Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="74d04-157">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
6. <span data-ttu-id="74d04-158">В службе запустите `setup.bat service` в Командная строка разработчика для Visual Studio, открытой с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="74d04-158">On the service, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="74d04-159">При запуске `setup.bat` с аргументом `service` создается сертификат службы с полным доменным именем компьютера и экспортируется сертификат службы в файл с именем Service. cer.</span><span class="sxs-lookup"><span data-stu-id="74d04-159">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
7. <span data-ttu-id="74d04-160">Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="74d04-160">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="74d04-161">В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="74d04-161">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="74d04-162">Есть несколько экземпляров, которые должны быть изменены.</span><span class="sxs-lookup"><span data-stu-id="74d04-162">There are multiple instances that must be changed.</span></span>  
  
9. <span data-ttu-id="74d04-163">На клиенте запустите Импортсервицецерт. bat в Командная строка разработчика для Visual Studio, открытой с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="74d04-163">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="74d04-164">Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="74d04-164">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="74d04-165">На компьютере службы запустите из командной строки программу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="74d04-165">On the service computer, launch the Service.exe from the command prompt.</span></span>  
  
11. <span data-ttu-id="74d04-166">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="74d04-166">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="74d04-167">Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="74d04-167">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="74d04-168">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="74d04-168">To clean up after the sample</span></span>  
  
- <span data-ttu-id="74d04-169">После завершения работы примера запустите в папке примеров файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="74d04-169">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="74d04-170">Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="74d04-170">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="74d04-171">Если вы выполнили примеры Windows Communication Foundation (WCF), использующие сертификаты на нескольких компьютерах, обязательно очистите сертификаты службы, установленные в хранилище CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="74d04-171">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="74d04-172">Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="74d04-172">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
