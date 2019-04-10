---
title: Практическое руководство. Задание учетных данных безопасности канала
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 0bfbb71ade3822b9f504c2f89a41145ce0d435f6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297984"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="d82a5-102">Практическое руководство. Задание учетных данных безопасности канала</span><span class="sxs-lookup"><span data-stu-id="d82a5-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="d82a5-103">Моникер служб Windows Communication Foundation (WCF) позволяет приложениям COM вызывать службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d82a5-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="d82a5-104">Большинство служб WCF потребовать от клиента указать учетные данные для проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="d82a5-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="d82a5-105">При вызове службы WCF из клиента WCF, можно указать эти учетные данные в управляемом коде или в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d82a5-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="d82a5-106">При вызове службы WCF из приложения COM, можно использовать <xref:System.ServiceModel.ComIntegration.IChannelCredentials> интерфейс, чтобы указать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d82a5-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="d82a5-107">В данном разделе описаны различные способы указания учетных данных с использованием интерфейса <xref:System.ServiceModel.ComIntegration.IChannelCredentials>.</span><span class="sxs-lookup"><span data-stu-id="d82a5-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
>  <xref:System.ServiceModel.ComIntegration.IChannelCredentials> <span data-ttu-id="d82a5-108">— Это интерфейс на основе IDispatch, и вы не получите функциональных возможностях IntelliSense в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d82a5-108">is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="d82a5-109">В этой статье будет использовать службу WCF, определенные в [пример безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d82a5-109">This article will use the WCF service defined in the [Message Security Sample](../../../../docs/framework/wcf/samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="d82a5-110">Задание сертификата клиента</span><span class="sxs-lookup"><span data-stu-id="d82a5-110">To specify a client certificate</span></span>  
  
1. <span data-ttu-id="d82a5-111">Запустите файл Setup.bat в каталоге "Безопасность сообщений", чтобы создать и установить требуемые тестовые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="d82a5-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2. <span data-ttu-id="d82a5-112">Откройте проект безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="d82a5-112">Open the Message Security project.</span></span>  
  
3. <span data-ttu-id="d82a5-113">Добавить `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` для `ICalculator` определение интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d82a5-113">Add `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` to the `ICalculator` interface definition.</span></span>  
  
4. <span data-ttu-id="d82a5-114">Добавить `bindingNamespace="http://Microsoft.ServiceModel.Samples"` в тег конечной точки в файле App.config для службы.</span><span class="sxs-lookup"><span data-stu-id="d82a5-114">Add `bindingNamespace="http://Microsoft.ServiceModel.Samples"` to the endpoint tag in the App.config for the service.</span></span>  
  
5. <span data-ttu-id="d82a5-115">Создайте образец безопасности сообщений и запустите файл Service.exe.</span><span class="sxs-lookup"><span data-stu-id="d82a5-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="d82a5-116">Используйте Internet Explorer и перейдите к URI службы (http://localhost:8000/ServiceModelSamples/Service) чтобы убедиться, что служба работает.</span><span class="sxs-lookup"><span data-stu-id="d82a5-116">Use Internet Explorer and browse to the service's URI (http://localhost:8000/ServiceModelSamples/Service) to ensure that the service is working.</span></span>  
  
6. <span data-ttu-id="d82a5-117">Откройте Visual Basic 6.0 и создайте новый стандартный EXE-файл.</span><span class="sxs-lookup"><span data-stu-id="d82a5-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="d82a5-118">Добавьте в форму кнопку и дважды щелкните ее, чтобы добавить следующий код в обработчик щелчка.</span><span class="sxs-lookup"><span data-stu-id="d82a5-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7. <span data-ttu-id="d82a5-119">Запустите приложение Visual Basic и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="d82a5-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="d82a5-120">Приложение Visual Basic отобразит окно сообщений с результатом вызова Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="d82a5-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> <span data-ttu-id="d82a5-121">или <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> также может использоваться вместо <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> задать сертификат клиента:</span><span class="sxs-lookup"><span data-stu-id="d82a5-121">or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="d82a5-122">Чтобы этот вызов работал, сертификат клиента должен быть доверенным на компьютере, на котором выполняется клиент.</span><span class="sxs-lookup"><span data-stu-id="d82a5-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d82a5-123">Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка".</span><span class="sxs-lookup"><span data-stu-id="d82a5-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="d82a5-124">При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.</span><span class="sxs-lookup"><span data-stu-id="d82a5-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="d82a5-125">Задание имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="d82a5-125">To specify user name and password</span></span>  
  
1. <span data-ttu-id="d82a5-126">Измените файл App.config службы, чтобы использовать привязку `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="d82a5-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="d82a5-127">Это необходимо для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="d82a5-127">This is required for user name and password validation:</span></span>  

2. <span data-ttu-id="d82a5-128">Задайте для атрибута `clientCredentialType` значение UserName.</span><span class="sxs-lookup"><span data-stu-id="d82a5-128">Set the `clientCredentialType` to UserName:</span></span>  

3. <span data-ttu-id="d82a5-129">Откройте Visual Basic 6.0 и создайте новый стандартный EXE-файл.</span><span class="sxs-lookup"><span data-stu-id="d82a5-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="d82a5-130">Добавьте в форму кнопку и дважды щелкните ее, чтобы добавить следующий код в обработчик щелчка.</span><span class="sxs-lookup"><span data-stu-id="d82a5-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. <span data-ttu-id="d82a5-131">Запустите приложение Visual Basic и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="d82a5-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="d82a5-132">Приложение Visual Basic отобразит окно сообщений с результатом вызова Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="d82a5-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d82a5-133">Привязка, заданная в моникере служб в этом примере, изменена на WSHttpBinding_ICalculator.</span><span class="sxs-lookup"><span data-stu-id="d82a5-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="d82a5-134">Также обратите внимание, что необходимо предоставить действительные имя пользователя и пароль в вызове метода <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="d82a5-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="d82a5-135">Задание учетных данных Windows</span><span class="sxs-lookup"><span data-stu-id="d82a5-135">To specify Windows Credentials</span></span>  
  
1. <span data-ttu-id="d82a5-136">Задайте для атрибута `clientCredentialType` значение Windows в файле App.config службы.</span><span class="sxs-lookup"><span data-stu-id="d82a5-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  

2. <span data-ttu-id="d82a5-137">Откройте Visual Basic 6.0 и создайте новый стандартный EXE-файл.</span><span class="sxs-lookup"><span data-stu-id="d82a5-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="d82a5-138">Добавьте в форму кнопку и дважды щелкните ее, чтобы добавить следующий код в обработчик щелчка.</span><span class="sxs-lookup"><span data-stu-id="d82a5-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="d82a5-139">Запустите приложение Visual Basic и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="d82a5-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="d82a5-140">Приложение Visual Basic отобразит окно сообщений с результатом вызова Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="d82a5-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d82a5-141">Необходимо заменить "domain", "userID" и "password" на действительные значения.</span><span class="sxs-lookup"><span data-stu-id="d82a5-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="d82a5-142">Задание маркера вопроса</span><span class="sxs-lookup"><span data-stu-id="d82a5-142">To specify an issue token</span></span>  
  
1. <span data-ttu-id="d82a5-143">Маркеры вопроса используются только для приложений с федеративной безопасностью.</span><span class="sxs-lookup"><span data-stu-id="d82a5-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="d82a5-144">Дополнительные сведения о федеративной безопасности, см. в разделе [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) и [пример федерации](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d82a5-144">For more information about federated security, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) and [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="d82a5-145">В следующем примере кода Visual Basic показано, как вызывать метод <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="d82a5-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="d82a5-146">Дополнительные сведения о параметрах для этого метода см. в разделе <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="d82a5-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d82a5-147">См. также</span><span class="sxs-lookup"><span data-stu-id="d82a5-147">See also</span></span>

- [<span data-ttu-id="d82a5-148">Федерация</span><span class="sxs-lookup"><span data-stu-id="d82a5-148">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)
- [<span data-ttu-id="d82a5-149">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="d82a5-149">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="d82a5-150">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="d82a5-150">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d82a5-151">Безопасность сообщений</span><span class="sxs-lookup"><span data-stu-id="d82a5-151">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="d82a5-152">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="d82a5-152">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
