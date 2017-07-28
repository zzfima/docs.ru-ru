---
title: "Элемент &lt;network&gt; (параметры сети) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#network"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<network> - элемент"
  - "network - элемент"
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;network&gt; (параметры сети)
Задает параметры сети для внешнего SMTP\-сервера.  
  
## Синтаксис  
  
```  
  
      <network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`clientDomain`|Определяет имя домена клиента, используемое запросом протокола SMTP для подключения к почтовому SMTP\-серверу.  Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.|  
|`defaultCredentials`|Указывает, следует ли использовать учетные данные пользователя по умолчанию для доступа к SMTP\-серверу для SMTP\-транзакций.  Значение по умолчанию — `false`.|  
|`enableSsl`|Задает, используется ли протокол SSL для доступа к почтовому SMTP\-серверу.  Значение по умолчанию — `false`.|  
|`host`|Задает имя почтового SMTP\-сервера для SMTP\-транзакций.  У данного атрибута нет значения по умолчанию.|  
|`password`|Задает пароль, используемый для проверки подлинности на почтовом SMTP\-сервере.  У данного атрибута нет значения по умолчанию.|  
|`port`|Задает номер порта, используемый для подключения к почтовому SMTP\-серверу.  Значение по умолчанию — 25.|  
|`targetName`|Задает имя поставщика услуг \(SPN\) для проверки подлинности при использовании расширенной защиты SMTP\-транзакций.  У данного атрибута нет значения по умолчанию.|  
|`userName`|Задает имя пользователя, используемое для проверки подлинности на почтовом SMTP\-сервере.  У данного атрибута нет значения по умолчанию.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<smtp\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Настраивает параметры отправки электронной почты по протоколу SMTP.|  
  
## Заметки  
 Перед началом работы с некоторыми  SMTP серверами требуется проверка подлинности учетных данных пользователя.  Если для проверки подлинности пользователя требуется использовать сетевые учетные данные по умолчанию на нужном узле, задайте для атрибута `defaultCredentials` значение `true`.  Свойство <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=fullName> может использоваться для получения текущего значения атрибута `defaultCredentials` из применимых файлов конфигурации.  
  
 Для проверки подлинности на SMTP сервере можно использоваться обычную проверку подлинности \(имя пользователя и пароль\).  Для этого следует предоставить допустимые имя пользователя и пароль для соответствующего SMTP сервера.  
  
> [!NOTE]
>  При обычной проверке подлинности `userName` и `password` передаются на сервер в незашифрованном виде.  При этом любой, кто имеет возможность отслеживать сетевой трафик, будет видеть передаваемые учетные данные и может воспользоваться ими для доступа к серверу.  Поэтому необходим более безопасный механизм проверки подлинности, такой как Kerberos или NTLM \(NT LAN Manager\). Если атрибут `defaultCredentials` имеет значение `true`, протоколы Kerberos или NTLM будут использоваться при условии их поддержки сервером.  
  
 Процедуры обычной проверки подлинности и проверки сетевых учетных данных по умолчанию являются взаимоисключающими, то есть если атрибут `defaultCredentials` имеет значение `true` и указаны имя пользователя и пароль, выполняется проверка сетевых учетных данных по умолчанию, а процедура обычной проверки подлинности игнорируется.  
  
 В случае обычной проверки подлинности при указании `userName` необходимо также указать `password` для выполнения собственной проверки подлинности на почтовом сервере.  
  
 Свойство <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=fullName> может использоваться для получения текущего значения атрибута `userName` из применимых файлов конфигурации.  Свойство <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=fullName> может использоваться для получения текущего значения атрибута `password` из применимых файлов конфигурации.  Атрибут `password` обычно не вносится в файлы конфигурации в целях безопасности.  
  
 Атрибут `clientDomain` изменяет имя домена клиента, используемое в первоначальном SMTP\-запросе протокола к SMTP\-серверу.  В качестве значения атрибута `clientDomain` можно использовать полное доменное имя локального компьютера, а не имя localhost, используемое по умолчанию.  Это обеспечивает большее соответствие стандартам протокола SMTP.  Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.  Свойство <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=fullName> может использоваться для получения текущего значения атрибута `clientDomain` из применимых файлов конфигурации.  
  
 Атрибут `targetName` используется для проверки подлинности при применении расширенной защиты.  Значение по умолчанию имеет форму "SMTPSVC\/\<узел\>", где \<узел\> — имя узла почтового SMTP\-сервера.  Свойство <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=fullName> может использоваться для получения текущего значения атрибута `targetName` из применимых файлов конфигурации.  
  
 Атрибут `enableSsl`  задает, используется ли протокол SSL для доступа к почтовому SMTP\-серверу.  Класс <xref:System.Net.Mail.SmtpClient?displayProperty=fullName> поддерживает только расширение службы SMTP для Secure SMTP через протокол TLS, определенный в RFC 3207.  В этом режиме сеанс SMTP начинается в незашифрованном канале, затем от клиента к серверу дается команда STARTTLS, чтобы переключиться на безопасное соединение с помощью протокола SSL.  См. RFC 3207 опубликованный IETF для получения дополнительных сведений.  
  
 Методом альтернативного подключения называется тот, при котором сеанс SSL устанавливается заранее, до отправки команд протокола.  Этот способ подключения иногда называют SMTPS и по умолчанию для него используется порт 465.  Этот альтернативный способ подключения с помощью протокола SSL в настоящее время не поддерживается.  
  
 Свойство <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=fullName> может использоваться для получения текущего значения атрибута `enableSsl` из применимых файлов конфигурации.  
  
## Пример  
 В следующем примере кода задаются соответствующие параметры протокола SMTP для отправки сообщений электронной почты с использованием сетевых учетных данных по умолчанию.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)