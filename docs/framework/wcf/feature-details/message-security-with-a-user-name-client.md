---
title: "Безопасность сообщений при использовании клиентом учетных данных пользователя | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# Безопасность сообщений при использовании клиентом учетных данных пользователя
На следующем рисунке показано, как защищаются служба и клиент [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с помощью безопасности на уровне сообщений.Служба проходит проверку подлинности с использованием сертификата X.509.Подлинность клиента проверяется с помощью имени и пароля пользователя.  
  
 Пример приложения см. в разделе [Безопасность сообщений с использованием имени пользователя](../../../../docs/framework/wcf/samples/message-security-user-name.md).  
  
 ![Безопасность сообщений с использованием аутентификации имени пользователя](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61\-7e1d\-42f5\-b1af\-195bfee5b3c6")  
  
|Характеристика|Описание|  
|--------------------|--------------|  
|Режим безопасности|Сообщение|  
|Взаимодействие|Только [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]|  
|Проверка подлинности \(сервера\)|Первоначальное согласование возможно только после проверки подлинности сервера|  
|Проверка подлинности \(клиента\)|Имя пользователя\/пароль|  
|Целостность|Да, используется общий контекст безопасности|  
|Конфиденциальность|Да, используется общий контекст безопасности|  
|Транспорт|HTTP|  
|Привязка|<xref:System.ServiceModel.WSHttpBinding>|  
  
## Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо.Выполните одно из следующих действий.  
  
-   Создайте автономную службу, используя код без конфигурации.  
  
-   Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### Код  
 В следующем коде показано, как создать конечную точку службы, которая использует безопасность сообщений.  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### Конфигурация  
 Вместо кода можно использовать следующую конфигурацию:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## Клиент  
  
### Код  
 Следующий код служит для создания клиента.Привязка осуществляется к безопасности режима сообщений, и типу учетных данных клиента присваивается значение `UserName`.Указать имя пользователя и пароль можно только с помощью кода \(они не подлежат настройке\).Здесь не показан код, который возвращает имя пользователя и пароль, потому что это происходит на уровне приложения.Например, диалоговое окно Window Forms используется для запроса данных у пользователя.  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### Конфигурация  
 Следующий код служит для настройки клиента.Привязка осуществляется к безопасности режима сообщений, и типу учетных данных клиента присваивается значение `UserName`.Указать имя пользователя и пароль можно только с помощью кода \(они не подлежат настройке\).  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## См. также  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Безопасность сообщений с использованием имени пользователя](../../../../docs/framework/wcf/samples/message-security-user-name.md)   
 [Идентификация и проверка подлинности службы](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<удостоверение\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)   
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x419)