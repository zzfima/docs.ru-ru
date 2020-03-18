---
title: Таймеры
description: Узнайте, какие таймеры .NET можно использовать в многопоточной среде.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: d7d1fa13b02fe7425fa9b4cb81ba20297a23fe4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128955"
---
# <a name="timers"></a>Таймеры

.NET предоставляет два таймера, которые можно использовать в многопоточной среде:

- <xref:System.Threading.Timer?displayProperty=nameWithType>, который выполняет метод одного обратного вызова в потоке <xref:System.Threading.ThreadPool> с регулярными интервалами.
- <xref:System.Timers.Timer?displayProperty=nameWithType>, который по умолчанию порождает событие в потоке <xref:System.Threading.ThreadPool> с регулярными интервалами.

> [!NOTE]
> В некоторых реализациях .NET может содержать дополнительные таймеры:
>
> - <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> — компонент Windows Forms, который вызывает событие через определенные интервалы времени. У этого компонента нет интерфейса пользователя. Он предназначен для однопоточной среды.  
> - <xref:System.Web.UI.Timer?displayProperty=nameWithType> — компонент ASP.NET, который выполняет асинхронную или синхронную обратную передачу веб-страницы с регулярными интервалами.
> - <xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType> — таймер, интегрированный в очередь <xref:System.Windows.Threading.Dispatcher>, которая обрабатывается с заданными интервалом и приоритетом.

## <a name="the-systemthreadingtimer-class"></a>Класс System.Threading.Timer

Класс <xref:System.Threading.Timer?displayProperty=nameWithType> позволяет непрерывно вызывать делегат через определенные интервалы времени. Этот класс также можно использовать для планирования одного вызова к делегату через заданный интервал времени. Делегат выполняется в потоке <xref:System.Threading.ThreadPool>.

При создании объекта <xref:System.Threading.Timer?displayProperty=nameWithType> вы указываете делегат <xref:System.Threading.TimerCallback>, который определяет метод обратного вызова, необязательный объект состояния, который передается обратному вызову, временную задержку до первого вызова обратного вызова и интервал времени между вызовами обратного вызова. Чтобы отменить ожидающий таймер, вызовите метод <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>.

В следующем примере создается таймер, который вызывает предоставленный делегат в первый раз через одну секунду (1000 миллисекунд), а затем каждые две секунды. Объект состояния в примере используется для подсчета вызовов делегата. Таймер останавливается после 10 вызовов.

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

Дополнительные сведения и примеры см. в разделе <xref:System.Threading.Timer?displayProperty=nameWithType>.

## <a name="the-systemtimerstimer-class"></a>Класс System.Timers.Timer

Еще один таймер, который может использоваться в многопоточной среде, — <xref:System.Timers.Timer?displayProperty=nameWithType>. По умолчанию он порождает событие в потоке <xref:System.Threading.ThreadPool>.

При создании объекта <xref:System.Timers.Timer?displayProperty=nameWithType> вы можете указать интервал времени, в котором порождается событие <xref:System.Timers.Timer.Elapsed>. Используйте свойство <xref:System.Timers.Timer.Enabled%2A>, чтобы указать, должен ли таймер порождать событие <xref:System.Timers.Timer.Elapsed>. Если вам нужно, чтобы событие <xref:System.Timers.Timer.Elapsed> вызывалось только один раз по истечении заданного интервала, установите для <xref:System.Timers.Timer.AutoReset%2A> значение `false`. Свойство <xref:System.Timers.Timer.AutoReset%2A> по умолчанию имеет значение `true`, то есть событие <xref:System.Timers.Timer.Elapsed> вызывается регулярно с интервалом, определенным в свойстве <xref:System.Timers.Timer.Interval%2A>.

Дополнительные сведения и примеры см. в разделе <xref:System.Timers.Timer?displayProperty=nameWithType>.
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md)
