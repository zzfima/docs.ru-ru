---
title: "Использование в WCF нескольких схем проверки подлинности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Использование в WCF нескольких схем проверки подлинности
В WCF теперь можно указать несколько схем проверки подлинности на одной конечной точке.  Кроме того, службы, размещенные на веб\-серверах, могут наследовать свои параметры проверки подлинности непосредственно из IIS.  Резидентные службы могут указывать, какие схемы проверки подлинности можно использовать.  Дополнительные сведения о настройке параметров проверки подлинности в IIS см. в разделе [Проверка подлинности IIS](http://go.microsoft.com/fwlink/?LinkId=232458)  
  
## Службы, размещенные в IIS  
 Для служб, размещенных в IIS, задайте схемы проверки подлинности, которые планируется использовать в IIS.  Затем в настройках привязки в файле конфигурации web.config службы укажите тип clientCredential как InheritedFromHost, как показано в следующем фрагменте кода XML:  
  
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
  
 С помощью ServiceAuthenticationBehavior или элемента \<serviceAuthenticationManager\> можно указать, что со службой можно использовать только подмножество схем проверки подлинности.  Настраивая это в коде, используйте ServiceAuthenticationBehavior, как показано в следующем фрагменте кода.  
  
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
  
 Настраивая это в файле конфигурации, используйте элемент \<serviceAuthenticationManager\>, как показано в следующем фрагменте кода XML.  
  
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
  
 Это гарантирует использование только подмножество перечисленных здесь схем проверки подлинности для применения на конечной точке службы в зависимости от того, что было выбрано на IIS.  Это означает, что разработчик может исключить, например, простую проверку подлинности из списка путем исключения ее из списка serviceAuthenticationManager, и она не будет применена на конечной точке службы, даже если она активирована в IIS.  
  
## Резидентные службы  
 Резидентные службы настраиваются несколько иначе, так как отсутствует наследование параметров из IIS.  Здесь элемент \<serviceAuthenticationManager\> или ServiceAuthenticationBehavior используется для указания наследуемых параметров проверки подлинности.  Соответствующий код выглядит следующим образом:  
  
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
  
## См. также  
 [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)   
 [Конечные точки: адреса, привязки и контракты](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)   
 [Настройка привязок, предоставляемых системой](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)   
 [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)   
 [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)