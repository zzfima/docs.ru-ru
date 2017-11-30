---
title: "Индуцированные коллекции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: garbage collection, forced
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92918e347b10dfcf3a0d6e2c08cec8c7a6963f5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="induced-collections"></a>Индуцированные коллекции
В большинстве случаев сборщик мусора может определить самое подходящее время для выполнения сборки мусора, поэтому следует дать ему возможность работать независимо. В очень редких случаях принудительная сборка мусора может улучшить производительность приложения. В таких случаях сборка мусора можно вызвать с помощью <xref:System.GC.Collect%2A?displayProperty=nameWithType> метод для принудительной сборки мусора.  
  
 Используйте <xref:System.GC.Collect%2A?displayProperty=nameWithType> метод при наличии значительное сокращение объема памяти, используемой в определенный момент в код приложения. Например, если приложение использует сложных диалоговое окно, которое содержит несколько элементов управления, при вызове метода <xref:System.GC.Collect%2A> при закрытии диалоговое окно может улучшить производительность посредством немедленной очистки памяти, используемой диалоговым окном. Убедитесь, что приложение не запускает сборку мусора слишком часто, потому что это может уменьшить производительность, если сборщик мусора непродуктивно пытается удалить объекты в не самое удачное время. Можно указать <xref:System.GCCollectionMode.Optimized?displayProperty=nameWithType> значение перечисления <xref:System.GC.Collect%2A> метод, чтобы собирать только в том случае, если коллекция будет эффективно, как описано в следующем разделе.  
  
## <a name="gc-collection-mode"></a>Режим сборки мусора  
 Можно использовать один из <xref:System.GC.Collect%2A?displayProperty=nameWithType> перегрузки метода, которые включают <xref:System.GCCollectionMode> значение для указания поведения принудительной сборки следующим образом.  
  
|Значение `GCCollectionMode`|Описание|  
|------------------------------|-----------------|  
|<xref:System.GCCollectionMode.Default>|Использует сбора мусора по умолчанию для используемой версии платформы .NET.|  
|<xref:System.GCCollectionMode.Forced>|Вызывает немедленное выполнение принудительной сборки мусора. Это эквивалентно вызову <xref:System.GC.Collect?displayProperty=nameWithType> перегрузки. В результате образуется коллекция полной блокировки всех поколений.<br /><br /> Можно также сжать кучи больших объектов, задав <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> свойства <xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce?displayProperty=nameWithType> до принудительного немедленного полной блокирующей сборки мусора.|  
|<xref:System.GCCollectionMode.Optimized>|Позволяет сборщику мусора определить, является ли текущий момент оптимальным для освобождения объектов.<br /><br /> Сборщик мусора может определить, что сборка мусора будет недостаточно продуктивна, в этом случае он возвратится без удаления объектов.|  
  
## <a name="background-or-blocking-collections"></a>Фоновые или блокирующие сборки  
 Можно вызвать <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=nameWithType> перегрузка метода для указания, блокируется ли Индуцированные коллекции или нет. Тип коллекции выполняется зависит от сочетания метода `mode` и `blocking` параметров. `mode`является членом <xref:System.GCCollectionMode> перечисления, и `blocking` — <xref:System.Boolean> значение. В следующей таблице перечислены взаимодействия `mode` и `blocking` аргументы.  
  
|`mode`|`blocking` = `true`|`blocking` = `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode.Forced> или <xref:System.GCCollectionMode.Default>|Блокирующий сбор выполнится, как только это станет возможным. Если выполняется фоновая сборка мусора и формирования равен 0 или 1, <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> метод немедленно запускает заблокированной коллекции и возвращает при завершении коллекции. Если выполняется фоновая сборка мусора и `generation` параметра равно 2, метод ожидает, пока фоновая сборка мусора завершения работы вызывает блокирующие сборки поколения 2 и возвращает.|Сборка выполнится, как только это станет возможным. <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> Метод запрашивает фоновая сборка мусора, но это не гарантируется; в зависимости от обстоятельств заблокированной коллекции по-прежнему может быть выполнена. Если фоновая сборка уже выполняется, метод возвращает управление немедленно.|  
|<xref:System.GCCollectionMode.Optimized>|Заблокированной коллекции может быть выполнено в зависимости от состояния сборщика мусора и `generation` параметра. Сборщик мусора пытается обеспечить оптимальную производительность.|Сборка может быть выполнена в зависимости от состояния сборщика мусора. <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> Метод запрашивает фоновая сборка мусора, но это не гарантируется; в зависимости от обстоятельств заблокированной коллекции по-прежнему может быть выполнена. Сборщик мусора пытается обеспечить оптимальную производительность. Если фоновая сборка уже выполняется, метод возвращает управление немедленно.|  
  
## <a name="see-also"></a>См. также  
 [Режимы задержки](../../../docs/standard/garbage-collection/latency.md)  
 [Сборка мусора](../../../docs/standard/garbage-collection/index.md)
