---
title: "События конфликтов (трассировка событий Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 931a3f7d5cbc441a3cae2b7359d129dff02afd44
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="contention-etw-events"></a>События конфликтов (трассировка событий Windows)
События конфликтов возникают каждый раз при обнаружении конфликта за блокировки <xref:System.Threading.Monitor?displayProperty=fullName> или блокировки машинного кода, используемые средой выполнения. Конфликт происходит, когда поток ожидает блокировку, которая обрабатывается другим потоком.  
  
 В следующей таблице показаны ключевое слово, в котором возникает событие конфликта, а также уровень события. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`ContentionKeyword` (0x4000)|Информационный (4)|  
  
 В таблице ниже представлены сведения о событии.  
  
|Событие|Идентификатор события|Условие вызова|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|81|Начало конфликта. Это событие не содержит сведений о времени, в течение которого поток ожидает получения блокировки. Оно возникает только в том случае, когда поток ожидает получения блокировки.|  
|`ContentionStop`|81|Конец конфликта.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|Флаги|win:UInt8|0 — управляемый; 1 — машинный.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра среды CLR.|  
  
## <a name="see-also"></a>См. также  
 [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md)

