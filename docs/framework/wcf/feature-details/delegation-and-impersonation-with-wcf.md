---
title: Делегирование и олицетворение с использованием WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- impersonation [WCF]
- delegation [WCF]
ms.assetid: 110e60f7-5b03-4b69-b667-31721b8e3152
ms.openlocfilehash: 578957888daf7be20ab7418a46c533a011b3d2ac
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964165"
---
# <a name="delegation-and-impersonation-with-wcf"></a>Делегирование и олицетворение с использованием WCF
*Олицетворение* - это стандартная техника, которую службы используют для ограничения клиентского доступа к ресурсам домена службы. В роли ресурсов домена службы могут выступать ресурсы компьютера, например локальные файлы (олицетворение), или ресурсы, расположенные на другом компьютере, например общая папка (делегирование). Пример приложения см. в разделе [Impersonating the Client](../../../../docs/framework/wcf/samples/impersonating-the-client.md). Пример использования олицетворения см. в разделе [How to: Impersonate a Client on a Service](../../../../docs/framework/wcf/how-to-impersonate-a-client-on-a-service.md).  
  
> [!IMPORTANT]
> Следует иметь в виду, что при олицетворении клиента в службе служба выполняется с учетными данными клиента, которые могут иметь более высокий уровень разрешений, чем серверный процесс.  
  
## <a name="overview"></a>Обзор  
 Обычно клиенты вызывают службы, чтобы платформа службы выполнила какие-либо действия от имени клиента. Олицетворение позволяет службе выступать в качестве клиента при выполнении такого действия. Делегирование позволяет внешней службе перенаправить запрос клиента внутренней службе таким образом, чтобы внутренняя служба также могла олицетворять клиент. Олицетворение чаще всего используется, чтобы проверить, имеет ли клиент разрешение на выполнение определенного действия, а делегирование позволяет передать возможности олицетворения, в том числе удостоверение клиента, внутренней службе. Делегирование - это функция домена Windows, которую можно использовать при проверке подлинности Kerberos. Делегирование отличается от потока работы с удостоверениями, а поскольку делегирование позволяет олицетворять клиент даже при отсутствии пароля клиента, эта операция обладает гораздо более широкими правами.  
  
 Для олицетворения и делегирования у клиента должно быть удостоверение Windows. Если у клиента нет удостоверения Windows, единственным решением является передача удостоверения клиента второй службе.  
  
## <a name="impersonation-basics"></a>Основные принципы олицетворения  
 Windows Communication Foundation (WCF) поддерживает олицетворение для различных клиентских учетных данных. В этом разделе описана поддержка модели служб для олицетворения вызывающего объекта во время реализации метода службы. Также рассматриваются распространенные сценарии развертывания, включающие олицетворение и параметры безопасности SOAP и WCF в этих сценариях.  
  
 В этом разделе основное внимание уделяется олицетворению и делегированию в WCF при использовании безопасности SOAP. Вы также можете использовать олицетворение и делегирование в WCF при использовании безопасности транспорта, как описано в разделе [использование олицетворения с защитой транспорта](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md).  
  
## <a name="two-methods"></a>Два метода  
 Безопасность WCF SOAP имеет два различных метода для выполнения олицетворения. Выбор используемого метода зависит от привязки. Первый - олицетворение на основании маркера Windows, получаемого из интерфейса поставщика поддержки безопасности (SSPI) или при проверке подлинности Kerberos, который затем кэшируется службой. Второй метод - олицетворение на основании маркера Windows, получаемого из расширений Kerberos, имеющих общее имя *Service-for-User* (S4U).  
  
### <a name="cached-token-impersonation"></a>Олицетворение с использованием кэшированного маркера  
 Для олицетворения с использованием кэшированного маркера используются следующие элементы:  
  
- привязки<xref:System.ServiceModel.WSHttpBinding>, <xref:System.ServiceModel.WSDualHttpBinding>и <xref:System.ServiceModel.NetTcpBinding> , а также учетные данные клиента Windows;  
  
- привязка<xref:System.ServiceModel.BasicHttpBinding> , у которой <xref:System.ServiceModel.BasicHttpSecurityMode> имеет значение <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> , или любая другая стандартная привязка, с помощью которой клиент представляет имя пользователя, которое служба может сопоставить с действительной учетной записью Windows;  
  
