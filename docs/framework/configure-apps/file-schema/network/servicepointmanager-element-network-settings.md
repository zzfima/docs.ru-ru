---
title: "Элемент &lt;servicePointManager&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<servicePointManager> - элемент"
  - "servicePointManager - элемент"
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# Элемент &lt;servicePointManager&gt; (параметры сети)
Настраивает подключения к сетевым ресурсам.  
  
## Синтаксис  
  
```  
  
      <servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`checkCertificateName`|Указывает, следует ли системе перед использованием сертификата проверить, соответствует ли имя на сертификате имени узла сервера.  Значение по умолчанию — `true`.|  
|`checkCertificateRevocationList`|Указывает, следует ли системе перед использованием сертификата проверить, не был ли он отозван.  Значение по умолчанию — `false`.|  
|`dnsRefreshTimeout`|Определяет, как долго \(в миллисекундах\) разрешения DNS\-имен хранятся вместе с параметрами циклического перебора DNS.  По умолчанию установлено значение 120 000 миллисекунд \(2 минутам\).|  
|`enableDnsRoundRobin`|Указывает, возвращают ли разрешенные DNS\-имена узлов с несколькими IP\-адресами все адреса или только первый из них.  Значение по умолчанию — `false`.|  
|`encryptionPolicy`|Задает политику шифрования для сеанса SSL\/TLS на экземпляре<xref:System.Net.ServicePointManager>.  Возможные значения эквивалентны значениям для перечисления <xref:System.Net.Security.EncryptionPolicy>.  Использование <xref:System.Security.Authentication.CipherAlgorithmType> является обязательным, если политика шифрования имеет значение `NoEncryption`.  Значение по умолчанию — `RequireEncryption`.|  
|`expect100Continue`|Указывает, следует ли методам POST ожидать получения ответа `100-continue` от сервера.  Значение по умолчанию — `true`.|  
|`useNagleAlgorithm`|Указывает, следует ли подключениям, управляемым диспетчером точек обслуживания, использовать алгоритм Nagle.  Значение по умолчанию — `true`.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметры для пространства имен <xref:System.Net>.|  
  
## Заметки  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## См. также  
 <xref:System.Net.ServicePointManager>   
 <xref:System.Net.Security.EncryptionPolicy>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)