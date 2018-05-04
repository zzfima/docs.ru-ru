---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: aaf89f73b6de250aaa572b8fef31e5a1ebd5482b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcommonbehaviorsgt"></a>&lt;commonBehaviors&gt;
Раздел `commonBehaviors` может определяться только в файле machine.config. В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведения, используемые соответственно всеми конечными точками [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и службами на компьютере. Поведения, определенные в `endpointBehaviors`, применяются только к клиентам, а поведения, определенные в `serviceBehaviors`, применяются только к службам. Если поведение определяется как в разделе `commonBehaviors`, так и в разделе `behaviors`, преимущество имеет поведение в разделе `behaviors`.
