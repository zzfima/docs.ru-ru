---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926603"
---
# <a name="allowaccounts"></a>\<Алловаккаунтс >
Содержит коллекцию элементов конфигурации, указывающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и которым предоставляется доступ к службе общего доступа.  
  
 \<> System. serviceModel. Activation  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|Добавляет учетную запись пользователя для процессов, на которых размещаются службы WCF, и предоставляет доступ к подключению к службе общего доступа.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|NET. pipe > или [ \<](net-pipe.md) [ \<NET. TCP >](net-tcp.md)|Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
