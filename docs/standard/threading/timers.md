---
title: "Timers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threading [.NET Framework], timers"
  - "timers, about timers"
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Timers
Таймерами являются простые объекты, позволяющие указывать время вызова делегата.  Поток из пула потоков выполняет операцию ожидания.  
  
 Использование класса <xref:System.Threading.Timer?displayProperty=fullName> является прямолинейным.  Пользователь создает класс **Timer** путем передачи делегата <xref:System.Threading.TimerCallback> методу обратного вызова; объект, представляющий состояние, передаваемое в обратный вызов; начальное время вызова; время между обратными вызовами.  Для отмены счетчика нужно вызвать функцию **Timer.Dispose**.  
  
> [!NOTE]
>  Существует два других класса таймера.  Класс <xref:System.Windows.Forms.Timer?displayProperty=fullName> является элементом управления, который работает с визуальными конструкторами, и предназначен для использования в контекстах пользовательского интерфейса; он создает события в потоке пользовательского интерфейса.  Класс <xref:System.Timers.Timer?displayProperty=fullName> является производным из <xref:System.ComponentModel.Component>, поэтому он может использоваться вместе с визуальными конструкторами; он также создает события, однако делает это в потоке <xref:System.Threading.ThreadPool>.  Класс <xref:System.Threading.Timer?displayProperty=fullName> выполняет обратные вызовы потока <xref:System.Threading.ThreadPool> и совершенно не использует модель событий.  Он также предоставляет объект состояния методу обратного вызова, тогда как другие таймеры этого не делают.  Он является очень облегченным.  
  
 В следующем примере кода запускается таймер, который начинает работу после одной секунды \(1000 миллисекунд\) и отсчитывает каждую секунду до нажатия клавиши **ВВОД**.  Переменная, содержащая ссылку на таймер, является полем уровня класса, чтобы гарантировать то, что таймер не подлежит сборке мусора во время своей работы.  Дополнительные сведения об агрессивной сборке мусора см. в разделе <xref:System.GC.KeepAlive%2A>.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## См. также  
 <xref:System.Threading.Timer>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)