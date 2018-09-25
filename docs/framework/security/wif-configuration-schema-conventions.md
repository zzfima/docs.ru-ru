---
title: Соглашения о схеме конфигурации WIF
ms.date: 03/30/2017
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
author: BrucePerlerMS
ms.openlocfilehash: dc2e8f7070af3ef907e4987964bb5aa83f889186
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070361"
---
# <a name="wif-configuration-schema-conventions"></a>Соглашения о схеме конфигурации WIF
В этом разделе описываются соглашения, используемые в разделах конфигурации Windows Identity Foundation (WIF), и некоторые общие компоненты и атрибуты, применяемые в разделах [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) и [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a>Режимы  
 Многие элементы конфигурации WIF имеют атрибут `mode`. Как правило, он определяет то, какой класс применяется для выполнения определенного этапа обработки и какие элементы конфигурации могут использоваться как дочерние элементы текущего элемента. Если элементы, содержащиеся в файле конфигурации, игнорируются из-за настроек режима, возникает ошибка конфигурации.  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a>Значения временного диапазона  
 Если в качестве типа атрибута используется <xref:System.TimeSpan>, допустимый формат см. в описании метода <xref:System.TimeSpan.Parse%28System.String%29>. Этот формат соответствует следующей спецификации.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
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
 [\<system.identityModel >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)  
 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
