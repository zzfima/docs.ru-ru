---
title: "Безопасность транспорта с обычной проверкой подлинности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: fe6b996c37e66f41c3946b8ef3437f8fa82c5201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="e11bc-102">Безопасность транспорта с обычной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="e11bc-102">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="e11bc-103">На следующем рисунке показаны служба и клиент [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e11bc-103">The following illustration shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client.</span></span> <span data-ttu-id="e11bc-104">Серверу требуется действительный сертификат X.509, который можно использовать для протокола SSL, а клиенты должны доверять сертификату сервера.</span><span class="sxs-lookup"><span data-stu-id="e11bc-104">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="e11bc-105">Кроме того, у веб-службы уже имеется сертификат SSL, который можно использовать.</span><span class="sxs-lookup"><span data-stu-id="e11bc-105">Further, the Web service already has an SSL implementation that can be used.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e11bc-106">Включение обычной проверки подлинности в Internet Information Services (IIS), в разделе [http://go.microsoft.com/fwlink/?LinkId=83822](http://go.microsoft.com/fwlink/?LinkId=83822).</span><span class="sxs-lookup"><span data-stu-id="e11bc-106"> enabling basic authentication on Internet Information Services (IIS), see [http://go.microsoft.com/fwlink/?LinkId=83822](http://go.microsoft.com/fwlink/?LinkId=83822).</span></span>  
  
 <span data-ttu-id="e11bc-107">![Безопасность транспорта с обычной проверкой подлинности](../../../../docs/framework/wcf/feature-details/media/securedbyusername.gif "SecuredbyUsername")</span><span class="sxs-lookup"><span data-stu-id="e11bc-107">![Transport security with basic authentication](../../../../docs/framework/wcf/feature-details/media/securedbyusername.gif "SecuredbyUsername")</span></span>  
  
|<span data-ttu-id="e11bc-108">Характеристика</span><span class="sxs-lookup"><span data-stu-id="e11bc-108">Characteristic</span></span>|<span data-ttu-id="e11bc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e11bc-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e11bc-110">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="e11bc-110">Security Mode</span></span>|<span data-ttu-id="e11bc-111">Transport</span><span class="sxs-lookup"><span data-stu-id="e11bc-111">Transport</span></span>|  
|<span data-ttu-id="e11bc-112">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="e11bc-112">Interoperability</span></span>|<span data-ttu-id="e11bc-113">С существующими службами и клиентами веб-служб</span><span class="sxs-lookup"><span data-stu-id="e11bc-113">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="e11bc-114">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="e11bc-114">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="e11bc-115">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="e11bc-115">Authentication (Client)</span></span>|<span data-ttu-id="e11bc-116">Да (по протоколу HTTPS)</span><span class="sxs-lookup"><span data-stu-id="e11bc-116">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="e11bc-117">Да (по имени/паролю пользователя)</span><span class="sxs-lookup"><span data-stu-id="e11bc-117">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="e11bc-118">Целостность</span><span class="sxs-lookup"><span data-stu-id="e11bc-118">Integrity</span></span>|<span data-ttu-id="e11bc-119">Да</span><span class="sxs-lookup"><span data-stu-id="e11bc-119">Yes</span></span>|  
|<span data-ttu-id="e11bc-120">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="e11bc-120">Confidentiality</span></span>|<span data-ttu-id="e11bc-121">Да</span><span class="sxs-lookup"><span data-stu-id="e11bc-121">Yes</span></span>|  
|<span data-ttu-id="e11bc-122">Transport</span><span class="sxs-lookup"><span data-stu-id="e11bc-122">Transport</span></span>|<span data-ttu-id="e11bc-123">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e11bc-123">HTTPS</span></span>|  
|<span data-ttu-id="e11bc-124">Привязка</span><span class="sxs-lookup"><span data-stu-id="e11bc-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="e11bc-125">Служба</span><span class="sxs-lookup"><span data-stu-id="e11bc-125">Service</span></span>  
 <span data-ttu-id="e11bc-126">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="e11bc-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e11bc-127">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e11bc-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="e11bc-128">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e11bc-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="e11bc-129">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="e11bc-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e11bc-130">Код</span><span class="sxs-lookup"><span data-stu-id="e11bc-130">Code</span></span>  
 <span data-ttu-id="e11bc-131">В следующем примере кода показано, как создавать конечную точку службы, использующую имя и пароль пользователя в домене Windows для безопасности передачи.</span><span class="sxs-lookup"><span data-stu-id="e11bc-131">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="e11bc-132">Обратите внимание, что для проверки подлинности клиента службе требуется сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="e11bc-132">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="e11bc-133">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) и [как: Настройка порта с SSL-сертификата](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="e11bc-133">For more information, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="e11bc-134">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="e11bc-134">Configuration</span></span>  
 <span data-ttu-id="e11bc-135">Следующий код служит для настройки службы на использование обычной проверки подлинности с безопасностью на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="e11bc-135">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"   
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"   
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="e11bc-136">Клиент</span><span class="sxs-lookup"><span data-stu-id="e11bc-136">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="e11bc-137">Код</span><span class="sxs-lookup"><span data-stu-id="e11bc-137">Code</span></span>  
 <span data-ttu-id="e11bc-138">В следующем примере кода демонстрируется код клиента, который содержит имя и пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="e11bc-138">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="e11bc-139">Обратите внимание, что пользователь должен предоставить действительные имя и пароль пользователя в Windows.</span><span class="sxs-lookup"><span data-stu-id="e11bc-139">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="e11bc-140">В данном разделе не представлен код, возвращающий имя и пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="e11bc-140">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="e11bc-141">Используйте диалоговое окно или другой интерфейс, чтобы запросить пользователя об этой информации.</span><span class="sxs-lookup"><span data-stu-id="e11bc-141">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e11bc-142">Имя и пароль пользователя задаются только с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="e11bc-142">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="e11bc-143">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="e11bc-143">Configuration</span></span>  
 <span data-ttu-id="e11bc-144">В следующем примере кода показана конфигурация клиента.</span><span class="sxs-lookup"><span data-stu-id="e11bc-144">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e11bc-145">Конфигурацию невозможно использовать для задания имени и пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="e11bc-145">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="e11bc-146">Представленную в этом примере конфигурацию необходимо дополнить с помощью кода, чтобы разрешить задание имени и пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="e11bc-146">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e11bc-147">См. также</span><span class="sxs-lookup"><span data-stu-id="e11bc-147">See Also</span></span>  
 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 [<span data-ttu-id="e11bc-148">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="e11bc-148">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="e11bc-149">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="e11bc-149">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="e11bc-150">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="e11bc-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="e11bc-151">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="e11bc-151">\<clientCredentials></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)  
 [<span data-ttu-id="e11bc-152">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="e11bc-152">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
