---
title: Авторизация доступа к операциям службы
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: c2ad6977674666ef65df1ea4cfe58cfd4bff8b69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183928"
---
# <a name="authorizing-access-to-service-operations"></a>Авторизация доступа к операциям службы
В этом примере показано, как использовать [ \<службуАвторации>,](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) чтобы использовать <xref:System.Security.Permissions.PrincipalPermissionAttribute> атрибут для авторизации доступа к операциям службы. Этот образец основан на примере [Getting Started.](../../../../docs/framework/wcf/samples/getting-started-sample.md) Служба и клиент настроены с помощью [ \<wsHttpBinding>. ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Атрибут `mode` [ \<>безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) был установлен `Message` `clientCredentialType` и установлен `Windows`на . К каждому методу службы применяется <xref:System.Security.Permissions.PrincipalPermissionAttribute> и используется для ограничения доступа к каждой операции. Чтобы получить доступ к каждой операции, вызывающий объект должен быть администратором Windows.  
  
 В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Файл конфигурации службы использует>`principalPermissionMode` [ \<службы Авторизации](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для установки атрибута:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Настройка `principalPermissionMode` как `UseWindowsGroups` позволяет использовать <xref:System.Security.Permissions.PrincipalPermissionAttribute> на основе имен групп Windows.  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> применяется к каждой операции, чтобы вызывающий объект входил в группу администраторов Windows, как показано в следующем образце кода.  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Клиент успешно связывается с каждой операцией, если он работает в учетной записи, входящей в группу «Администраторы». В противном случае доступ запрещен. Чтобы поэкспериментировать со сбоем авторизации, запустите клиент в учетной записи, не входящей в группу "Администраторы". Чтобы закрыть клиент, нажмите клавишу ВВОД в окне консоли.  
  
 Службу можно уведомить о сбоях авторизации, реализовав <xref:System.ServiceModel.Dispatcher.IErrorHandler>. Подробнее о [реализации](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) `IErrorHandler`см.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
