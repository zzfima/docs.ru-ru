---
title: Авторизация доступа к операциям службы
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: a0ea82c876b3bd8c2a3218f84399fbb69e1d0080
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932500"
---
# <a name="authorizing-access-to-service-operations"></a>Авторизация доступа к операциям службы
В этом примере показано, <xref:System.Security.Permissions.PrincipalPermissionAttribute> [ \<как использовать > ServiceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) , чтобы разрешить использование атрибута для авторизации доступа к операциям службы. Этот пример основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) . Служба и клиент настраиваются с помощью [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). `Message` `clientCredentialType` [Атрибут > безопасностибылустановленвзначениеиимеетзначение.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `mode` `Windows` К каждому методу службы применяется <xref:System.Security.Permissions.PrincipalPermissionAttribute> и используется для ограничения доступа к каждой операции. Чтобы получить доступ к каждой операции, вызывающий объект должен быть администратором Windows.  
  
 В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Файл конфигурации службы использует [ \<> ServiceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для задания `principalPermissionMode` атрибута:  
  
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
  
 Службу можно уведомить о сбоях авторизации, реализовав <xref:System.ServiceModel.Dispatcher.IErrorHandler>. Сведения о реализации `IErrorHandler`см. в разделе [расширение управления обработкой ошибок и создание отчетов](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) .  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
