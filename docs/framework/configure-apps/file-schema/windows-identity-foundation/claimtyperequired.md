---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6fb600aac46b3ee5cb54fa904d35ac7b7ed90719
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequiredgt"></a>&lt;claimTypeRequired&gt;
Указывает набор утверждений, необходимых для входящих токенов безопасности.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<claimTypeRequired >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<claimType >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|Указывает один обязательный или необязательный утверждений входящие маркеры безопасности.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы удостоверений.|
