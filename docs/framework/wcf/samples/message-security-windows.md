---
title: Безопасность сообщений с использованием механизмов Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7bf731c1accd6eefc97c27af58ba139992ae1866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502365"
---
# <a name="message-security-windows"></a>Безопасность сообщений с использованием механизмов Windows
В этом образце показывается, как настраивать привязку <xref:System.ServiceModel.WSHttpBinding> для использования безопасности на уровне сообщений с проверкой подлинности Windows. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md). В этом образце служба размещается в службах IIS, а клиентом является консольное приложение (EXE).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Безопасность по умолчанию для [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) — безопасность сообщений с использованием проверки подлинности Windows. Файлы конфигурации в этом примере явно задать `mode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) для `Message` и `clientCredentialType` атрибут `Windows`. Эти значения являются значениями по умолчанию для этой привязки, но они были явно заданы, как показано в следующем образце конфигурации с целью демонстрации их использования.  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта. Привязка клиента настраивается с помощью соответствующих `securityMode` и `authenticationMode`.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      <!--The default security for the WSHttpBinding is-->  
      <!--Message security using Windows authentication. -->  
      <!--This configuration explicitly defines the security mode -->  
      <!--as Message and the clientCredentialType as Windows  -->  
      <!--for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Исходный код службы был изменен, чтобы показать, как можно использовать <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> для доступа к идентификатору вызывающего объекта.  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Первый вызываемый метод - `GetCallerIdentity` - возвращает имя идентификатора вызывающего объекта для клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне консоли.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также
