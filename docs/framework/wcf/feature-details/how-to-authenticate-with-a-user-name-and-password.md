---
title: Практическое руководство. Проверка подлинности с использованием имени и пароля пользователя
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: 33205f9e12fcee53f2f29b63b836ea0cbc792025
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834737"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="25a3d-102">Практическое руководство. Проверка подлинности с использованием имени и пароля пользователя</span><span class="sxs-lookup"><span data-stu-id="25a3d-102">How to: Authenticate with a User Name and Password</span></span>

<span data-ttu-id="25a3d-103">В этом разделе показано, как включить службу Windows Communication Foundation (WCF) для проверки подлинности клиента с именем пользователя домена Windows и паролем.</span><span class="sxs-lookup"><span data-stu-id="25a3d-103">This topic demonstrates how to enable a Windows Communication Foundation (WCF) service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="25a3d-104">Предполагается, что это рабочая резидентная служба WCF.</span><span class="sxs-lookup"><span data-stu-id="25a3d-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="25a3d-105">Пример создания основной самостоятельно размещенной службы WCF см. в [Начало работы руководстве](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="25a3d-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="25a3d-106">В этом разделе предполагается, что служба настраивается в коде.</span><span class="sxs-lookup"><span data-stu-id="25a3d-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="25a3d-107">Пример настройки аналогичной службы с помощью файла конфигурации см. в разделе [Message Security Name (имя пользователя безопасности сообщения](../samples/message-security-user-name.md)).</span><span class="sxs-lookup"><span data-stu-id="25a3d-107">If you would like to see an example of configuring a similar service using a configuration file, see [Message Security User Name](../samples/message-security-user-name.md).</span></span>

<span data-ttu-id="25a3d-108">Чтобы настроить службу для проверки подлинности клиентов по имени пользователя и паролю в домене Windows, используйте <xref:System.ServiceModel.WSHttpBinding>, установив свойство `Security.Mode` в значение `Message`.</span><span class="sxs-lookup"><span data-stu-id="25a3d-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <xref:System.ServiceModel.WSHttpBinding> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="25a3d-109">Кроме того, необходимо указать сертификат X509, который будет использован для шифрования имени пользователя и пароля, так как они передаются от клиента к службе.</span><span class="sxs-lookup"><span data-stu-id="25a3d-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>

<span data-ttu-id="25a3d-110">На стороне клиента необходимо запрашивать у пользователя учетные данные и указать учетные данные пользователя в клиентском классе-посреднике WCF.</span><span class="sxs-lookup"><span data-stu-id="25a3d-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>

## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="25a3d-111">Настройка службы WCF для проверки подлинности с помощью имени пользователя и пароля домена Windows</span><span class="sxs-lookup"><span data-stu-id="25a3d-111">To configure a WCF service to authenticate using Windows domain username and password</span></span>

1. <span data-ttu-id="25a3d-112">Создайте экземпляр <xref:System.ServiceModel.WSHttpBinding>, установите режим безопасности привязки в <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, установите `ClientCredentialType` привязки в значение <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> и добавьте в узел службы конечную точку службы с помощью заданной привязки, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="25a3d-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding>, set the security mode of the binding to <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, set the `ClientCredentialType` of the binding to <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType>, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>

    ```csharp
    // ...
    var userNameBinding = new WSHttpBinding();
    userNameBinding.Security.Mode = SecurityMode.Message;
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");
    // ...
    ```

