---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925842"
---
# <a name="dispatchersynchronization"></a>\<Диспатчерсинчронизатион >
  
Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.  
  
\<> System. serviceModel  
\<> поведения  
\<endpointBehaviors >  
\<> поведения  
  
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

Нет.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |  
| ------- | ----------- |  
| [\<> поведения](behavior-of-endpointbehaviors.md)|Задает поведение конечной точки. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
