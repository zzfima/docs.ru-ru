---
title: SpinWait
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
ms.openlocfilehash: 91588fc6e9c3c8e85de6a315c0743efb0137ecd5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128990"
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType> представляет собой упрощенный тип синхронизации, который позволяет обойтись в низкоуровневых сценариях без ресурсоемких переключений контекста и изменений режима ядра, которые выполняются для событий ядра. На многоядерных компьютерах, если сценарий не подразумевает долгосрочную блокировку ресурсов, эффективнее всего применить цикл ожидания в пользовательском режиме для потока в состоянии ожидания, который после нескольких десятков или сотен повторений снова попытается обратиться к ресурсу. Если ресурс окажется доступен после выхода из такого цикла, вы сэкономите несколько тысяч тактов процессора. Если же ресурс будет недоступен, то вы потратили лишь несколько циклов и можете снова применить ожидание на уровне ядра. Такой подход с циклом и последующим ожиданием иногда называют *двухэтапной операцией ожидания*.  
  
 <xref:System.Threading.SpinWait> предназначены для использования в сочетании с типами .NET Framework, которые являются оболочкой событий ядра, например <xref:System.Threading.ManualResetEvent>. <xref:System.Threading.SpinWait> также можно использовать отдельно, чтобы реализовать простой процесс ожидания в одной программе.  
  
 Не следует считать <xref:System.Threading.SpinWait> обычным пустым циклом. Он тщательно реализован с таким расчетом, чтобы правильно выполнять описанное поведение в разных ситуациях, и может самостоятельно переключать контекст, если ожидание оказывается слишком долгим. Долгим считается интервал времени, примерно соответствующий скорости перехода в режим ядра. Например, на одноядерных компьютерах <xref:System.Threading.SpinWait> немедленно прерывает квант времени, выделенный потоку, так как цикл ожидания в этой ситуации заблокирует выполнение всех потоков. Также <xref:System.Threading.SpinWait> немедленно приостанавливается даже на многоядерных компьютерах, если поток в состоянии ожидания может заблокировать потоки с более высоким приоритетом или сборщик мусора. Таким образом, если вы используете <xref:System.Threading.SpinWait> для двухэтапной операции ожидания, мы рекомендуем вручную вызвать ожидание ядра до того, как <xref:System.Threading.SpinWait> инициирует переключение контекста. <xref:System.Threading.SpinWait> предоставляет свойство <xref:System.Threading.SpinWait.NextSpinWillYield%2A>, которое следует проверять перед каждым вызовом <xref:System.Threading.SpinWait.SpinOnce%2A>. Если это свойство возвращает `true`, используйте собственную операцию ожидания. Пример реализации см. в статье [Практическое руководство. Использование объекта SpinWait для реализации двухэтапной операции ожидания](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Если вы просто выполняете цикл ожидания до наступления некоторого условия, не используя двухэтапную операцию ожидания, можно позволить <xref:System.Threading.SpinWait> самому переключать контекст, чтобы он соблюдал все условия и принципы корректной работы в операционной системе Windows. В следующем простом примере <xref:System.Threading.SpinWait> применяется в стеке без блокировки. Если вам нужен потокобезопасный стек с высокой производительностью, используйте <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.Thread.SpinWait%2A>
- [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
