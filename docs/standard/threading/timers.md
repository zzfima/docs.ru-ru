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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 80b4cee03e934d3aec98ca323aac43f934c56455
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="timers"></a>таймеры
Таймеры являются простыми объектами, которые позволяют указать делегат для вызова в заданное время. Поток в пуле потоков выполняет операцию ожидания.  
  
 Работа с классом <xref:System.Threading.Timer?displayProperty=nameWithType> не имеет никаких сложностей. Вы создаете **таймер**, передав делегат <xref:System.Threading.TimerCallback> для метода обратного вызова, объект состояния, который будет передан при обратном вызове, время первого вызова и длительность периода между последующими обратными вызовами. Чтобы отменить ожидающий таймер, вызовите функцию **Timer.Dispose**.  
  
> [!NOTE]
>  Есть еще два класса таймера с другими возможностями. Класс <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> представляет собой элемент управления, который используется в визуальных конструкторах, то есть в контекстах пользовательского интерфейса. Он создает события в потоке пользовательского интерфейса. Класс <xref:System.Timers.Timer?displayProperty=nameWithType> является производным от <xref:System.ComponentModel.Component>, а значит может использоваться в визуальных конструкторах. Он также создает события, но уже в потоке <xref:System.Threading.ThreadPool>. Класс <xref:System.Threading.Timer?displayProperty=nameWithType> выполняет обратные вызовы в потоке <xref:System.Threading.ThreadPool> и никак не использует модель события. Он также передает в метод обратного вызова объект состояния, чего не делают другие таймеры. Он требует совсем немного ресурсов.  
  
 В следующем примере кода запускается таймер, который начинает работу через одну секунду (1000 миллисекунд) и срабатывает каждую секунду, пока пользователь не нажмет клавишу **ВВОД**. Переменная со ссылкой на таймер является полем уровня класса, чтобы таймер не пострадал от сборки мусора, пока не закончит свою работу. Дополнительные сведения об агрессивной сборке мусора см. в статье <xref:System.GC.KeepAlive%2A>.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Timer>  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
