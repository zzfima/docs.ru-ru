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
# <a name="authorizing-access-to-service-operations"></a><span data-ttu-id="bd42e-102">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="bd42e-102">Authorizing Access to Service Operations</span></span>
<span data-ttu-id="bd42e-103">В этом примере показано, как использовать [ \<службуАвторации>,](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) чтобы использовать <xref:System.Security.Permissions.PrincipalPermissionAttribute> атрибут для авторизации доступа к операциям службы.</span><span class="sxs-lookup"><span data-stu-id="bd42e-103">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span> <span data-ttu-id="bd42e-104">Этот образец основан на примере [Getting Started.](../../../../docs/framework/wcf/samples/getting-started-sample.md)</span><span class="sxs-lookup"><span data-stu-id="bd42e-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) sample.</span></span> <span data-ttu-id="bd42e-105">Служба и клиент настроены с помощью [ \<wsHttpBinding>. ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="bd42e-105">The service and client are configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="bd42e-106">Атрибут `mode` [ \<>безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) был установлен `Message` `clientCredentialType` и установлен `Windows`на .</span><span class="sxs-lookup"><span data-stu-id="bd42e-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="bd42e-107">К каждому методу службы применяется <xref:System.Security.Permissions.PrincipalPermissionAttribute> и используется для ограничения доступа к каждой операции.</span><span class="sxs-lookup"><span data-stu-id="bd42e-107">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each service method and used to restrict access to each operation.</span></span> <span data-ttu-id="bd42e-108">Чтобы получить доступ к каждой операции, вызывающий объект должен быть администратором Windows.</span><span class="sxs-lookup"><span data-stu-id="bd42e-108">The caller must be a Windows administrator to access each operation.</span></span>  
  
 <span data-ttu-id="bd42e-109">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="bd42e-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd42e-110">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="bd42e-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="bd42e-111">Файл конфигурации службы использует>`principalPermissionMode` [ \<службы Авторизации](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для установки атрибута:</span><span class="sxs-lookup"><span data-stu-id="bd42e-111">The service configuration file uses the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to set the `principalPermissionMode` attribute:</span></span>  
  
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
  
 <span data-ttu-id="bd42e-112">Настройка `principalPermissionMode` как `UseWindowsGroups` позволяет использовать <xref:System.Security.Permissions.PrincipalPermissionAttribute> на основе имен групп Windows.</span><span class="sxs-lookup"><span data-stu-id="bd42e-112">Setting the `principalPermissionMode` to `UseWindowsGroups` enables the use of <xref:System.Security.Permissions.PrincipalPermissionAttribute> based on Windows group names.</span></span>  
  
 <span data-ttu-id="bd42e-113"><xref:System.Security.Permissions.PrincipalPermissionAttribute> применяется к каждой операции, чтобы вызывающий объект входил в группу администраторов Windows, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="bd42e-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each operation to require the caller to be part of the Windows administrators group, as shown in the following sample code.</span></span>  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 <span data-ttu-id="bd42e-114">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="bd42e-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="bd42e-115">Клиент успешно связывается с каждой операцией, если он работает в учетной записи, входящей в группу «Администраторы». В противном случае доступ запрещен.</span><span class="sxs-lookup"><span data-stu-id="bd42e-115">The client successfully communicates with each operation if it is running under an account that is part of the Administrators group; otherwise, access is denied.</span></span> <span data-ttu-id="bd42e-116">Чтобы поэкспериментировать со сбоем авторизации, запустите клиент в учетной записи, не входящей в группу "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="bd42e-116">To experiment with authorization failure, run the client under an account that is not part of the Administrators group.</span></span> <span data-ttu-id="bd42e-117">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="bd42e-117">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="bd42e-118">Службу можно уведомить о сбоях авторизации, реализовав <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="bd42e-118">A service can be notified of authorization failures by implementing an <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span></span> <span data-ttu-id="bd42e-119">Подробнее о [реализации](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) `IErrorHandler`см.</span><span class="sxs-lookup"><span data-stu-id="bd42e-119">See [Extending Control Over Error Handling and Reporting](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) for information about implementing `IErrorHandler`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bd42e-120">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="bd42e-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bd42e-121">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="bd42e-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="bd42e-122">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bd42e-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="bd42e-123">Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="bd42e-123">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
