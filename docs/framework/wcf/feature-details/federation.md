---
title: Федерация
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation [WCF]
ms.assetid: 2f1e646f-8361-48d4-9d5d-1b961f31ede4
ms.openlocfilehash: baf65340e390c7439e8639e334819fb0bf60f952
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662625"
---
# <a name="federation"></a>Федерация
В этом разделе приведен краткий обзор концепции федеративной безопасности. Здесь также описываются поддержка развертывания архитектур федеративной безопасности Windows Communication Foundation (WCF). Образец приложения, демонстрирующий федерацию, см. в разделе [пример федерации](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
## <a name="definition-of-federated-security"></a>Определение федеративной безопасности  
 Федеративная безопасность обеспечивает четкое разделение между службой, к которой обращается клиент, и связанными процедурами проверки подлинности и авторизации. Федеративная безопасность также делает возможной совместную работу групп из нескольких систем, сетей и организаций, принадлежащих к различным областям доверия.  
  
 WCF обеспечивает поддержку для создания и развертывания распределенных систем, применяющих федеративной безопасности.  
  
### <a name="elements-of-a-federated-security-architecture"></a>Элементы архитектуры федеративной безопасности  
 Архитектура федеративной безопасности включает три основных элемента, рассмотренных в следующей таблице.  
  
|Элемент|Описание|  
|-------------|-----------------|  
|Домен/область|Единица администрирования безопасности или доверия. Типичный домен может включать одну организацию.|  
|Федерация|Совокупность доменов, между которыми установлено отношение доверия. Уровень доверия может быть разным, но обычно предусматривает проверку подлинности и почти всегда предусматривает авторизацию. Типичная федерация может включать ряд организаций, между которыми установлено отношение доверия для общего доступа к некоторому набору ресурсов.|  
|Служба маркеров безопасности (STS)|Веб-служба, выдающая маркеры безопасности, т. е. делающая утверждения на основании свидетельств, которым она доверяет, перед теми, кто доверяет ей. Эти утверждения образуют основу посредничества с доверием между доменами.|  
  
### <a name="example-scenario"></a>Пример сценария  
 Ниже показан пример федеративной безопасности:  
  
 ![Схема, показывающая сценарий типичный федеративной безопасности.](./media/federation/typical-federated-security-scenario.gif)  
  
 Этот сценарий включает две организации: A и B. Организация B имеет веб-ресурс (веб-службы), некоторые пользователи в организации A находят полезной.  
  
> [!NOTE]
>  В этом разделе используются термины *ресурсов*, *службы*, и *веб-службы* являются взаимозаменяемыми.  
  
 Как правило, организация B требует, чтобы пользователь из организации A предоставил какое-либо допустимое доказательство своей подлинности, прежде чем обращаться к службе. Кроме того, организация может также потребовать, чтобы пользователь был авторизован для доступа к данному ресурсу. Один из способов решить эту проблему и дать пользователям в организации A возможность доступа к ресурсу в организации B заключается в следующем.  
  
- Пользователи из организации A регистрируют свои учетные данные (имя пользователя и пароль) в организации B.  
  
- При обращении к ресурсу пользователи из организации A предъявляют свои учетные данные организации B, т. е. подлинность пользователей проверяется, прежде чем они получают доступ к ресурсу.  
  
 Это подход имеет три существенных недостатка.  
  
- Организации B приходится управлять учетными данными пользователей из организации A, помимо управления учетными данными своих локальных пользователей.  
  
- Пользователям в организации A приходится иметь дополнительный набор учетных данных (т. е. помнить дополнительные имя пользователя и пароль) помимо учетных данных, которыми они пользуются для получения доступа к ресурсам в пределах организации A. В таких случаях пользователи часто используют одни и те же имя пользователя и пароль для доступа к нескольким сайтам служб, что ослабляет защиту.  
  
- Архитектура не масштабируется, если другие организации посчитают ресурс в организации B полезным для своих пользователей.  
  
 Альтернативный подход, лишенный упомянутых выше недостатков - это использование федеративной безопасности. В соответствии с этим подходом организации A и B устанавливают отношения доверия и используют службу маркеров безопасности (Security Token Service, STS) как посредника для установленного доверия.  
  
 В архитектуре федеративной безопасности пользователи из организации A знают, что если им требуется обратиться к веб-службе в организации B, они должны предъявить в организации B допустимый маркер безопасности от службы STS, который используется для проверки их подлинности и авторизации их доступа к определенной службе.  
  
 При обращении к службе STS B пользователи приобретают еще один уровень косвенного обращения от политики, связанной со службой STS. Прежде чем служба STS B сможет выдать им маркер безопасности, они должны предъявить допустимый маркер безопасности от службы STS A (т. е. из области доверия клиента). Это логическое следствие из отношения доверия, установленного между двумя организациями, подразумевающее, что организации B не требуется управлять удостоверениями пользователей из организации A. На практике служба STS B обычно имеет пустые адреса `issuerAddress` и `issuerMetadataAddress`. Дополнительные сведения см. в разделе [Как Настройка локального издателя](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md). В этом случае клиент обращается к локальной политике, чтобы найти службу STS A. Такая конфигурация называется *домашней области федерации* и является более масштабируемой, поскольку службе STS B не имеет к сбору сведений о службе STS A.  
  
 Затем пользователи связываются со службой STS в организации A и получают маркер безопасности, предъявляя для проверки подлинности учетные данные, которыми они обычно пользуются для доступа к любому другому ресурсу в пределах организации A. Это также решает проблему пользователей, которым приходится либо помнить несколько наборов учетных данных, либо использовать один и тот же набор учетных данных на нескольких сайтах служб.  
  
 Получив маркер безопасности от службы STS A, пользователи предъявляют маркер службе STS B. Далее организация B авторизует запросы пользователей и выдает пользователям маркер безопасности из собственного набора маркеров безопасности. Пользователи затем могут предъявить свой маркер ресурсу в организации B и получить доступ к службе.  
  
## <a name="support-for-federated-security-in-wcf"></a>Поддержка федеративной безопасности в WCF  
 WCF предусмотрена готовая поддержка развертывания архитектуры федеративной безопасности с помощью [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
 [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) обеспечивает безопасную, надежную, с возможностью взаимодействия привязку, предполагающую использование HTTP как базовый механизм транспортировки для связи типа запрос ответ в стиле использования в качестве формата подключения для кодирования текста и XML.  
  
 Использование [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) в таком сценарии можно разделить на две логически независимых фазы, как описано в следующих разделах.  
  
### <a name="phase-1-design-phase"></a>Этап 1. Этап разработки  
 На этапе проектирования, клиент использует [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) ознакомиться с политикой, предоставляет конечную точку службы и сбора требований проверки подлинности и авторизации службы. Строятся соответствующие прокси-объекты для создания следующей схемы обмена данными федеративной безопасности на стороне клиента:  
  
- получение маркера безопасности от службы STS в области доверия клиента;  
  
- предъявление маркера службе STS в области доверия службы;  
  
- получение маркера безопасности от службы STS в области доверия службы;  
  
- предъявление маркера службе для доступа к службе.  
  
### <a name="phase-2-run-time-phase"></a>Этап 2. Фаза времени выполнения  
 На этапе выполнения клиент создает экземпляр объекта класса клиента WCF и делает вызов с помощью клиента WCF. Базовую платформу WCF обрабатывает упомянутые выше шаги в шаблоне обмена данными федеративной безопасности и позволяет клиенту легко воспользоваться службой.  
  
## <a name="sample-implementation-using-wcf"></a>Пример реализации с использованием WCF  
 Ниже показан пример реализации архитектуры федеративной безопасности с помощью встроенной поддержки WCF.  
  
 ![Схема, показывающая пример реализации безопасности федерации.](./media/federation/federated-security-implementation.gif)  
  
### <a name="example-myservice"></a>Служба MyService  
 Служба `MyService` предоставляет одну конечную точку - `MyServiceEndpoint`. На следующем рисунке показаны адрес, привязка и контракт, связанные с конечной точкой.  
  
 ![Схема, показывающая MyServiceEndpoint сведения.](./media/federation/myserviceendpoint-details.gif)  
  
 Конечная точка службы `MyServiceEndpoint` использует [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) и требует допустимый маркер Security Assertions Markup Language (SAML) с `accessAuthorized` утверждения, выданного службой STS б. Это декларативно указано в конфигурации службы.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.MyService"      
        behaviorConfiguration='MyServiceBehavior'>  
        <endpoint address=""  
            binding=" wsFederationHttpBinding"  
            bindingConfiguration='MyServiceBinding'  
            contract="Federation.IMyService" />  
   </service>  
  </services>  
  
  <bindings>  
    <wsFederationHttpBinding>  
    <!-- This is the binding used by MyService. It redirects   
    clients to STS-B. -->  
      <binding name='MyServiceBinding'>  
        <security mode="Message">  
           <message issuedTokenType=  
"http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
           <issuer address="http://localhost/FederationSample/STS-B/STS.svc" />  
            <issuerMetadata   
           address=  
"http://localhost/FederationSample/STS-B/STS.svc/mex" />  
         <requiredClaimTypes>  
            <add claimType="http://tempuri.org:accessAuthorized" />  
         </requiredClaimTypes>  
        </message>  
      </security>  
      </binding>  
    </wsFederationHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <behavior name='MyServiceBehavior'>  
      <serviceAuthorization   
operationRequirementType="FederationSample.MyServiceOperationRequirement, MyService" />  
       <serviceCredentials>  
         <serviceCertificate findValue="CN=FederationSample.com"  
         x509FindType="FindBySubjectDistinguishedName"  
         storeLocation='LocalMachine'  
         storeName='My' />  
      </serviceCredentials>  
    </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
> [!NOTE]
>  Относительно утверждений, которые требует служба `MyService`, необходимо отметить один небольшой момент. Из второго рисунка видно, что служба `MyService` требует маркер SAML с утверждением `accessAuthorized`. Точнее, эта строка задает тип утверждения, которого требует служба `MyService`. — Полное доменное имя этого типа утверждения `http://tempuri.org:accessAuthorized` (вместе со связанным пространством имен), которая будет использоваться в файле конфигурации службы. Значение этого утверждения указывает на присутствие этого утверждения, и предполагается, что служба STS B установила его равным `true`.  
  
 Во время выполнения эта политика применяется классом `MyServiceOperationRequirement`, реализованным в составе службы `MyService`.  
  
 [!code-csharp[C_Federation#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#0)]
 [!code-vb[C_Federation#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#0)]  
[!code-csharp[C_Federation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#1)]
[!code-vb[C_Federation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#1)]  
  
#### <a name="sts-b"></a>Служба STS B  
 На следующем рисунке показана служба STS B. Как говорилось выше, служба маркеров безопасности (STS) также представляет собой веб-службу и может иметь свои конечные точки, политику и т. д.  
  
 ![Схема, показывающая службы маркеров безопасности б.](./media/federation/myservice-security-token-service-b.gif)  
  
 Служба STS B предоставляет одну конечную точку, `STSEndpoint`, которую можно использовать для запроса маркеров безопасности. В частности, служба STS B выдает маркеры SAML с утверждением `accessAuthorized`, которые могут быть предъявлены на сайте службы `MyService` для доступа к службе. В то же время служба STS B требует от пользователей предъявления допустимого маркера SAML, выданного службой STS A и содержащего утверждение `userAuthenticated`. Это декларативно указано в конфигурации службы STS.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.STS_B" behaviorConfiguration=  
     "STS-B_Behavior">  
    <endpoint address=""  
              binding="wsFederationHttpBinding"  
              bindingConfiguration='STS-B_Binding'  
      contract="FederationSample.ISts" />  
    </service>  
  </services>  
  <bindings>  
    <wsFederationHttpBinding>  
    <!-- This is the binding used by STS-B. It redirects clients to   
         STS-A. -->  
      <binding name='STS-B_Binding'>  
        <security mode='Message'>  
          <message issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
          <issuer address='http://localhost/FederationSample/STS-A/STS.svc' />  
          <issuerMetadata address='http://localhost/FederationSample/STS-A/STS.svc/mex'/>  
          <requiredClaimTypes>  
            <add claimType='http://tempuri.org:userAuthenticated'/>  
          </requiredClaimTypes>  
          </message>  
        </security>  
    </binding>  
   </wsFederationHttpBinding>  
  </bindings>  
  <behaviors>  
  <behavior name='STS-B_Behavior'>  
    <serviceAuthorization   operationRequirementType='FederationSample.STS_B_OperationRequirement, STS_B' />  
    <serviceCredentials>  
      <serviceCertificate findValue='CN=FederationSample.com'  
      x509FindType='FindBySubjectDistinguishedName'  
       storeLocation='LocalMachine'  
       storeName='My' />  
     </serviceCredentials>  
   </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
> [!NOTE]
>  Опять же `userAuthenticated` утверждения является тип утверждения, которые требуются для службы STS б. — Полное доменное имя этого типа утверждения `http://tempuri.org:userAuthenticated` (вместе со связанным пространством имен), которая будет использоваться в файле конфигурации службы STS. Значение этого утверждения указывает на присутствие этого утверждения, и предполагается, что служба STS A установила его равным `true`.  
  
 Во время выполнения эта политика применяется классом `STS_B_OperationRequirement`, реализованным в составе службы STS B.  
  
 [!code-csharp[C_Federation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#2)]
 [!code-vb[C_Federation#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#2)]  
  
 Если проверка доступа пройдена, служба STS B выдает маркер SAML с утверждением `accessAuthorized`.  
  
 [!code-csharp[C_Federation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#3)]
 [!code-vb[C_Federation#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#3)]  
  
#### <a name="sts-a"></a>Служба STS A  
 На следующем рисунке показана служба STS A.  
  
 ![Федерации](../../../../docs/framework/wcf/feature-details/media/sts-b.gif "STS_B")  
  
 Как и STS B, служба STS A также представляет собой веб-службу, выдающую маркеры безопасности и предоставляющую с этой целью одну конечную точку. Однако она использует другую привязку (`wsHttpBinding`) и требует от пользователей предъявления допустимого маркера [!INCLUDE[infocard](../../../../includes/infocard-md.md)] с утверждением `emailAddress`. В ответ она выдает маркеры SAML с утверждением `userAuthenticated`. Это декларативно указано в конфигурации службы.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.STS_A" behaviorConfiguration="STS-A_Behavior">  
      <endpoint address=""  
                binding="wsHttpBinding"  
                bindingConfiguration="STS-A_Binding"  
                contract="FederationSample.ISts">  
       <identity>  
       <certificateReference findValue="CN=FederationSample.com"    
                       x509FindType="FindBySubjectDistinguishedName"  
                       storeLocation="LocalMachine"   
                       storeName="My" />  
       </identity>  
    <endpoint>  
  </service>  
</services>  
  
<bindings>  
  <wsHttpBinding>  
  <!-- This is the binding used by STS-A. It requires users to present  
   a CardSpace. -->  
    <binding name='STS-A_Binding'>  
      <security mode='Message'>  
        <message clientCredentialType="CardSpace" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
  
<behaviors>  
  <behavior name='STS-A_Behavior'>  
    <serviceAuthorization operationRequirementType=  
     "FederationSample.STS_A_OperationRequirement, STS_A" />  
      <serviceCredentials>  
  <serviceCertificate findValue="CN=FederationSample.com"  
                     x509FindType='FindBySubjectDistinguishedName'  
                     storeLocation='LocalMachine'  
                     storeName='My' />  
      </serviceCredentials>  
    </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
 Во время выполнения эта политика применяется классом `STS_A_OperationRequirement`, реализованным в составе службы STS A.  
  
 [!code-csharp[C_Federation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#4)]
 [!code-vb[C_Federation#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#4)]  
  
 Если проверка доступа возвратила значение `true`, служба STS A выдает маркер SAML с утверждением `userAuthenticated`.  
  
 [!code-csharp[C_Federation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#5)]
 [!code-vb[C_Federation#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#5)]  
  
### <a name="client-at-organization-a"></a>Клиент в организации A  
 На следующем рисунке показан клиент в организации A и шаги, которые включает в себя вызов функции `MyService`. Для полноты картины включены также другие функциональные компоненты.  
  
 ![Схема showwing действия, описанные в вызов службы MyService.](./media/federation/federation-myservice-service-call-process.gif)  
  
## <a name="summary"></a>Сводка  
 Федеративная безопасность обеспечивает четкое разделение ответственности и позволяет выстраивать безопасные, масштабируемые архитектуры служб. Платформа для построения и развертывания распределенных приложений WCF обеспечивает встроенную поддержку для реализации федеративной безопасности.  
  
## <a name="see-also"></a>См. также

- [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)
