---
title: '&lt;persistenceProvider&gt;'
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: ba02977a7df44931ae195040949e9a8eb0c141b5
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152025"
---
# <a name="ltpersistenceprovidergt"></a>&lt;persistenceProvider&gt;
Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<persistenceProvider >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|persistenceOperationTimeout|Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости. Значение по умолчанию — «00: 00:30».|  
|type|Строка, указывающая тип используемой фабрики поставщика сохраняемости.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF. Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
