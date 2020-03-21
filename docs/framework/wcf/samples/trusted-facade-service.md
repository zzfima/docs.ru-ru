---
title: Доверенная фасадная служба
ms.date: 03/30/2017
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
ms.openlocfilehash: 17901b7a68d4701287d02bc7ee3174683e777fd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143750"
---
# <a name="trusted-facade-service"></a><span data-ttu-id="62af6-102">Доверенная фасадная служба</span><span class="sxs-lookup"><span data-stu-id="62af6-102">Trusted Facade Service</span></span>
<span data-ttu-id="62af6-103">В этом примере сценария показано, как передавать идентификационную информацию вызывающего абонента из одной службы в другую с помощью инфраструктуры безопасности Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="62af6-103">This scenario sample demonstrates how to flow caller's identity information from one service to another using Windows Communication Foundation (WCF) security infrastructure.</span></span>  
  
 <span data-ttu-id="62af6-104">Обычно разработчики обеспечивают предоставление функциональных возможностей службы в открытую сеть через "фасадную" службу.</span><span class="sxs-lookup"><span data-stu-id="62af6-104">It is a common design pattern to expose the functionality provided by a service to the public network using a façade service.</span></span> <span data-ttu-id="62af6-105">Фасадная служба обычно размещается в демилитаризованной зоне (также называемой промежуточной подсетью или DMZ) и взаимодействует с серверной службой, реализующей бизнес-логику и имеющей доступ к внутренним данным.</span><span class="sxs-lookup"><span data-stu-id="62af6-105">The façade service typically resides in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet) and communicates with a backend service that implements the business logic and has access to internal data.</span></span> <span data-ttu-id="62af6-106">Коммуникационный канал между фасадной службой и серверной службой проходит через брандмауэр, и обычно он используется только для одной цели.</span><span class="sxs-lookup"><span data-stu-id="62af6-106">The communication channel between the façade service and the backend service goes through a firewall and is usually limited for a single purpose only.</span></span>  
  
 <span data-ttu-id="62af6-107">Код в этом образце состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="62af6-107">This sample consists of the following components:</span></span>  
  
- <span data-ttu-id="62af6-108">Клиентская часть калькулятора</span><span class="sxs-lookup"><span data-stu-id="62af6-108">Calculator client</span></span>  
  
- <span data-ttu-id="62af6-109">Фасадная служба калькулятора</span><span class="sxs-lookup"><span data-stu-id="62af6-109">Calculator façade service</span></span>  
  
- <span data-ttu-id="62af6-110">Серверная служба калькулятора</span><span class="sxs-lookup"><span data-stu-id="62af6-110">Calculator backend service</span></span>  
  
 <span data-ttu-id="62af6-111">Фасадная служба проверяет запрос и подлинность вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="62af6-111">The façade service is responsible for validating the request and authenticating the caller.</span></span> <span data-ttu-id="62af6-112">После успешного выполнения этих проверок она передает запрос серверной службе по управляемому коммуникационному каналу из демилитаризованной зоны во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="62af6-112">After successful authentication and validation, it forwards the request to the backend service using the controlled communication channel from the perimeter network to the internal network.</span></span> <span data-ttu-id="62af6-113">В передаваемый запрос фасадная служба добавляет удостоверение вызывающей стороны, чтобы серверная служба могла использовать его при обработке.</span><span class="sxs-lookup"><span data-stu-id="62af6-113">As a part of the forwarded request, the façade service includes information about the caller's identity so that the backend service can use this information in its processing.</span></span> <span data-ttu-id="62af6-114">Это удостоверение передается с помощью маркера безопасности `Username` в заголовке сообщения `Security` .</span><span class="sxs-lookup"><span data-stu-id="62af6-114">The caller's identity is transmitted using a `Username` security token inside the message `Security` header.</span></span> <span data-ttu-id="62af6-115">Выборка использует инфраструктуру безопасности WCF для `Security` передачи и извлечения этой информации из заголовка.</span><span class="sxs-lookup"><span data-stu-id="62af6-115">The sample uses the WCF security infrastructure to transmit and extract this information from the `Security` header.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="62af6-116">Серверная служба доверяет результатам проверки подлинности вызывающей стороны, выполненной фасадной службой.</span><span class="sxs-lookup"><span data-stu-id="62af6-116">The backend service trusts the façade service to authenticate the caller.</span></span> <span data-ttu-id="62af6-117">Поэтому серверная служба не выполняет проверку подлинности повторно. Она использует удостоверение, предоставленное фасадной службой в переданном запросе.</span><span class="sxs-lookup"><span data-stu-id="62af6-117">Because of this, the backend service does not authenticate the caller again; it uses the identity information provided by the façade service in the forwarded request.</span></span> <span data-ttu-id="62af6-118">Это отношение доверия требует, чтобы серверная служба проверяла подлинность фасадной службы, чтобы убедиться, что сообщение передано из надежного источника (в данном случае - от фасадной службы).</span><span class="sxs-lookup"><span data-stu-id="62af6-118">Because of this trust relationship, the backend service must authenticate the façade service to ensure that the forwarded message comes from a trusted source - in this case, the façade service.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="62af6-119">Реализация</span><span class="sxs-lookup"><span data-stu-id="62af6-119">Implementation</span></span>  
 <span data-ttu-id="62af6-120">В этом образце используются два пути обмена данными:</span><span class="sxs-lookup"><span data-stu-id="62af6-120">There are two communication paths in this sample.</span></span> <span data-ttu-id="62af6-121">между клиентом и фасадной службой и между фасадной службой и серверной службой.</span><span class="sxs-lookup"><span data-stu-id="62af6-121">First is between the client and the façade service, the second is between the façade service and the backend service.</span></span>  
  