- любая привязка <xref:System.ServiceModel.Channels.CustomBinding> , использующая учетные данные клиента Windows, где свойство `requireCancellation` имеет значение `true`. (Свойство доступно в следующих классах: <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>, <xref:System.ServiceModel.Security.Tokens.SslSecurityTokenParameters>и <xref:System.ServiceModel.Security.Tokens.SspiSecurityTokenParameters>.) Если для привязки используется безопасный диалог, для свойства `requireCancellation` также должно быть задано значение `true`.  
  
- любая привязка <xref:System.ServiceModel.Channels.CustomBinding> , в которой клиент представляет имя пользователя. При использовании в привязке безопасного обмена данными свойство `requireCancellation` также должно иметь значение `true`.  
  
### <a name="s4u-based-impersonation"></a>Олицетворение на базе S4U  
 Для олицетворения на базе S4U используются следующие элементы:  
  
- привязка<xref:System.ServiceModel.WSHttpBinding>, <xref:System.ServiceModel.WSDualHttpBinding>или <xref:System.ServiceModel.NetTcpBinding> с учетными данными сертификата клиента, которые служба может сопоставить с действительной учетной записью Windows;.  
  
- любая привязка <xref:System.ServiceModel.Channels.CustomBinding> , использующая учетные данные клиента Windows, где свойство `requireCancellation` имеет значение `false`;  
  
- любая привязка <xref:System.ServiceModel.Channels.CustomBinding> , использующая имя пользователя или учетные данные клиента Windows, а также безопасный обмен данными, где свойство `requireCancellation` имеет значение `false`.  
  
 Уровень олицетворения клиента службой зависит от привилегий, доступных учетной записи при попытке олицетворения, используемого типа олицетворения и, возможно, от уровня олицетворения, разрешенного клиентом.  
  
