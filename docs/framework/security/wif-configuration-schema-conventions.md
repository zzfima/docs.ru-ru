---
title: Соглашения о схеме конфигурации WIF
ms.date: 03/30/2017
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
author: BrucePerlerMS
ms.openlocfilehash: c02d467260a5197cdd01a3819f8a323655a8a08f
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045099"
---
# <a name="wif-configuration-schema-conventions"></a>Соглашения о схеме конфигурации WIF
В этом разделе описываются соглашения, используемые в разделах конфигурации Windows Identity Foundation (WIF), и некоторые общие компоненты и атрибуты, применяемые в разделах [\<system.identityModel>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) и [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a>Режимы  
 Многие элементы конфигурации WIF имеют атрибут `mode`. Как правило, он определяет то, какой класс применяется для выполнения определенного этапа обработки и какие элементы конфигурации могут использоваться как дочерние элементы текущего элемента. Если элементы, содержащиеся в файле конфигурации, игнорируются из-за настроек режима, возникает ошибка конфигурации.  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a>Значения временного диапазона  
 Если в качестве типа атрибута используется <xref:System.TimeSpan>, допустимый формат см. в описании метода <xref:System.TimeSpan.Parse%28System.String%29>. Этот формат соответствует следующей спецификации.  
  
`[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]`  
  
 Например, "30", "30.00:00" и "30.00:00:00" означают 30 дней, а "00:05", "00:05:00", "0.00:05:00.00" означают 5 минут.  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a>Ссылки на сертификаты  
 Некоторые элементы принимают ссылки на сертификаты посредством элемента `<certificateReference>`. При указании ссылки на сертификат доступны перечисленные ниже атрибуты.  
  
|||  
|-|-|  
|`storeLocation`|Значение из перечисления <xref:System.Security.Cryptography.X509Certificates.StoreLocation>: `CurrentUser` или `CurrentMachine`.|  
|`storeName`|Значение из перечисления <xref:System.Security.Cryptography.X509Certificates.StoreName>. Наиболее полезными в этом контексте являются значения `My` и `TrustedPeople`.|  
|`x509FindType`|Значение из перечисления <xref:System.Security.Cryptography.X509Certificates.X509FindType>. Наиболее полезными в этом контексте являются значения `FindBySubjectName` и `FindByThumbprint`. Чтобы избежать ошибок, в рабочих средах рекомендуется использовать тип `FindByThumbprint`.|  
|`findValue`|Значение, используемое для поиска сертификата, в соответствии с атрибутом `x509FindType`. Чтобы избежать ошибок, в рабочих средах рекомендуется использовать тип `FindByThumbprint`. Если задано значение `FindByThumbPrint`, этот атрибут принимает значение, которое представляет собой отпечаток сертификата в виде шестнадцатеричной строки, например 97249e1a5fa6bee5e515b82111ef524a4c91583f.|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a>Ссылки на пользовательские типы  
 Некоторые элементы ссылаются на пользовательские типы посредством атрибута `type`. В этом атрибуте должно указываться имя пользовательского типа. Для ссылки на тип из глобального кэша сборок (GAC) следует использовать строгое имя. Для ссылки на тип из сборки в каталоге Bin/ можно использовать простое имя с указанием сборки. На типы, определенные в каталоге App_Code/, можно также ссылаться просто по имени типа без указания сборки.  
  
 Пользовательские типы должны быть производными от указанного типа и предоставлять конструктор `public` по умолчанию (аргумент 0).  
  
## <a name="see-also"></a>См. также

- [\<> System. identityModel](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)
- [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