### <a name="communication-path-between-client-and-faade-service"></a><span data-ttu-id="62af6-122">Путь обмена данными между клиентом и фасадной службой</span><span class="sxs-lookup"><span data-stu-id="62af6-122">Communication Path between Client and Façade Service</span></span>  
 <span data-ttu-id="62af6-123">На пути обмена данными между клиентом и фасадной службой используется привязка `wsHttpBinding` и тип учетных данных клиента `UserName` .</span><span class="sxs-lookup"><span data-stu-id="62af6-123">The client to the façade service communication path uses `wsHttpBinding` with a `UserName` client credential type.</span></span> <span data-ttu-id="62af6-124">Это означает, что фасадная служба проверяет подлинность клиента по имени пользователя и паролю, а клиент проверяет подлинность фасадной службы с помощью сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="62af6-124">This means that the client uses username and password to authenticate to the façade service and the façade service uses X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="62af6-125">Конфигурация привязки выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="62af6-125">The binding configuration looks like the following example.</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="62af6-126">Фасадная служба проверяет подлинность вызывающей стороны с помощью пользовательской реализации класса `UserNamePasswordValidator` .</span><span class="sxs-lookup"><span data-stu-id="62af6-126">The façade service authenticates the caller using custom `UserNamePasswordValidator` implementation.</span></span> <span data-ttu-id="62af6-127">Для простоты примера проверка подлинности проверяет только соответствие имени пользователя представленному паролю.</span><span class="sxs-lookup"><span data-stu-id="62af6-127">For demonstration purposes, the authentication only ensures that the caller's username matches the presented password.</span></span> <span data-ttu-id="62af6-128">На практике проверка подлинности пользователя обычно выполняется с помощью Active Directory или пользовательского поставщика членства ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="62af6-128">In the real world situation, the user is probably authenticated using Active Directory or custom ASP.NET Membership provider.</span></span> <span data-ttu-id="62af6-129">Код, реализующий проверку подлинности, находится в файле `FacadeService.cs` .</span><span class="sxs-lookup"><span data-stu-id="62af6-129">The validator implementation resides in `FacadeService.cs` file.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="62af6-130">Пользовательский модуль проверки настроен для использования в рамках поведения `serviceCredentials` в файле конфигурации фасадной службы.</span><span class="sxs-lookup"><span data-stu-id="62af6-130">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span> <span data-ttu-id="62af6-131">Это поведение также используется для настройки сертификата X.509 службы.</span><span class="sxs-lookup"><span data-stu-id="62af6-131">This behavior is also used to configure the service's X.509 certificate.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate
               findValue="localhost"
               storeLocation="LocalMachine"
               storeName="My"
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a><span data-ttu-id="62af6-132">Путь обмена данными между фасадной службой и серверной службой</span><span class="sxs-lookup"><span data-stu-id="62af6-132">Communication Path between Façade Service and Backend Service</span></span>  
 <span data-ttu-id="62af6-133">На пути обмена данными между фасадной службой и серверной службой используется привязка `customBinding` , включающая в себя несколько элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="62af6-133">The façade service to the backend service communication path uses a `customBinding` that consists of several binding elements.</span></span> <span data-ttu-id="62af6-134">Эта привязка выполняет две задачи.</span><span class="sxs-lookup"><span data-stu-id="62af6-134">This binding accomplishes two things.</span></span> <span data-ttu-id="62af6-135">Она проверяет подлинность фасадной службы и серверной службы, обеспечивая безопасность связи и надежность источника данных.</span><span class="sxs-lookup"><span data-stu-id="62af6-135">It authenticates the façade service and backend service to ensure that the communication is secure and is coming from a trusted source.</span></span> <span data-ttu-id="62af6-136">Кроме того, она передает удостоверение изначальной вызывающей стороны в маркере безопасности `Username` .</span><span class="sxs-lookup"><span data-stu-id="62af6-136">Additionally, it also transmits the initial caller's identity inside the `Username` security token.</span></span> <span data-ttu-id="62af6-137">В этом случае серверной службе передается только имя пользователя изначальной вызывающей стороны (пароль не указывается в сообщении).</span><span class="sxs-lookup"><span data-stu-id="62af6-137">In this case, only the initial caller's username is transmitted to the backend service, the password is not included in the message.</span></span> <span data-ttu-id="62af6-138">Это обуславливается тем, что серверная служба доверяет фасадной службе проверку подлинности вызывающей стороны, выполняемую перед отправкой запроса.</span><span class="sxs-lookup"><span data-stu-id="62af6-138">This is because the backend service trusts the façade service to authenticate the caller before forwarding the request to it.</span></span> <span data-ttu-id="62af6-139">Поскольку серверная служба проверяет подлинность фасадной службы, она доверяет информации, содержащейся в переданном от нее запросе.</span><span class="sxs-lookup"><span data-stu-id="62af6-139">Because the façade service authenticates itself to the backend service, the backend service can trust the information contained in the forwarded request.</span></span>  
  
 <span data-ttu-id="62af6-140">Ниже приведена конфигурация привязки для этого пути обмена данными.</span><span class="sxs-lookup"><span data-stu-id="62af6-140">The following is the binding configuration for this communication path.</span></span>  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="62af6-141">[ \<Элемент безопасности>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) связывающий элемент заботится о передаче и извлечении имени пользователя исходного абонента.</span><span class="sxs-lookup"><span data-stu-id="62af6-141">The [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) binding element takes care of the initial caller's username transmission and extraction.</span></span> <span data-ttu-id="62af6-142">WindowsStreamSecurity>и [ \<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) заботиться о аутентификации фасада и бэкэнд услуг и защиты сообщений. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="62af6-142">The [\<windowsStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md) and [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) take care of authenticating façade and backend services and message protection.</span></span>  
  
 <span data-ttu-id="62af6-143">Для переадресовывания запроса реализация службы фасада должна предоставить имя пользователя исходного вызываемого абонента, чтобы инфраструктура безопасности WCF смогли поместить это в переадресованное сообщение.</span><span class="sxs-lookup"><span data-stu-id="62af6-143">To forward the request, the façade service implementation must provide the initial caller's username so that WCF security infrastructure can place this into the forwarded message.</span></span> <span data-ttu-id="62af6-144">Фасадная служба предоставляет имя пользователя изначальной вызывающей стороны в виде значения свойства `ClientCredentials` экземпляра клиентского прокси-класса, используемого для обмена информацией между фасадной и серверной службами.</span><span class="sxs-lookup"><span data-stu-id="62af6-144">The initial caller's username is provided in the façade service implementation by setting it in the `ClientCredentials` property on the client proxy instance that façade service uses to communicate with the backend service.</span></span>  
  
 <span data-ttu-id="62af6-145">В следующем примере кода показана реализация метода `GetCallerIdentity` фасадной службы.</span><span class="sxs-lookup"><span data-stu-id="62af6-145">The following code shows how `GetCallerIdentity` method is implemented on the façade service.</span></span> <span data-ttu-id="62af6-146">В прочих методах используются аналогичные принципы.</span><span class="sxs-lookup"><span data-stu-id="62af6-146">Other methods use the same pattern.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 <span data-ttu-id="62af6-147">Как показано в предыдущем примере кода, в свойстве `ClientCredentials` не задается пароль (в нем содержится только имя пользователя).</span><span class="sxs-lookup"><span data-stu-id="62af6-147">As shown in the previous code, the password is not set on the `ClientCredentials` property, only the username is set.</span></span> <span data-ttu-id="62af6-148">Инфраструктура безопасности WCF создает маркер безопасности имени пользователя без пароля в данном случае, что и требуется в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="62af6-148">WCF security infrastructure creates a username security token without a password in this case, which is exactly what is required in this scenario.</span></span>  
  
 <span data-ttu-id="62af6-149">В серверной службе должна быть проверена подлинность информации, содержащейся в маркере безопасности.</span><span class="sxs-lookup"><span data-stu-id="62af6-149">On the backend service, the information contained in the username security token must be authenticated.</span></span> <span data-ttu-id="62af6-150">По умолчанию служба безопасности WCF пытается сопоставить пользователя с учетной записью Windows с помощью предоставленного пароля.</span><span class="sxs-lookup"><span data-stu-id="62af6-150">By default, WCF security attempts to map the user to a Windows account using the provided password.</span></span> <span data-ttu-id="62af6-151">В данном случае пароль не предоставляется, и серверной службе не требуется проверять имя пользователя, поскольку эта процедура уже выполнена фасадной службой.</span><span class="sxs-lookup"><span data-stu-id="62af6-151">In this case, there is no password provided and the backend service is not required to authenticate the username because the authentication was already performed by the façade service.</span></span> <span data-ttu-id="62af6-152">Для реализации этой функции в `UserNamePasswordValidator` WCF предусмотрен пользовательский обычай, который только присровает, что имя пользователя указано в маркере и не выполняет никакой дополнительной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="62af6-152">To implement this functionality in WCF, a custom `UserNamePasswordValidator` is provided that only enforces that a username is specified in the token and does not perform any additional authentication.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="62af6-153">Пользовательский модуль проверки настроен для использования в рамках поведения `serviceCredentials` в файле конфигурации фасадной службы.</span><span class="sxs-lookup"><span data-stu-id="62af6-153">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="62af6-154">Для извлечения имени пользователя и информации об учетной записи доверенной фасадной службы в серверной службе реализован класс `ServiceSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="62af6-154">To extract the username information and information about the trusted façade service account, the backend service implementation uses the `ServiceSecurityContext` class.</span></span> <span data-ttu-id="62af6-155">В следующем примере кода показана реализация метода `GetCallerIdentity` .</span><span class="sxs-lookup"><span data-stu-id="62af6-155">The following code shows how the `GetCallerIdentity` method is implemented.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 <span data-ttu-id="62af6-156">Информация об учетной записи фасадной службы извлекается с помощью свойства `ServiceSecurityContext.Current.WindowsIdentity` .</span><span class="sxs-lookup"><span data-stu-id="62af6-156">The façade service account information is extracted using the `ServiceSecurityContext.Current.WindowsIdentity` property.</span></span> <span data-ttu-id="62af6-157">Для доступа к информации об изначальной вызывающей стороне серверная служба использует свойство `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` .</span><span class="sxs-lookup"><span data-stu-id="62af6-157">To access the information about the initial caller the backend service uses the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` property.</span></span> <span data-ttu-id="62af6-158">Она выполняет поиск утверждения `Identity` , принадлежащего к типу `Name`.</span><span class="sxs-lookup"><span data-stu-id="62af6-158">It looks for an `Identity` claim with a type `Name`.</span></span> <span data-ttu-id="62af6-159">Эта претензия автоматически генерируется инфраструктурой безопасности `Username` WCF из информации, содержащейся в маркере безопасности.</span><span class="sxs-lookup"><span data-stu-id="62af6-159">This claim is automatically generated by WCF security infrastructure from the information contained in the `Username` security token.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="62af6-160">Выполнение примера</span><span class="sxs-lookup"><span data-stu-id="62af6-160">Running the sample</span></span>  
 <span data-ttu-id="62af6-161">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="62af6-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="62af6-162">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="62af6-162">Press ENTER in the client window to shut down the client.</span></span> <span data-ttu-id="62af6-163">Можно нажать клавишу ВВОД в окнах консолей фасадной и серверной служб, чтобы закрыть их.</span><span class="sxs-lookup"><span data-stu-id="62af6-163">You can press ENTER in the façade and backend service console windows to shut down the services.</span></span>  
  