2. <span data-ttu-id="25a3d-113">Задает сертификат сервера, используемый для шифрования имени пользователя и пароля, передаваемых по сети.</span><span class="sxs-lookup"><span data-stu-id="25a3d-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="25a3d-114">Этот код должен непосредственно следовать за показанным выше кодом.</span><span class="sxs-lookup"><span data-stu-id="25a3d-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="25a3d-115">В следующем примере используется сертификат, созданный в файле Setup. bat, из примера [имени пользователя для защиты сообщений](../samples/message-security-user-name.md) :</span><span class="sxs-lookup"><span data-stu-id="25a3d-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../samples/message-security-user-name.md) sample:</span></span>

    ```csharp
    // ...
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");
    // ...
    ```

    <span data-ttu-id="25a3d-116">Вы можете использовать собственный сертификат, просто укажите ссылку на него в коде.</span><span class="sxs-lookup"><span data-stu-id="25a3d-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="25a3d-117">Дополнительные сведения о создании и использовании сертификатов см. [в разделе Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="25a3d-117">For more information about creating and using certificates see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="25a3d-118">Убедитесь, что сертификат находится в хранилище сертификатов «Доверенные лица» для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="25a3d-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="25a3d-119">Это можно сделать, запустив MMC. exe и выбрав пункт меню **файл**, **Добавить или удалить оснастку...** .</span><span class="sxs-lookup"><span data-stu-id="25a3d-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="25a3d-120">В диалоговом окне **Добавление или удаление оснастки** выберите **оснастку Сертификаты** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="25a3d-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="25a3d-121">В диалоговом окне Оснастка "сертификаты" выберите **учетная запись компьютера**.</span><span class="sxs-lookup"><span data-stu-id="25a3d-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="25a3d-122">По умолчанию сертификат, сформированный из образца «Безопасность сообщений с использованием имени пользователя», будет находиться в папке «Личное или сертификаты».</span><span class="sxs-lookup"><span data-stu-id="25a3d-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="25a3d-123">Он будет указан как localhost в столбце Кому выдан в окне MMC.</span><span class="sxs-lookup"><span data-stu-id="25a3d-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="25a3d-124">Перетащите сертификат в папку " **Доверенные лица** ".</span><span class="sxs-lookup"><span data-stu-id="25a3d-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="25a3d-125">Это позволит WCF считать сертификат доверенным при выполнении проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="25a3d-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>

## <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="25a3d-126">Вызов службы с передачей имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="25a3d-126">To call the service passing username and password</span></span>

1. <span data-ttu-id="25a3d-127">Клиентское приложение должно предложить пользователю ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="25a3d-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="25a3d-128">Следующий код запрашивает у пользователя имя пользователя и пароль:</span><span class="sxs-lookup"><span data-stu-id="25a3d-128">The following code asks the user for username and password:</span></span>

    > [!WARNING]
    > <span data-ttu-id="25a3d-129">Этот код не следует использовать в рабочей среде, так как пароль во время ввода отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="25a3d-129">This code should not be used in production as the password is displayed while being entered.</span></span>

    ```csharp
    public static void GetPassword(out string username, out string password)
    {
        Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");
        Console.WriteLine("   Enter username:");
        username = Console.ReadLine();
        Console.WriteLine("   Enter password:");
        password = Console.ReadLine();
    }
    ```

2. <span data-ttu-id="25a3d-130">Создайте экземпляр прокси клиента, указав учетные данные клиента, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="25a3d-130">Create an instance of the client proxy specifying the client's credentials as shown in the following code:</span></span>

    ```csharp
    string username;
    string password;

    // Instantiate the proxy.
    var proxy = new Service1Client();

    // Prompt the user for username & password.
    GetPassword(out username, out password);

    // Set the user's credentials on the proxy.
    proxy.ClientCredentials.UserName.UserName = username;
    proxy.ClientCredentials.UserName.Password = password;

    // Treat the test certificate as trusted.
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;
    // Call the service operation using the proxy
    ```

## <a name="see-also"></a><span data-ttu-id="25a3d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="25a3d-131">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [<span data-ttu-id="25a3d-132">Безопасность транспорта с обычной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="25a3d-132">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)
- [<span data-ttu-id="25a3d-133">Защита распределенных приложений</span><span class="sxs-lookup"><span data-stu-id="25a3d-133">Distributed Application Security</span></span>](distributed-application-security.md)
- [<span data-ttu-id="25a3d-134">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="25a3d-134">\<wsHttpBinding></span></span>](../../configure-apps/file-schema/wcf/wshttpbinding.md)
