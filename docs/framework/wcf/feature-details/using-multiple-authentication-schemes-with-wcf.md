---
title: Использование в WCF нескольких схем проверки подлинности
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: b0f5da9a4c6fdfede9a86434f49f9e9821778176
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102314"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>Использование в WCF нескольких схем проверки подлинности
В WCF теперь можно указать несколько схем проверки подлинности на одной конечной точке. Кроме того, службы, размещенные на веб-серверах, могут наследовать свои параметры проверки подлинности непосредственно из IIS. Резидентные службы могут указывать, какие схемы проверки подлинности можно использовать. Дополнительные сведения о настройке параметров проверки подлинности в службах IIS, см. в разделе [проверки подлинности IIS](https://go.microsoft.com/fwlink/?LinkId=232458)  
  
## <a name="iis-hosted-services"></a>Службы, размещенные в IIS  
 Для служб, размещенных в IIS, задайте схемы проверки подлинности, которые планируется использовать в IIS. Затем в файле web.config службы, в конфигурации привязки укажите тип clientCredential как «InheritedFromHost» как показано в следующем фрагменте XML:  
  
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
  
 Можно указать, что требуется только подмножество схем проверки подлинности для использования с вашей службой, с помощью ServiceAuthenticationBehavior или \<serviceAuthenticationManager > элемента. Настраивая это в коде, используйте ServiceAuthenticationBehavior, как показано в следующем фрагменте кода.  
  
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
  
 Настраивая это в файле конфигурации, используйте \<serviceAuthenticationManager > элемента, как показано в следующем фрагменте кода XML.  
  
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
  
 Это гарантирует использование только подмножество перечисленных здесь схем проверки подлинности для применения на конечной точке службы в зависимости от того, что было выбрано на IIS. Это означает, что разработчик может исключить, например, простую проверку подлинности из списка путем исключения ее из списка serviceAuthenticationManager, и она не будет применена на конечной точке службы, даже если она активирована в IIS.  
  
## <a name="self-hosted-services"></a>Резидентные службы  
 Резидентные службы настраиваются несколько иначе, так как отсутствует наследование параметров из IIS. Здесь используется \<serviceAuthenticationManager > элемента или ServiceAuthenticationBehavior для указания наследуемых параметров проверки подлинности. Соответствующий код выглядит следующим образом:  
  
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
  
 В конфигурации это выглядит следующим образом:  
  
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
  
 Затем можно указать InheritFromHost в параметрах привязки, как показано в следующем фрагменте кода XML.  
  
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
  
 Кроме того, можно определить схемы проверки подлинности в пользовательской привязке, задав схемы проверки подлинности на элементе привязки транспорта HTTP, как показано в следующем фрагменте конфигурации.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a>См. также

- [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [Конечные точки: Адреса, привязки и контракты](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Настройка привязок, предоставляемых системой](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)
- [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)
