---
title: <behaviors>рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945994"
---
# <a name="behaviors-of-workflow"></a>\<> поведения рабочего процесса
Этот элемент содержит коллекцию **serviceBehaviors** .  Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса. Каждый элемент поведения определяется с помощью уникального атрибута **имени** .  
  
 \<системой. > ServiceModel  
  
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
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceBehaviors >](servicebehaviors-of-workflow.md)|В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|Корневой элемент всех элементов конфигурации рабочего процесса.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Настройка и расширение среды выполнения с помощью поведений](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