```console  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="62af6-164">В состав образца сценария, где используется доверенная фасадная служба, входит пакетный файл Setup.bat, позволяющий настроить для сервера соответствующий сертификат для запуска фасадной службы, необходимый для проверки ее подлинности клиентом.</span><span class="sxs-lookup"><span data-stu-id="62af6-164">The Setup.bat batch file included with the Trusted Facade scenario sample enables you to configure the server with a relevant certificate to run the façade service that requires certificate-based security to authenticate itself to the client.</span></span> <span data-ttu-id="62af6-165">Подробные сведения см. в описании процедуры настройки в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="62af6-165">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="62af6-166">Ниже приводится краткое описание различных разделов пакетного файла.</span><span class="sxs-lookup"><span data-stu-id="62af6-166">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="62af6-167">Создание сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="62af6-167">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="62af6-168">Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="62af6-168">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```console  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="62af6-169">В переменной `%SERVER_NAME%` указывается имя сервера. Значение по умолчанию - localhost.</span><span class="sxs-lookup"><span data-stu-id="62af6-169">The `%SERVER_NAME%` variable specifies the server name - the default value is localhost.</span></span> <span data-ttu-id="62af6-170">Сертификат хранится в хранилище LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="62af6-170">The certificate is stored in the LocalMachine store.</span></span>  
  
