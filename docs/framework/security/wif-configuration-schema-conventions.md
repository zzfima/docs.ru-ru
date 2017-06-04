---
title: "Соглашения о схеме конфигурации WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# Соглашения о схеме конфигурации WIF
В этом разделе обсуждаются соглашения, используемые в течение разделов конфигурации foundation идентификатора Windows \(WIF\) и описаны некоторые распространенные функции и атрибуты, используемые в [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) и разделах [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).  
  
<a name="BKMK_Modes"></a>   
## Режимы  
 Многие из элементов конфигурации WIF имеют атрибут `mode`.  Этот атрибут обычно контролирует, класс используется, чтобы сделать указанную часть обработки и которому элементы конфигурации разрешены как дочерние элементы текущего элемента.  Ошибка возникнет, если элементы конфигурации, которые содержатся в файле конфигурации игнорируются из\-за параметров режима.  
  
<a name="BKMK_TimespanValues"></a>   
## Значения Timespan  
 Где <xref:System.TimeSpan> используется как тип атрибута см. в разделе <xref:System.TimeSpan.Parse%28System.String%29> метод, чтобы увидеть разрешенный формат.  Этот формат соответствует следующей спецификации.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 Например, "30", "30.00:00", "30.00:00: 00 означают " все 30 дней. и "00:05", "00:05: 00 ", "0.00:05: 00,00 означают " все 5 минут.  
  
<a name="BKMK_CertificateReferences"></a>   
## Ссылки сертификата  
 Несколько ссылок взятия элементов к сертификатам, используя элемент `<certificateReference>`.  Ссылки на сертификат, доступны следующие атрибуты.  
  
|||  
|-|-|  
|`storeLocation`|Значение перечисления <xref:System.Security.Cryptography.X509Certificates.StoreLocation> : `CurrentUser` или `CurrentMachine`.|  
|`storeName`|Значение перечисления <xref:System.Security.Cryptography.X509Certificates.StoreName>; самые полезные для данного контекста `My` и `TrustedPeople`.|  
|`x509FindType`|Значение перечисления <xref:System.Security.Cryptography.X509Certificates.X509FindType>; самые полезные для данного контекста `FindBySubjectName` и `FindByThumbprint`.  Исключает возможность ошибки, рекомендуется, чтобы использовался тип `FindByThumbprint` в производственной среде.|  
|`findValue`|Значение, используемое для поиска сертификата, основанный на атрибуте `x509FindType`.  Исключает возможность ошибки, рекомендуется, чтобы использовался тип `FindByThumbprint` в производственной среде.  При `FindByThumbPrint` указано, этот атрибут принимает значение, форма шестнадцатеричный\- строки отпечаток сертификата; например, "97249e1a5fa6bee5e515b82111ef524a4c91583f".|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## Ссылки пользовательского типа  
 Несколько пользовательских типов ссылок элементов с помощью атрибута `type`.  Этот атрибут должен указать имя пользовательского типа.  Для ссылки на тип из глобального кэша сборок \(gac\), строгое имя должно использоваться.  Для ссылки на тип из сборки в каталоге папки, простой сборка\- квалифицированная ссылка может быть использована.  Типы, определенные в каталоге App\_Code\/также могут ссылаться просто указав имя типа без указания сборки.  
  
 Пользовательские типы должен быть производным от определенного типа и они должны предоставлять конструктор по умолчанию `public` аргументов \(0\).  
  
## См. также  
 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)   
 [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)