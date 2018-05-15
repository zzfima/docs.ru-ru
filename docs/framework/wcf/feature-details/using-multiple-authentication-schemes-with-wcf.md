---
title: Использование в WCF нескольких схем проверки подлинности
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 140211f10f7cdc88a3df8eb8ea1c30df73b0c4c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="8f2fd-102">Использование в WCF нескольких схем проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8f2fd-102">Using Multiple Authentication Schemes with WCF</span></span>
<span data-ttu-id="8f2fd-103">В WCF теперь можно указать несколько схем проверки подлинности на одной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="8f2fd-104">Кроме того, службы, размещенные на веб-серверах, могут наследовать свои параметры проверки подлинности непосредственно из IIS.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="8f2fd-105">Резидентные службы могут указывать, какие схемы проверки подлинности можно использовать.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="8f2fd-106">Дополнительные сведения о настройке параметров проверки подлинности в службах IIS см. в разделе [проверки подлинности IIS](http://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="8f2fd-106">For more information about setting authentication settings in IIS, see [IIS Authentication](http://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="8f2fd-107">Службы, размещенные в IIS</span><span class="sxs-lookup"><span data-stu-id="8f2fd-107">IIS-Hosted Services</span></span>  
 <span data-ttu-id="8f2fd-108">Для служб, размещенных в IIS, задайте схемы проверки подлинности, которые планируется использовать в IIS.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="8f2fd-109">Затем в файле web.config приложения службы, в конфигурацию привязки укажите тип clientCredential как «InheritedFromHost» как показано в следующем фрагменте кода XML:</span><span class="sxs-lookup"><span data-stu-id="8f2fd-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="8f2fd-110">Можно указать, что требуется только подмножество схем проверки подлинности для использования со службой с помощью ServiceAuthenticationBehavior или \<serviceAuthenticationManager > элемент.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="8f2fd-111">Настраивая это в коде, используйте ServiceAuthenticationBehavior, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="8f2fd-112">Настраивая это в файле конфигурации, используйте \<serviceAuthenticationManager > элемента, как показано в следующем фрагменте кода XML.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="8f2fd-113">Это гарантирует использование только подмножество перечисленных здесь схем проверки подлинности для применения на конечной точке службы в зависимости от того, что было выбрано на IIS.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="8f2fd-114">Это означает, что разработчик может исключить, например, простую проверку подлинности из списка путем исключения ее из списка serviceAuthenticationManager, и она не будет применена на конечной точке службы, даже если она активирована в IIS.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="8f2fd-115">Резидентные службы</span><span class="sxs-lookup"><span data-stu-id="8f2fd-115">Self-Hosted Services</span></span>  
 <span data-ttu-id="8f2fd-116">Резидентные службы настраиваются несколько иначе, так как отсутствует наследование параметров из IIS.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="8f2fd-117">Здесь используется \<serviceAuthenticationManager > элемент или ServiceAuthenticationBehavior, чтобы задать параметры проверки подлинности, которые будут унаследованы.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="8f2fd-118">Соответствующий код выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8f2fd-118">In code it looks like this:</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="8f2fd-119">В конфигурации это выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8f2fd-119">In config, it looks like this:</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="8f2fd-120">Затем можно указать InheritFromHost в параметрах привязки, как показано в следующем фрагменте кода XML.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="8f2fd-121">Кроме того, можно определить схемы проверки подлинности в пользовательской привязке, задав схемы проверки подлинности на элементе привязки транспорта HTTP, как показано в следующем фрагменте конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8f2fd-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f2fd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8f2fd-122">See Also</span></span>  
 [<span data-ttu-id="8f2fd-123">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="8f2fd-123">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="8f2fd-124">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="8f2fd-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="8f2fd-125">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="8f2fd-125">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8f2fd-126">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="8f2fd-126">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="8f2fd-127">Привязки</span><span class="sxs-lookup"><span data-stu-id="8f2fd-127">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="8f2fd-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="8f2fd-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="8f2fd-129">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="8f2fd-129">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
