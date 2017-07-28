---
title: "Программирование безопасности WCF | Microsoft Docs"
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
  - "безопасность сообщений [WCF], общие сведения о программировании"
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
caps.latest.revision: 25
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 25
---
# Программирование безопасности WCF
В данном разделе приводится описание основных задач программирования, используемых для создания безопасного приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Здесь рассматриваются только вопросы проверки подлинности, конфиденциальности и целостности, которые в совокупности называются *безопасностью передачи*.Не рассматривается авторизация \(управление доступом к ресурсам или службам\). Сведения об авторизации см. в разделе [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
> [!NOTE]
>  Полезные общие сведения о концепциях безопасности, главным образом касающиеся [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], см. в наборе образцов, практических рекомендаций и руководств в разделе [Scenarios, Patterns, and Implementation Guidance for Web Services Enhancements \(WSE\) 3.0](http://go.microsoft.com/fwlink/?LinkID=88250) на сайте MSDN.  
  
 Программирование безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] заключается в задании следующих трех элементов: режим безопасности, тип учетных данных клиента и значения учетных данных.Эти действия можно выполнить с помощью кода или конфигурации.  
  
## Задание режима безопасности  
 Ниже рассматриваются общие действия по программированию режима безопасности в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
1.  Выберите одну из предопределенных привязок, отвечающих требованиям приложения.Список привязок см. в разделе [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md).По умолчанию практически во всех привязках включены функции безопасности.Единственное исключение — класс <xref:System.ServiceModel.BasicHttpBinding> \(используется конфигурация, [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)\).  
  
     Выбранная привязка определяет транспорт.Например, привязка <xref:System.ServiceModel.WSHttpBinding> использует протокол HTTP в качестве транспорта; привязка <xref:System.ServiceModel.NetTcpBinding> использует протокол TCP.  
  
2.  Выберите один из режимов безопасности привязки.Обратите внимание, что выбранная привязка определяет выбор доступных режимов.Например, привязка <xref:System.ServiceModel.WSDualHttpBinding> не позволяет обеспечить безопасность транспорта \(это изменить нельзя\).Аналогично, привязки <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> и <xref:System.ServiceModel.NetNamedPipeBinding> не обеспечивают безопасность сообщений.  
  
     Доступны три варианта.  
  
    1.  `Transport`  
  
         Безопасность транспорта зависит от механизма, используемого в выбранной привязке.Например, при использовании привязки `WSHttpBinding` в качестве механизма безопасности выступает протокол SSL \(который также служит механизмом для протокола HTTPS\).Основное преимущество безопасности транспорта заключается в обеспечении большой пропускной способности независимо от используемого типа транспорта.Однако имеются два ограничения. Первое ограничение — транспортный механизм определяет тип учетных данных, используемых для проверки подлинности пользователя.Этот недостаток проявляется, только если служба взаимодействует с другими службами, которым требуются другие типы учетных данных.Второе ограничение заключается в том, что безопасность применяется не на уровне сообщений, поэтому безопасность реализуется последовательным, а не сквозным способом.Это ограничение представляет проблему только в том случае, если на пути сообщения между клиентом и службой имеются посредники.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о том, какой транспорт необходимо использовать, см. в разделе [Выбор транспортов](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об использовании безопасности транспорта см. в разделе [Общие сведения о безопасности транспорта](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).  
  
    2.  `Message`  
  
         Под безопасностью сообщений понимается наличие в каждом сообщении необходимых заголовок и данных для обеспечения безопасности сообщения.Поскольку состав заголовков не является фиксированным, можно включать любое количество учетных данных.Это становится важным в случае взаимодействия с другими службами, которым требуются учетные данные определенного типа, которые невозможно предоставить с помощью транспортного механизма, или если сообщение необходимо использовать для нескольких служб, которым требуются различные учетные данные.  
  
         [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Безопасность обмена сообщениями](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
    3.  `TransportWithMessageCredential`  
  
         В этом случае транспортный уровень используется для защиты передачи сообщений. При этом каждое сообщение включает расширенные учетные данные, необходимые другим службам.Этот способ сочетает повышение производительности механизма безопасности транспорта с наличием различных учетных данных механизма безопасности сообщений.Его можно использовать со следующими привязками: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> и <xref:System.ServiceModel.WSHttpBinding>.  
  
3.  Если принято решение использовать безопасность транспорта для протокола HTTP \(т.е. протокол HTTPS\), необходимо настроить узел с сертификатом SSL и включить SSL для порта.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
4.  Если используется привязка <xref:System.ServiceModel.WSHttpBinding> и при этом не требуется устанавливать безопасный сеанс, следует присвоить свойству <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> значение `false`.  
  
     Безопасный сеанс создается, когда клиент и служба создают канал с использованием симметричного ключа \(клиент и служба используют один и тот же ключ в течение всего диалога вплоть до его завершения\).  
  
## Задание типа учетных данных клиента  
 Выберите необходимый тип учетных данных клиента.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Выбор типа учетных данных](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).Доступны следующие типы учетных данных клиента:  
  
-   `Windows`  
  
-   `Certificate`  
  
-   `Digest`  
  
-   `Basic`  
  
-   `UserName`  
  
-   `NTLM`  
  
-   `IssuedToken`  
  
 Тип учетных данных задается с учетом выбранного режима.Например, если выбрана привязка `wsHttpBinding` и задан режим Message, необходимо также присвоить атрибуту `clientCredentialType` элемента Message одно из следующих значений: `None`, `Windows`, `UserName`, `Certificate` или `IssuedToken`, как показано в следующем примере конфигурации.  
  
```  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>  
</bindings>  
</system.serviceModel>  
```  
  
 Или в коде:  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## Задание значений учетных данных службы  
 После выбора типа учетных данных необходимо задать фактические значения учетных данных, которые будут использоваться службой и клиентом.Задание учетных данных для службы осуществляется с помощью класса <xref:System.ServiceModel.Description.ServiceCredentials>. Свойство <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> класса <xref:System.ServiceModel.ServiceHostBase> возвращает эти учетные данные.Используемая привязка заключает в себе тип учетных данных службы, выбранный режим безопасности и тип учетных данных клиента.В следующем примере задается сертификат для учетных данных службы.  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## Задание значений учетных данных клиента  
 Задание учетных данных для клиента осуществляется с помощью класса <xref:System.ServiceModel.Description.ClientCredentials>. Свойство <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601> возвращает эти учетные данные.В следующем примере задается сертификат для учетных данных клиента с использованием протокола TCP.  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## См. также  
 [Базовое программирование WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)   
 [Типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)