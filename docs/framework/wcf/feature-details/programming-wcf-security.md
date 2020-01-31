---
title: Программирование безопасности WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
ms.openlocfilehash: e19f858818866f16b8af44abe462ddb826d43b69
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741478"
---
# <a name="programming-wcf-security"></a>Программирование безопасности WCF
В этом разделе описываются фундаментальные задачи программирования, используемые для создания безопасного Windows Communication Foundation (WCF) приложения. В этом разделе рассматриваются только проверка подлинности, конфиденциальность и целостность, называемая *безопасностью перемещения*. В этом разделе не рассматривается авторизация (Управление доступом к ресурсам или службам). сведения об авторизации см. в разделе [авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
> [!NOTE]
> Чтобы получить ценные сведения о концепциях безопасности, особенно в отношении WCF, ознакомьтесь с набором руководств по работе с шаблонами и практическими рекомендациями на MSDN в [сценариях, шаблонах и руководствах по реализации усовершенствований веб-служб (WSE) 3,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648183(v=pandp.10)).  
  
 Программирование безопасности WCF основывается на трех шагах: режим безопасности, тип учетных данных клиента и значения учетных данных. Эти действия можно выполнить с помощью кода или конфигурации.  
  
## <a name="setting-the-security-mode"></a>Задание режима безопасности  
 Ниже описаны общие шаги для программирования с использованием режима безопасности в WCF.  
  
1. Выберите одну из предопределенных привязок, отвечающих требованиям приложения. Список вариантов привязки см. в разделе привязки, [предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md). По умолчанию практически во всех привязках включены функции безопасности. Единственным исключением является класс <xref:System.ServiceModel.BasicHttpBinding> (с использованием конфигурации, [\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)).  
  
     Выбранная привязка определяет транспорт. Например, привязка <xref:System.ServiceModel.WSHttpBinding> использует протокол HTTP в качестве транспорта; привязка <xref:System.ServiceModel.NetTcpBinding> использует протокол TCP.  
  
2. Выберите один из режимов безопасности привязки. Обратите внимание, что выбранная привязка определяет выбор доступных режимов. Например, привязка <xref:System.ServiceModel.WSDualHttpBinding> не позволяет обеспечить безопасность транспорта (это изменить нельзя). Аналогично, привязки <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> и <xref:System.ServiceModel.NetNamedPipeBinding> не обеспечивают безопасность сообщений.  
  
     Доступны три варианта.  
  
    1. `Transport`  
  
         Безопасность транспорта зависит от механизма, используемого в выбранной привязке. Например, при использовании привязки `WSHttpBinding` в качестве механизма безопасности выступает протокол SSL (который также служит механизмом для протокола HTTPS). Основное преимущество безопасности транспорта заключается в обеспечении большой пропускной способности независимо от используемого типа транспорта. Однако имеются два ограничения. Первое ограничение - транспортный механизм определяет тип учетных данных, используемых для проверки подлинности пользователя. Этот недостаток проявляется, только если служба взаимодействует с другими службами, которым требуются другие типы учетных данных. Второе ограничение заключается в том, что безопасность применяется не на уровне сообщений, поэтому безопасность реализуется последовательным, а не сквозным способом. Это ограничение представляет проблему только в том случае, если на пути сообщения между клиентом и службой имеются посредники. Дополнительные сведения о том, какой транспорт использовать, см. в разделе [Выбор транспорта](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Дополнительные сведения об использовании безопасности транспорта см. в статье [Общие сведения о безопасности транспорта](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).  
  
    2. `Message`  
  
         Под безопасностью сообщений понимается наличие в каждом сообщении необходимых заголовок и данных для обеспечения безопасности сообщения. Поскольку состав заголовков не является фиксированным, можно включать любое количество учетных данных. Это становится важным в случае взаимодействия с другими службами, которым требуются учетные данные определенного типа, которые невозможно предоставить с помощью транспортного механизма, или если сообщение необходимо использовать для нескольких служб, которым требуются различные учетные данные.  
  
         Дополнительные сведения см. в разделе [безопасность сообщений](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
    3. `TransportWithMessageCredential`  
  
         В этом случае транспортный уровень используется для защиты передачи сообщений. При этом каждое сообщение включает расширенные учетные данные, необходимые другим службам. Этот способ сочетает повышение производительности механизма безопасности транспорта с наличием различных учетных данных механизма безопасности сообщений. Его можно использовать со следующими привязками: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> и <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Если принято решение использовать безопасность транспорта для протокола HTTP (т.е. протокол HTTPS), необходимо настроить узел с сертификатом SSL и включить SSL для порта. Дополнительные сведения см. в разделе [Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
4. Если используется привязка <xref:System.ServiceModel.WSHttpBinding> и при этом не требуется устанавливать безопасный сеанс, следует присвоить свойству <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> значение `false`.  
  
     Безопасный сеанс создается, когда клиент и служба создают канал с использованием симметричного ключа (клиент и служба используют один и тот же ключ в течение всего диалога вплоть до его завершения).  
  
## <a name="setting-the-client-credential-type"></a>Задание типа учетных данных клиента  
 Выберите необходимый тип учетных данных клиента. Дополнительные сведения см. [в разделе Выбор типа учетных данных](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md). Доступны следующие типы учетных данных клиента:  
  
- `Windows`  
  
- `Certificate`  
  
- `Digest`  
  
- `Basic`  
  
- `UserName`  
  
- `NTLM`  
  
- `IssuedToken`  
  
 Тип учетных данных задается с учетом выбранного режима. Например, если выбрана привязка `wsHttpBinding` и задан режим Message, необходимо также присвоить атрибуту `clientCredentialType` элемента Message одно из следующих значений: `None`, `Windows`, `UserName`, `Certificate` или `IssuedToken`, как показано в следующем примере конфигурации.  
  
```xml  
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
  
## <a name="setting-service-credential-values"></a>Задание значений учетных данных службы  
 После выбора типа учетных данных необходимо задать фактические значения учетных данных, которые будут использоваться службой и клиентом. Задание учетных данных для службы осуществляется с помощью класса <xref:System.ServiceModel.Description.ServiceCredentials>. Свойство <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> класса <xref:System.ServiceModel.ServiceHostBase> возвращает эти учетные данные. Используемая привязка заключает в себе тип учетных данных службы, выбранный режим безопасности и тип учетных данных клиента. В следующем примере задается сертификат для учетных данных службы.  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a>Задание значений учетных данных клиента  
 Задание учетных данных для клиента осуществляется с помощью класса <xref:System.ServiceModel.Description.ClientCredentials>. Свойство <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601> возвращает эти учетные данные. В следующем примере задается сертификат для учетных данных клиента с использованием протокола TCP.  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также:

- [Базовое программирование для WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [Типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
