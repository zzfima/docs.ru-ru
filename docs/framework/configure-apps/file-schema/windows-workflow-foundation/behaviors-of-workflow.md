---
title: '&lt;варианты поведения&gt; рабочего процесса'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b4ad7fb54cc8a03f5dd698055da5a29e719775c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731677"
---
# <a name="ltbehaviorsgt-of-workflow"></a>&lt;варианты поведения&gt; рабочего процесса
Этот элемент содержит **serviceBehaviors** коллекции.  Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса. Каждый элемент поведения идентифицируется по уникальному **имя** атрибута.  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Корневой элемент всех элементов конфигурации рабочего процесса.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Настройка и расширение среды выполнения с помощью поведений](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
