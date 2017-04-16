---
title: "Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, аутентификация"
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов
В данном разделе показано, как реализовать пользовательский проверяющий элемент управления для сертификата и как настроить учетные данные клиента или службы, чтобы заменить логику проверки сертификата по умолчанию пользовательским проверяющим элементом управления для сертификата.  
  
 Если для проверки подлинности клиента или службы используется сертификат X.509, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] по умолчанию использует хранилище сертификатов Windows и Crypto API, чтобы проверить сертификат и гарантировать его надежность.  Иногда встроенных функциональных возможностей проверки сертификатов недостаточно, их необходимо изменить.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет простой способ изменения логики проверки, позволяя пользователям добавлять свои элементы проверки сертификата.  Если пользовательский проверяющий элемент управления для сертификата указан, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместо встроенной логики проверки сертификатов использует пользовательский проверяющий элемент управления.  
  
## Процедуры  
  
#### Создание пользовательского проверяющего элемента управления для сертификата  
  
1.  Определите новый производный класс на основе класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
2.  Реализуйте абстрактный метод <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>.  Сертификат, который необходимо проверить, передается методу как аргумент.  Если переданный сертификат недопустим согласно логике проверки, этот метод создает исключение <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.  Если сертификат действителен, метод возвращает его вызывающей стороне.  
  
    > [!NOTE]
    >  Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### Задание пользовательского проверяющего элемента управления для сертификата в конфигурации службы  
  
1.  Добавьте элемент [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) и [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) в элемент [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md).  
  
2.  Добавьте элемент [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и задайте соответствующее значение для атрибута `name`.  
  
3.  Добавьте элемент [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) в элемент `<behavior>`.  
  
4.  Добавьте элемент `<clientCertificate>` в элемент `<serviceCredentials>`.  
  
5.  Добавьте элемент [\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) в элемент `<clientCertificate>`.  
  
6.  Задайте для атрибута `customCertificateValidatorType` тип проверяющего элемента управления.  В следующем примере для атрибута задано значение пространства имен и имени типа.  
  
7.  Задайте для атрибута `certificateValidationMode` значение `Custom`.  
  
    ```  
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
  
#### Задание пользовательского проверяющего элемента управления для сертификата с использованием конфигурации на стороне клиента  
  
1.  Добавьте элемент [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) и [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) в элемент [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md).  
  
2.  Добавьте элемент [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md).  
  
3.  Добавьте элемент `<behavior>` и присвойте атрибуту `name` соответствующее значение.  
  
4.  Добавьте элемент [\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
5.  Добавьте элемент [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).  
  
6.  Добавьте элемент [\<аутентификация\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md), как показано в следующем примере.  
  
7.  Задайте для атрибута `customCertificateValidatorType` тип проверяющего элемента управления.  
  
8.  Задайте для атрибута `certificateValidationMode` значение `Custom`.  В следующем примере для атрибута задано значение пространства имен и имени типа.  
  
    ```  
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
  
#### Задание пользовательского проверяющего элемента управления для сертификата с использованием кода на стороне службы  
  
1.  Задайте пользовательский проверяющий элемент управления для сертификата в свойстве <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>.  Получить доступ к учетным данным службы можно с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.  
  
2.  Задайте для свойства <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> значение <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### Задание пользовательского проверяющего элемента управления для сертификата с использованием кода на стороне клиента  
  
1.  Задайте пользовательский проверяющий элемент управления для сертификата в свойстве <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.  Получить доступ к учетным данным клиента можно с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.  \(Класс клиента, созданный с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), всегда наследуется от класса <xref:System.ServiceModel.ClientBase%601>.\)  
  
2.  Задайте для свойства <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> значение <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  
  
## Пример  
  
### Описание  
 В следующем примере показана реализация пользовательского проверяющего элемента управления для сертификата и его использование на стороне службы.  
  
### Код  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## См. также  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>