- <span data-ttu-id="62af6-171">Установка сертификата фасадной службы в хранилище доверенных сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="62af6-171">Installing the façade service's certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="62af6-172">Следующая строка копирует сертификат фасадной службы в хранилище доверенных лиц клиента.</span><span class="sxs-lookup"><span data-stu-id="62af6-172">The following line copies the façade service's certificate into the client trusted people store.</span></span> <span data-ttu-id="62af6-173">Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.</span><span class="sxs-lookup"><span data-stu-id="62af6-173">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="62af6-174">Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.</span><span class="sxs-lookup"><span data-stu-id="62af6-174">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="62af6-175">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="62af6-175">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="62af6-176">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="62af6-176">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="62af6-177">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="62af6-177">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="62af6-178">Запуск образца на том же компьютере</span><span class="sxs-lookup"><span data-stu-id="62af6-178">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="62af6-179">Убедитесь, что путь включает папку, в которой хранится файл Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="62af6-179">Ensure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="62af6-180">Запустите файл Setup.bat из папки установки примера.</span><span class="sxs-lookup"><span data-stu-id="62af6-180">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="62af6-181">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="62af6-181">This installs all the certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="62af6-182">Запустите программу BackendService.exe из каталога \BackendService\bin в отдельном окне консоли.</span><span class="sxs-lookup"><span data-stu-id="62af6-182">Launch the BackendService.exe from \BackendService\bin directory in a separate console window</span></span>  
  
4. <span data-ttu-id="62af6-183">Запустите программу FacadeService.exe из каталога \FacadeService\bin в отдельном окне консоли.</span><span class="sxs-lookup"><span data-stu-id="62af6-183">Launch the FacadeService.exe from \FacadeService\bin directory in a separate console window</span></span>  
  
5. <span data-ttu-id="62af6-184">Запустите программу Client.exe из каталога \client\bin.</span><span class="sxs-lookup"><span data-stu-id="62af6-184">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="62af6-185">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="62af6-185">Client activity is displayed on the client console application.</span></span>  
  
6. <span data-ttu-id="62af6-186">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="62af6-186">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="62af6-187">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="62af6-187">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="62af6-188">После завершения работы примера запустите в папке примеров файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="62af6-188">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="62af6-189">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="62af6-189">The samples may already be installed on your machine.</span></span> <span data-ttu-id="62af6-190">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="62af6-190">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="62af6-191">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="62af6-191">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="62af6-192">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="62af6-192">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`  
