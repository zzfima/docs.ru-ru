---
title: "Блокировки чтения и записи"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a>Блокировки чтения и записи
<xref:System.Threading.ReaderWriterLockSlim> Класс позволяет нескольким потокам чтение ресурса, но требует поток ждать монопольную блокировку для записи ресурса.  
  
 Можно использовать <xref:System.Threading.ReaderWriterLockSlim> в приложении для обеспечения синхронизации доступа к общему ресурсу между потоками. Блокировки <xref:System.Threading.ReaderWriterLockSlim> сам.  
  
 Как в любом механизме синхронизации, необходимо убедиться, что потоки не обходят блокировку, предоставляемая <xref:System.Threading.ReaderWriterLockSlim>. Один из способов сделать это является разработка класса, который инкапсулирует общий ресурс. Этот класс должен предоставлять элементы, доступ к закрытому общему ресурсу и используют закрытый <xref:System.Threading.ReaderWriterLockSlim> для синхронизации. Например, см. пример кода для <xref:System.Threading.ReaderWriterLockSlim> класса. <xref:System.Threading.ReaderWriterLockSlim>является эффективным, который будет использоваться для синхронизации отдельных объектов.  
  
 Приложение для уменьшить время чтения и записи операций. Длительные операции записи непосредственно влияет пропускной способности, поскольку блокировка записи является взаимоисключающей. Длинная чтение операций блокируют ожидающие средства записи, а если хотя бы один поток для записи, потоки, запрашивающие доступ для чтения также будут заблокированы.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Имеет два блокировки чтения и записи, <xref:System.Threading.ReaderWriterLockSlim> и <xref:System.Threading.ReaderWriterLock>. <xref:System.Threading.ReaderWriterLockSlim>рекомендуется для всех новых разработках. <xref:System.Threading.ReaderWriterLockSlim>Аналогично <xref:System.Threading.ReaderWriterLock>, но использует упрощенные правила рекурсии и повышения или понижения уровня состояния блокировки. <xref:System.Threading.ReaderWriterLockSlim>позволяет избежать многих случаях потенциальной взаимоблокировки. Кроме того, производительность <xref:System.Threading.ReaderWriterLockSlim> значительно лучше, чем <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