> [!NOTE]
> Если клиент и служба выполняются на одном компьютере и клиент выполняется от имени системной учетной записи (например, `Local System` или `Network Service`), клиент невозможно олицетворить, если установлен безопасный сеанс с маркерами контекста безопасности с отслеживанием состояния. Приложения Windows Form и консольные приложения обычно выполняются от имени учетной записи находящегося в системе пользователя, поэтому эту учетную запись можно олицетворять по умолчанию. Однако если клиент является страницей ASP.NET и эта страница размещается в IIS 6,0 или IIS 7,0, то клиент по умолчанию работает под учетной записью `Network Service`. Все предоставляемые системой привязки, поддерживающие защищенные сеансы, по умолчанию используют маркеры контекста безопасности с отслеживанием состояния. Однако если клиент является ASP.NET страницей и используются безопасные сеансы с отслеживанием состояния, клиент не сможет выполнить олицетворение. Дополнительные сведения об использовании СКТС с отслеживанием состояния в безопасном сеансе см. в разделе [инструкции. Создание маркера контекста безопасности для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
## <a name="impersonation-in-a-service-method-declarative-model"></a>Олицетворение в методе службы: декларативная модель  
 Большинство сценариев олицетворения предполагают выполнение метода службы в контексте вызывающего объекта. WCF предоставляет функцию олицетворения, которая делает это простым, позволяя пользователю указать требование олицетворения в атрибуте <xref:System.ServiceModel.OperationBehaviorAttribute>. Например, в следующем коде инфраструктура WCF олицетворяет вызывающий объект перед выполнением метода `Hello`. Все попытки обратиться к собственным ресурсам внутри метода `Hello` окажутся успешными только в том случае, если список управления доступом (ACL) ресурса дает права на доступ вызывающему объекту. Чтобы включить олицетворение, присвойте свойству <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> одно из значений перечисления <xref:System.ServiceModel.ImpersonationOption> : <xref:System.ServiceModel.ImpersonationOption.Required?displayProperty=nameWithType> или <xref:System.ServiceModel.ImpersonationOption.Allowed?displayProperty=nameWithType>, как показано в следующем примере.  
  
> [!NOTE]
> Если у службы имеется больше прав, чем у удаленного клиента, то используются учетные данные службы, если свойство <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> имеет значение <xref:System.ServiceModel.ImpersonationOption.Allowed>. Это значит, что если пользователь с более узкими правами предоставляет свои учетные данные, то метод выполняется с более широкими правами службы, и пользователь получает доступ к ресурсам, доступ к которым он бы сам получить не смог.  
  
 [!code-csharp[c_ImpersonationAndDelegation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#1)]
 [!code-vb[c_ImpersonationAndDelegation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#1)]  
  
 Инфраструктура WCF может олицетворять вызывающий объект только в том случае, если вызывающий объект прошел проверку подлинности с учетными данными, которые можно сопоставить с учетной записью пользователя Windows. Если служба настроена на прохождение проверки подлинности с использованием учетных данных, которые невозможно сопоставить с учетной записью Windows, метод службы не выполняется.  
  
> [!NOTE]
> В [!INCLUDE[wxp](../../../../includes/wxp-md.md)]происходит сбой олицетворения, если создается маркер контекста безопасности с отслеживанием состояния, что приводит к появлению исключения <xref:System.InvalidOperationException>. Дополнительные сведения см. в разделе [неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="impersonation-in-a-service-method-imperative-model"></a>Олицетворение в методе службы: императивная модель  
 Иногда вызывающему объекту требуется олицетворять не весь метод службы, а лишь его часть. В этом случае необходимо получить удостоверение Windows вызывающего объекта внутри метода службы и императивно выполнить олицетворение. Для этого необходимо с помощью свойства <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> объекта <xref:System.ServiceModel.ServiceSecurityContext> возвратить экземпляр класса <xref:System.Security.Principal.WindowsIdentity> и вызвать метод <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> перед использованием этого экземпляра.  
  
> [!NOTE]
> Не забудьте использовать инструкцию`Using` Visual Basic или инструкцию C# `using` для автоматической отмены действия олицетворения. Если вы не используете оператор или используете язык программирования, отличный от Visual Basic или C#, не забудьте вернуть уровень олицетворения. В противном случае возникнет угроза атаки типа «отказ в обслуживании» или «несанкционированное получение прав».  
  
 [!code-csharp[c_ImpersonationAndDelegation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#2)]
 [!code-vb[c_ImpersonationAndDelegation#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#2)]  
  
## <a name="impersonation-for-all-service-methods"></a>Олицетворение для всех методов службы  
 В некоторых случаях требуется выполнять в контексте вызывающего объекта все методы службы. Вместо явного включения этой функции для каждого метода в отдельности можно воспользоваться классом <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>. Как показано в следующем фрагменте кода, установите свойство <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ImpersonateCallerForAllOperations%2A> равным `true`. Объект <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> извлекается из коллекции расширений функциональности класса <xref:System.ServiceModel.ServiceHost> . Также обратите внимание, что свойство `Impersonation` объекта <xref:System.ServiceModel.OperationBehaviorAttribute> , применяемого к каждому из методов, тоже должно иметь значение <xref:System.ServiceModel.ImpersonationOption.Allowed> или <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
 [!code-csharp[c_ImpersonationAndDelegation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#3)]
 [!code-vb[c_ImpersonationAndDelegation#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#3)]  
  
 В следующей таблице описывается поведение WCF для всех возможных сочетаний `ImpersonationOption` и `ImpersonateCallerForAllServiceOperations`.  
  
|`ImpersonationOption`|`ImpersonateCallerForAllServiceOperations`|Поведение|  
|---------------------------|------------------------------------------------|--------------|  
|Обязательное|Н/Д|WCF олицетворяет вызывающего|  
|Allowed|false|WCF не олицетворяет вызывающего|  
|Allowed|true|WCF олицетворяет вызывающего|  
|NotAllowed|false|WCF не олицетворяет вызывающего|  
|NotAllowed|true|Disallowed. (Создается исключение <xref:System.InvalidOperationException> .)|  
  
## <a name="impersonation-level-obtained-from-windows-credentials-and-cached-token-impersonation"></a>Уровень олицетворения, получаемый на основании учетных данных Windows, и олицетворение с использованием кэшированного маркера  
 В некоторых сценариях при использовании учетных данных клиента Windows клиент может лишь частично управлять уровнем олицетворения в службе. Один из таких сценариев имеет место, когда клиент задает уровень олицетворения Anonymous. Второй сценарий имеет место при олицетворении с использованием кэшированного маркера. Для этого задается свойство <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> класса <xref:System.ServiceModel.Security.WindowsClientCredential> , к которому происходит обращение как к свойству универсального класса <xref:System.ServiceModel.ChannelFactory%601> .  
  
> [!NOTE]
> Задание уровня олицетворения Anonymous приводит к тому, что клиент входит в систему службы анонимно. Поэтому служба должна разрешать анонимный вход независимо от того, будет ли выполняться олицетворение.  
  
 Клиент может установить один из следующих уровней олицетворения: <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>или <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. При этом создается только маркер на заданном уровне, как показано в следующем фрагменте кода.  
  
 [!code-csharp[c_ImpersonationAndDelegation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#4)]
 [!code-vb[c_ImpersonationAndDelegation#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#4)]  
  
 В следующей таблице показаны уровни олицетворения, получаемые службой при олицетворении с использованием кэшированного маркера.  
  
|Значение`AllowedImpersonationLevel`|У службы есть `SeImpersonatePrivilege`|Служба и клиент поддерживают делегирование|Кэшированный маркер `ImpersonationLevel`|  
|---------------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|Anonymous (Анонимный)|Да|Н/Д|Олицетворение|  
|Anonymous (Анонимный)|Нет|Н/Д|Identification|  
|Identification|Н/Д|Н/Д|Identification|  
|Олицетворение|Да|Н/Д|Олицетворение|  
|Олицетворение|Нет|Н/Д|Identification|  
|Делегирование|Да|Да|Делегирование|  
|Делегирование|Да|Нет|Олицетворение|  
|Делегирование|Нет|Н/Д|Identification|  
  
## <a name="impersonation-level-obtained-from-user-name-credentials-and-cached-token-impersonation"></a>Уровень олицетворения, получаемый на основании учетных данных имени пользователя, и олицетворение с использованием кэшированного маркера  
 Передавая службе имя пользователя и пароль, клиент позволяет WCF войти в систему от имени этого пользователя, что эквивалентно присвоению свойству `AllowedImpersonationLevel` значения <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. (`AllowedImpersonationLevel` доступен в классах <xref:System.ServiceModel.Security.WindowsClientCredential> и <xref:System.ServiceModel.Security.HttpDigestClientCredential>.) В следующей таблице приводится уровень олицетворения, полученный при получении службой учетных данных имени пользователя.  
  
|`AllowedImpersonationLevel`|У службы есть `SeImpersonatePrivilege`|Служба и клиент поддерживают делегирование|Кэшированный маркер `ImpersonationLevel`|  
|---------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|Н/Д|Да|Да|Делегирование|  
|Н/Д|Да|Нет|Олицетворение|  
|Н/Д|Нет|Н/Д|Identification|  
  
## <a name="impersonation-level-obtained-from-s4u-based-impersonation"></a>Уровень олицетворения при олицетворении на базе S4U  
  
|У службы есть `SeTcbPrivilege`|У службы есть `SeImpersonatePrivilege`|Служба и клиент поддерживают делегирование|Кэшированный маркер `ImpersonationLevel`|  
|----------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|Да|Да|Н/Д|Олицетворение|  
|Да|Нет|Н/Д|Identification|  
|Нет|Н/Д|Н/Д|Identification|  
  
## <a name="mapping-a-client-certificate-to-a-windows-account"></a>Сопоставление сертификата клиента с учетной записью Windows  
 Клиент может выполнить свою проверку подлинности в службе с использованием сертификата, чтобы служба сама сопоставила клиент с существующей учетной записью в Active Directory. В следующем примере XML-кода показано, как настроить службы для сопоставления сертификата.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="MapToWindowsAccount">  
      <serviceCredentials>  
        <clientCertificate>  
          <authentication mapClientCertificateToWindowsAccount="true" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 В следующем примере кода показано, как настроить службу.  
  
```csharp
// Create a binding that sets a certificate as the client credential type.  
WSHttpBinding b = new WSHttpBinding();  
b.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a service host that maps the certificate to a Windows account.  
Uri httpUri = new Uri("http://localhost/Calculator");  
ServiceHost sh = new ServiceHost(typeof(HelloService), httpUri);  
sh.Credentials.ClientCertificate.Authentication.MapClientCertificateToWindowsAccount = true;  
```  
  
## <a name="delegation"></a>Делегирование  
 Чтобы выполнить делегирование внутренней службе, служба должна выполнить многоступенчатую (SSPI без резервной проверки подлинности NTLM) проверку подлинности или прямую проверку подлинности Kerberos во внутренней службе, используя удостоверение Windows клиента. Для делегирования внутренней службе создайте объект <xref:System.ServiceModel.ChannelFactory%601> и канал, а затем используйте этот канал для взаимодействия при олицетворении клиента. При такой модели делегирования расстояние, на котором внутренняя служба может располагаться относительно внешней службы, зависит от уровня олицетворения, полученного внешней службой. Если уровень олицетворения равен <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, внешняя и внутренняя службы должны выполняться на одном компьютере. Если уровень олицетворения равен <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, внешняя и внутренняя службы могут выполняться как на различных компьютерах, так и на одном компьютере. Для включения олицетворения уровня делегирования необходимо, чтобы политика домена Windows разрешала делегирование. Дополнительные сведения о настройке поддержки делегирования в Active Directory см. в разделе [Включение делегированной проверки подлинности](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc780217(v=ws.10)).  
  
> [!NOTE]
> Если клиент проходит проверку подлинности во внешней службе с использованием имени пользователя и пароля, соответствующих учетной записи Windows во внутренней службе, внешняя служба может пройти проверку подлинности во внутренней службе, используя имя пользователя и пароль клиента. Это особенно мощная форма потока обработки удостоверений, поскольку передача имени пользователя и пароля внутренней службе позволяет этой службе выполнять олицетворение; однако в этом случае невозможно делегирование, так как не использует проверка подлинности Kerberos. Действие элементов управления делегированием службы каталогов Active Directory не распространяется на проверку подлинности имени пользователя и пароля.  
  
### <a name="delegation-ability-as-a-function-of-impersonation-level"></a>Возможность делегирования как функция уровня олицетворения  
  
|Уровень олицетворения|Служба может выполнять делегирование между процессами|Служба может выполнять делегирование между компьютерами|  
|-------------------------|---------------------------------------------------|---------------------------------------------------|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Identification>|Нет|Нет|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>|Да|Нет|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Delegation>|Да|Да|  
  
 В следующем примере кода показано, как использовать делегирование.  
  
 [!code-csharp[c_delegation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_delegation/cs/source.cs#1)]
 [!code-vb[c_delegation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_delegation/vb/source.vb#1)]  
  
### <a name="how-to-configure-an-application-to-use-constrained-delegation"></a>Настройка приложения для использования ограниченного делегирования  
 Для использования ограниченного делегирования необходимо предварительно настроить отправитель, получатель и контроллер домена. Ниже перечислены операции по включению ограниченного делегирования. Дополнительные сведения о различиях между делегированием и ограниченным делегированием см. в части раздела [Расширения Kerberos Windows Server 2003](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc738207(v=ws.10)) , посвященной ограниченному делегированию.  
  
1. На контроллере домена снимите флажок **Учетная запись важна и не может быть делегирована** для учетной записи, от имени которой выполняется клиентское приложение.  
  
2. На контроллере домена установите флажок **Учетная запись доверена для делегирования** для учетной записи, от имени которой выполняется клиентское приложение.  
  
3. На контроллере домена настройте компьютер промежуточного уровня, чтобы он был доверен для делегирования. Для этого установите параметр **Доверять компьютеру делегирование** .  
  
4. На контроллере домена настройте компьютер промежуточного уровня, чтобы он использовал ограниченное делегирование. Для этого установите параметр **Этот компьютер доверенный для делегирования указанных служб** .  
  
 Более подробные инструкции по настройке ограниченного делегирования см. в разделе [Смена протокола Kerberos и ограниченное делегирование](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc739587(v=ws.10)).
  
## <a name="see-also"></a>См. также:

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>
- <xref:System.ServiceModel.ImpersonationOption>
- <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>
- <xref:System.ServiceModel.ServiceSecurityContext>
- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ImpersonateCallerForAllOperations%2A>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- <xref:System.ServiceModel.ChannelFactory%601>
- <xref:System.Security.Principal.TokenImpersonationLevel.Identification>
- [Использование олицетворения при обеспечении безопасности транспорта](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)
- [Олицетворение клиента](../../../../docs/framework/wcf/samples/impersonating-the-client.md)
- [Практическое руководство. Олицетворение клиента в рамках службы](../../../../docs/framework/wcf/how-to-impersonate-a-client-on-a-service.md)
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
