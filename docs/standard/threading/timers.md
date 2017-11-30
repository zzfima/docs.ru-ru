---
title: "таймеры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fca27cf5261e253c2bb3d3a10fa3db31f28a2415
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="timers"></a>таймеры
Таймеры являются простые объекты, которые позволяют указать делегат, вызываемый в указанное время. Поток в пуле потоков выполняет операцию ожидания.  
  
 С помощью <xref:System.Threading.Timer?displayProperty=nameWithType> класса выполняется просто. Вы создаете **таймера**, передав <xref:System.Threading.TimerCallback> делегат для метода обратного вызова, объект, представляющий состояние, которое будет передано обратного вызова, raise начальное время и время, представляющий время обратного вызова. Чтобы отменить ожидающие таймера, вызовите **Timer.Dispose** функции.  
  
> [!NOTE]
>  Существует два других класса таймера. <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> Элемент управления, который используется в конструкторах visual и предназначен для использования в контекстах пользовательского интерфейса; он создает события в потоке пользовательского интерфейса. <xref:System.Timers.Timer?displayProperty=nameWithType> Класс является производным от <xref:System.ComponentModel.Component>, поэтому он может использоваться с визуальными конструкторами; он также создает события, но делает это в <xref:System.Threading.ThreadPool> потока. <xref:System.Threading.Timer?displayProperty=nameWithType> Класс выполняет обратные вызовы <xref:System.Threading.ThreadPool> потоков и вообще не использовать модель событий. Он также предоставляет объект состояния методу обратного вызова, который другие таймеры этого не делают. Он является очень облегченным.  
  
 В следующем примере кода запускается таймер, который начинает работу после одной секунды (1000 миллисекунд) и отсчитывает каждую секунду до нажатия клавиши **ввод** ключа. Переменная, содержащая ссылку на таймер является полем уровня класса, чтобы убедиться, что таймер не подвергаются сборке мусора пока она продолжает работать. Дополнительные сведения об агрессивной сборке мусора см. в разделе <xref:System.GC.KeepAlive%2A>.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Timer>  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
