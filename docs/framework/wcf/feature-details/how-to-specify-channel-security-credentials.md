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
# <a name="how-to-specify-channel-security-credentials"></a>Практическое руководство. Задание учетных данных безопасности канала
Моникер служб Windows Communication Foundation (WCF) позволяет приложениям COM вызывать службы WCF. Большинство служб WCF потребовать от клиента указать учетные данные для проверки подлинности и авторизации. При вызове службы WCF из клиента WCF, можно указать эти учетные данные в управляемом коде или в файле конфигурации приложения. При вызове службы WCF из приложения COM, можно использовать <xref:System.ServiceModel.ComIntegration.IChannelCredentials> интерфейс, чтобы указать учетные данные. В данном разделе описаны различные способы указания учетных данных с использованием интерфейса <xref:System.ServiceModel.ComIntegration.IChannelCredentials>.  
  
> [!NOTE]
>  <xref:System.ServiceModel.ComIntegration.IChannelCredentials> — Это интерфейс на основе IDispatch, и вы не получите функциональных возможностях IntelliSense в среде Visual Studio.  
  
 В этой статье будет использовать службу WCF, определенные в [пример безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-sample.md).  
  
### <a name="to-specify-a-client-certificate"></a>Задание сертификата клиента  
  
1. Запустите файл Setup.bat в каталоге "Безопасность сообщений", чтобы создать и установить требуемые тестовые сертификаты.  
  
2. Откройте проект безопасности сообщений.  
  
3. Добавить `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` для `ICalculator` определение интерфейса.  
  
4. Добавить `bindingNamespace="http://Microsoft.ServiceModel.Samples"` в тег конечной точки в файле App.config для службы.  
  
5. Создайте образец безопасности сообщений и запустите файл Service.exe. Используйте Internet Explorer и перейдите к URI службы (http://localhost:8000/ServiceModelSamples/Service) чтобы убедиться, что служба работает.  
  
6. Откройте Visual Basic 6.0 и создайте новый стандартный EXE-файл. Добавьте в форму кнопку и дважды щелкните ее, чтобы добавить следующий код в обработчик щелчка.  
  
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
  
7. Запустите приложение Visual Basic и проверьте результаты.  
  
     Приложение Visual Basic отобразит окно сообщений с результатом вызова Add(3, 4). <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> или <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> также может использоваться вместо <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> задать сертификат клиента:  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  Чтобы этот вызов работал, сертификат клиента должен быть доверенным на компьютере, на котором выполняется клиент.  
  
> [!NOTE]
>  Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка". При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
### <a name="to-specify-user-name-and-password"></a>Задание имени пользователя и пароля  
  
1. Измените файл App.config службы, чтобы использовать привязку `wsHttpBinding`. Это необходимо для проверки имени пользователя и пароля.  

2. Задайте для атрибута `clientCredentialType` значение UserName.  

3. Откройте Visual Basic 6.0 и создайте новый стандартный EXE-файл. Добавьте в форму кнопку и дважды щелкните ее, чтобы добавить следующий код в обработчик щелчка.  
  
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
  
4. Запустите приложение Visual Basic и проверьте результаты. Приложение Visual Basic отобразит окно сообщений с результатом вызова Add(3, 4).  
  
    > [!NOTE]
    >  Привязка, заданная в моникере служб в этом примере, изменена на WSHttpBinding_ICalculator. Также обратите внимание, что необходимо предоставить действительные имя пользователя и пароль в вызове метода <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.  
  
### <a name="to-specify-windows-credentials"></a>Задание учетных данных Windows  
  
1. Задайте для атрибута `clientCredentialType` значение Windows в файле App.config службы.  

2. Откройте Visual Basic 6.0 и создайте новый стандартный EXE-файл. Добавьте в форму кнопку и дважды щелкните ее, чтобы добавить следующий код в обработчик щелчка.  
  
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
  
3. Запустите приложение Visual Basic и проверьте результаты. Приложение Visual Basic отобразит окно сообщений с результатом вызова Add(3, 4).  
  
    > [!NOTE]
    >  Необходимо заменить "domain", "userID" и "password" на действительные значения.  
  
### <a name="to-specify-an-issue-token"></a>Задание маркера вопроса  
  
1. Маркеры вопроса используются только для приложений с федеративной безопасностью. Дополнительные сведения о федеративной безопасности, см. в разделе [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) и [пример федерации](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
     В следующем примере кода Visual Basic показано, как вызывать метод <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     Дополнительные сведения о параметрах для этого метода см. в разделе <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
## <a name="see-also"></a>См. также

- [Федерация](../../../../docs/framework/wcf/feature-details/federation.md)
- [Практическое руководство. Настройка учетных данных службы федерации](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Практическое руководство. Создание федеративного клиента](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Безопасность сообщений](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
