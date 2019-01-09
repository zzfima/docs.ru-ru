---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 86660620113b162a9a5260b7026a64455284d184
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151466"
---
# <a name="ltdispatchersynchronizationgt"></a>&lt;dispatcherSynchronization&gt;
  
Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.  
  
\<system.serviceModel >  
\<варианты поведения >  
\<endpointBehaviors >  
\<поведение >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a>Тип  
  
`Type`  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты  
  
В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты

| Атрибут               | Описание       |
| ----------------------- | ----------------- |
| asynchronousSendEnabled | Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме. |
| `maxPendingReceives`    | Целочисленное значение, которое указывает число возможных получений по одному каналу.<br /><br /> Это значение должно настраиваться только после правильной настройки поведения регулирования службы. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание: |  
| ------- | ----------- |  
| [\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки. |

## <a name="see-also"></a>См. также

 <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
