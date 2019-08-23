---
title: Процедурные рабочие процессы
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: d1edd73b2276d0a3918b61c8da2d04769d09e7c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956108"
---
# <a name="procedural-workflows"></a>Процедурные рабочие процессы
Процедурные рабочие процессы используют методы управления потоком выполнения, аналогичные таким методам в процедурных языках. К этим конструкциям относятся `While` и `If`. Такие рабочие процессы можно свободно создавать с применением других действий управления потоком выполнения, таких как <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Sequence>.  
  
## <a name="controlling-execution-flow"></a>Управление потоком выполнения  
 Библиотека действий рабочих процессов содержит действия для моделирования большинства методов управления потоком выполнения, используемых в процедурных языках. Сюда входит следующее.  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 Чтобы использовать действия управления потоком, перетащите их из панели элементов **действия** в составное действие в окне конструктора.  
  
> [!NOTE]
> При использовании компонентов Windows Server AppFabric для размещения рабочих процессов на веб-ферме AppFabric переместит экземпляры между разными серверами AppFabric. Для этого необходимо, чтобы ресурсы можно было совместно использовать на всех узлах.  Ни одно из действий рабочих процессов .NET 4 по умолчанию не содержит операций, осуществляющих доступ к локальным ресурсам. Поскольку AppFabric не реализует ни одного механизма пометки рабочего процесса как неперемещаемого, разработчику не следует создавать пользовательские действия, в которых возникает ошибка при перемещении рабочего процесса.  
  
## <a name="see-also"></a>См. также

- [Рабочие процессы с блок-схемой](flowchart-workflows.md)
