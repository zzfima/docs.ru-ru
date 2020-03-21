---
title: Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: af1bb9b2ff793f6e6854c1b253dd445a35a5076f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185575"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a>Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов
В данном разделе показано, как реализовать пользовательский проверяющий элемент управления для сертификата и как настроить учетные данные клиента или службы, чтобы заменить логику проверки сертификата по умолчанию пользовательским проверяющим элементом управления для сертификата.  
  
 Если сертификат X.509 используется для проверки подлинности клиента или службы, Windows Communication Foundation (WCF) по умолчанию использует магазин сертификатов Windows и Crypto API для проверки сертификата и обеспечения его доверия. Иногда встроенных функциональных возможностей проверки сертификатов недостаточно, их необходимо изменить. WCF предоставляет простой способ изменить логику проверки, позволяя пользователям добавлять пользовательский валидатор сертификата. Если указан пользовательский валидатор сертификата, WCF не использует встроенную логику проверки сертификата, а полагается на пользовательский валидатор.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-create-a-custom-certificate-validator"></a>Создание пользовательского проверяющего элемента управления для сертификата  
  
1. Определите новый производный класс на основе класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
2. Реализуйте абстрактный метод <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>. Сертификат, который необходимо проверить, передается методу как аргумент. Если переданный сертификат недопустим согласно логике проверки, этот метод создает исключение <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>. Если сертификат действителен, метод возвращает его вызывающей стороне.  
  
    > [!NOTE]
    > Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a>Задание пользовательского проверяющего элемента управления для сертификата в конфигурации службы  
  
1. Добавьте [ \<в](../../configure-apps/file-schema/wcf/behaviors.md) [ \<элемент system.serviceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<>](../../configure-apps/file-schema/wcf/servicebehaviors.md)>>  
  
2. Добавьте [ \<поведение>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и установите `name` атрибут соответствующим значением.  
  
3. Добавьте `<behavior>` [ \<>в элемент serviceCredentials.](../../configure-apps/file-schema/wcf/servicecredentials.md)  
  
4. Добавьте элемент `<clientCertificate>` в элемент `<serviceCredentials>`.  
  
5. Добавьте [ \<>проверки подлинности](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) в `<clientCertificate>` элемент.  
  
6. Задайте для атрибута `customCertificateValidatorType` тип проверяющего элемента управления. В следующем примере для атрибута задано значение пространства имен и имени типа.  
  
7. Задайте для атрибута `certificateValidationMode` значение `Custom`.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a>Задание пользовательского проверяющего элемента управления для сертификата с использованием конфигурации на стороне клиента  
  
1. Добавьте [ \<в](../../configure-apps/file-schema/wcf/behaviors.md) [ \<элемент system.serviceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<>](../../configure-apps/file-schema/wcf/servicebehaviors.md)>>  
  
2. Добавьте [ \<элемент endpointBehaviors>.](../../configure-apps/file-schema/wcf/endpointbehaviors.md)  
  
3. Добавьте элемент `<behavior>` и присвойте атрибуту `name` соответствующее значение.  
  
4. Добавьте [ \<элемент clientCredentials>.](../../configure-apps/file-schema/wcf/clientcredentials.md)  
  
5. Добавить [ \<сервисный сертификат>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).  
  
6. Добавьте [ \<>аутентификации,](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) показанную в следующем примере.  
  
7. Задайте для атрибута `customCertificateValidatorType` тип проверяющего элемента управления.  
  
8. Задайте для атрибута `certificateValidationMode` значение `Custom`. В следующем примере для атрибута задано значение пространства имен и имени типа.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a>Задание пользовательского проверяющего элемента управления для сертификата с использованием кода на стороне службы  
  
1. Задайте пользовательский проверяющий элемент управления для сертификата в свойстве <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>. Получить доступ к учетным данным службы можно с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.  
  
2. Установите свойство <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> в значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a>Задание пользовательского проверяющего элемента управления для сертификата с использованием кода на стороне клиента  
  
1. Задайте пользовательский проверяющий элемент управления для сертификата в свойстве <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>. Получить доступ к учетным данным клиента можно с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>. (Клиентский класс, генерируемый [ServiceModel Metadata Utility Tool (Svcutil.exe),](../servicemodel-metadata-utility-tool-svcutil-exe.md) всегда происходит от <xref:System.ServiceModel.ClientBase%601> класса.)  
  
2. Установите свойство <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> в значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показана реализация пользовательского проверяющего элемента управления для сертификата и его использование на стороне службы.  
  
### <a name="code"></a>Код  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
