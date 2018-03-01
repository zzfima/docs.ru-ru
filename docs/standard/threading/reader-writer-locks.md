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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d005442ee74b46a0ecb1eaafe214e7190330cfe7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="reader-writer-locks"></a>Блокировки чтения и записи
Класс <xref:System.Threading.ReaderWriterLockSlim> позволяет нескольким потокам одновременно считывать данные из одного ресурса, но требует предоставить потоку монопольную блокировку для записи в этот ресурс.  
  
 Вы можете применить <xref:System.Threading.ReaderWriterLockSlim> в приложении для координированной синхронизации доступа к общему ресурсу между потоками. Блокировки выполняются непосредственно в <xref:System.Threading.ReaderWriterLockSlim>.  
  
 Как и для любого другого механизма синхронизации, нужно гарантировать невозможность обойти блокировку, организованную в <xref:System.Threading.ReaderWriterLockSlim>. Для этого можно, например, разработать класс, который инкапсулирует общий ресурс. Этот класс будет предоставлять элементы, которые получают доступ к закрытому общему ресурсу и используют закрытый <xref:System.Threading.ReaderWriterLockSlim> для синхронизации. В качестве примера изучите код класса <xref:System.Threading.ReaderWriterLockSlim>. <xref:System.Threading.ReaderWriterLockSlim> достаточно эффективен и может применяться для синхронизации отдельных объектов.  
  
 Оптимизируйте приложение так, чтобы снизить продолжительность операций чтения и записи. Длительные операции записи напрямую ухудшают пропускную способность, поскольку блокировки записи являются взаимоисключающими. Длительные операции чтения блокируют потоки, ожидающие записи. Если же появится хотя бы один поток, ожидающий записи, то заблокируются и те потоки, которые запрашивают доступ на чтение.  
  
> [!NOTE]
>  Класс [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] использует две блокировки чтения и записи: <xref:System.Threading.ReaderWriterLockSlim> и <xref:System.Threading.ReaderWriterLock>. Мы рекомендуем применять <xref:System.Threading.ReaderWriterLockSlim> при любых новых разработках. <xref:System.Threading.ReaderWriterLockSlim> действует так же, как и <xref:System.Threading.ReaderWriterLock>, но с более простыми правилами рекурсии и изменения состояния блокировки. <xref:System.Threading.ReaderWriterLockSlim> позволяет избежать многих ситуаций взаимоблокировки. Кроме того, производительность <xref:System.Threading.ReaderWriterLockSlim> значительно выше, чем у <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
