---
title: Практическое руководство. Проверка подлинности с использованием имени и пароля пользователя
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: b37d296312be4c7694a2db55d85dd618e3252f14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Практическое руководство. Проверка подлинности с использованием имени и пароля пользователя

В этом разделе показано, как включить службы Windows Communication Foundation (WCF) для проверки подлинности клиента с помощью имени пользователя домена Windows и пароля. Предполагается, что это рабочая резидентная служба WCF. Пример создания основных резидентной WCF службы см. в разделе [учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md). В этом разделе предполагается, что служба настраивается в коде. Если вы хотите проверить пример настройки аналогичную службу с помощью файла конфигурации см. раздел [имя пользователя безопасности сообщения](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
  
 Чтобы настроить службу для проверки подлинности клиентов по имени пользователя и паролю в домене Windows, используйте <xref:System.ServiceModel.WSHttpBinding>, установив свойство `Security.Mode` в значение `Message`. Кроме того, необходимо указать сертификат X509, который будет использован для шифрования имени пользователя и пароля, так как они передаются от клиента к службе.  
  
 На стороне клиента необходимо запрашивать у пользователя учетные данные и указать учетные данные пользователя в клиентском классе-посреднике WCF.  
  
## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>Чтобы настроить службу WCF для проверки подлинности с помощью имени пользователя домена Windows и пароль
  
1.  Создайте экземпляр <xref:System.ServiceModel.WSHttpBinding>, установите режим безопасности привязки в `SecurityMode.Message`, установите `ClientCredentialType` привязки в значение `MessageCredentialType.UserName` и добавьте в узел службы конечную точку службы с помощью заданной привязки, как показано в следующем коде:  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  Задает сертификат сервера, используемый для шифрования имени пользователя и пароля, передаваемых по сети. Этот код должен непосредственно следовать за показанным выше кодом. В следующем примере используется сертификат, созданный с помощью файла setup.bat из [имя пользователя безопасности сообщения](../../../../docs/framework/wcf/samples/message-security-user-name.md) образца:  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     Вы можете использовать собственный сертификат, просто укажите ссылку на него в коде. Дополнительные сведения о создании и использовании сертификатов в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Убедитесь, что сертификат находится в хранилище сертификатов «Доверенные лица» для локального компьютера. Это можно сделать, запустив mmc.exe и выбрав **файл**, **добавить или удалить оснастку...**  элемента меню. В **Добавление или удаление оснасток** диалогового окна выберите **оснастку сертификатов** и нажмите кнопку **добавить**. В диалоговом окне оснастки сертификатов выберите **учетная запись компьютера**. По умолчанию сертификат, сформированный из образца «Безопасность сообщений с использованием имени пользователя», будет находиться в папке «Личное или сертификаты».  Оно будет указано как «localhost» в разделе «выпущен» столбца в окне MMC. Перетаскивание сертификат в **доверенные лица** папки. Это позволит WCF считать сертификат доверенным при выполнении проверки подлинности.  
  
## <a name="to-call-the-service-passing-username-and-password"></a>Вызов службы с передачей имени пользователя и пароля  
  
1.  Клиентское приложение должно предложить пользователю ввести имя пользователя и пароль. Следующий код запрашивает у пользователя имя пользователя и пароль.  
  
    > [!WARNING]
    >  Этот код не следует использовать в рабочей среде, так как пароль во время ввода отображается на экране.  
  
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
  
2.  Создайте экземпляр клиентского класса-посредника, указав учетные данные клиента, как показано в следующем коде:  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.WSHttpBinding>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [Безопасность транспорта с обычной проверкой подлинности](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [Защита распределенных приложений](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
