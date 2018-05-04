---
title: '&lt;add&gt; для &lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 20e1052a0517bb170cf796dd40d58c298185a958
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a>&lt;add&gt; для &lt;allowAccounts&gt;
Определяет учетную запись пользователя для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.  
  
 \<system.serviceModel.activation >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|securityIdentifier|Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя. Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS_USRS.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<allowAccounts >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Коллекция элементов конфигурации, которые содержат атрибут `securityIdentifier`, указывающий учетные записи пользователей для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.|  
  
## <a name="example"></a>Пример  
 В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
