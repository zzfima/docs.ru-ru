---
title: "Как проверить подлинность с использованием имени и пароля пользователя | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "проверка подлинности [WCF], имя пользователя и пароль"
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Как проверить подлинность с использованием имени и пароля пользователя
В этом разделе показано, как включить службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для проверки подлинности клиента с помощью имени пользователя домена Windows и пароля.Предполагается, что это рабочая резидентная служба WCF.Пример создания базовой резидентной службы WCF см. в разделе [Учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md).В этом разделе предполагается, что служба настраивается в коде.Пример настройки похожей службы с помощью файла конфигурации см. в разделе [Безопасность сообщений с использованием имени пользователя](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
  
 Чтобы настроить службу для проверки подлинности клиентов по имени пользователя и паролю в домене Windows, используйте <xref:System.ServiceModel.WSHttpBinding>, установив свойство `Security.Mode` в значение `Message`.Кроме этого, необходимо указать сертификат X509, который будет использован для шифрования имени пользователя и пароля, так как они передаются от клиента к службе.  
  
 На стороне клиента необходимо запрашивать у пользователя учетные данные и указать учетные данные пользователя в клиентском классе\-посреднике WCF.  
  
### Чтобы настроить службу WCF для проверки подлинности, используйте имя пользователя и пароль в домене Windows.  
  
1.  Создайте экземпляр <xref:System.ServiceModel.WSHttpBinding>, установите режим безопасности привязки в `SecurityMode.Message`, установите `ClientCredentialType` привязки в значение `MessageCredentialType.UserName` и добавьте в узел службы конечную точку службы с помощью заданной привязки, как показано в следующем коде.  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  Задает сертификат сервера, используемый для шифрования имени пользователя и пароля, передаваемых по сети.Этот код должен непосредственно следовать за показанным выше кодом.В следующем примере используется сертификат, созданный файлом setup.bat из образца [Безопасность сообщений с использованием имени пользователя](../../../../docs/framework/wcf/samples/message-security-user-name.md).  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     Вы можете использовать собственный сертификат, просто укажите ссылку на него в коде.Дополнительные сведения о создании и использовании сертификатов см. в разделе [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).Убедитесь, что сертификат находится в хранилище сертификатов «Доверенные лица» для локального компьютера.Это вы можете сделать, запустив mmc.exe и выбрав в меню **Файл** пункт **Добавить или удалить оснастку...**.В диалоговом окне **Добавление или удаление оснастки** выберите **Оснастка диспетчера сертификатов** и нажмите кнопку **Добавить**.В диалоговом окне «Оснастка диспетчера сертификатов» выберите **Учетная запись компьютера**.По умолчанию сертификат, сформированный из образца «Безопасность сообщений с использованием имени пользователя», будет находиться в папке «Личные\/Сертификаты».Он будет указан как «localhost» в столбце «Выпущен» в окне ММС.Перетащите сертификат в папку **Доверенные лица**.Это позволит WCF считать сертификат доверенным при выполнении аутентификации.  
  
### Вызов службы с передачей имени пользователя и пароля  
  
1.  Клиентское приложение должно предложить пользователю ввести имя пользователя и пароль.Следующий код запрашивает у пользователя имя пользователя и пароль.  
  
    > [!WARNING]
    >  Этот код не следует использовать в рабочей среде, поскольку пароль во время ввода отображается на экране.  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
  
    ```  
  
2.  Создайте экземпляр клиентского класса\-посредника, указав учетные данные клиента, как это показано в следующем коде:  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## См. также  
 <xref:System.ServiceModel.WsHttpBinding>   
 <xref:System.ServiceModel.WSHttpSecurity>   
 <xref:System.ServiceModel.SecurityMode>   
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>   
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>   
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>   
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>   
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>   
 [Безопасность транспорта с обычной проверкой подлинности](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)   
 [Защита распределенных приложений](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)   
 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)