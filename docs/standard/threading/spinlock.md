---
title: SpinLock
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
ms.openlocfilehash: eac9a1be38ea81e8ccee1d05d9061ceeb597627f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106169"
---
# <a name="spinlock"></a>SpinLock
Структура <xref:System.Threading.SpinLock> — это примитив низкоуровневой синхронизации со взаимоисключающей блокировкой, которая выполняет цикл ожидания, пока не получит блокировку. На многоядерных компьютерах, если предполагается короткое время ожидания и минимальный риск состязаний, <xref:System.Threading.SpinLock> может выполняться быстрее, чем другие виды блокировок. Но мы рекомендуем использовать <xref:System.Threading.SpinLock> только в том случае, если в ходе профилирования подтверждается существенное ухудшение производительности при работе с методом <xref:System.Threading.Monitor?displayProperty=nameWithType> и методами <xref:System.Threading.Interlocked>.  
  
 <xref:System.Threading.SpinLock> может освободить квант процессорного времени для потока, даже не создав блокировку. Такое поведение позволяет избежать инверсии приоритетов потока, а также не мешать работе сборщика мусора. При работе с <xref:System.Threading.SpinLock> важно гарантировать, чтобы ни один поток не устанавливал блокировку дольше, чем на очень короткий промежуток времени, и чтобы ни один поток не мог заблокироваться в режиме удержания блокировки.  
  
 Поскольку SpinLock является типом значения, его необходимо явным образом передавать по ссылке, если две копии значения должны указывать на одну и ту же блокировку.  
  
 Дополнительные сведения об использовании этого типа см. в статье о структуре <xref:System.Threading.SpinLock?displayProperty=nameWithType>. Некоторые примеры есть в статье [Практическое руководство. SpinLock и низкоуровневая синхронизация](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock> поддерживает режим *отслеживания*-*потоков*, удобный на этапе разработки для выявления потока, который удерживает блокировку в конкретный момент времени. Режим отслеживания потоков очень полезен для отладки, но мы рекомендуем отключать его в рабочей версии программы, чтобы не снижать производительность. Дополнительные сведения см. в статье [Практическое руководство. Включение режима отслеживания потоков в SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## <a name="see-also"></a>См. также раздел

- [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
