---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 34c12a05ee363df6b6cfc9ff3809bab50ee8d522
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747581"
---
# <a name="ltdispatchersynchronizationgt"></a>&lt;dispatcherSynchronization&gt;

Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.

\<system.serviceModel > \<поведения > \<endpointBehaviors > \<поведения >

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

| Элемент | Описание |  
| ------- | ----------- |  
| [\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки. |

## <a name="see-also"></a>См. также

 <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
