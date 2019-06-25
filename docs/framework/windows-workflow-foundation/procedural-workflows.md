---
title: Процедурные рабочие процессы
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 15ff155fb057c4c10663d383a8942108c6e4375c
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348368"
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
  
 Чтобы использовать действия управления потоком, путем перетаскивания их из **действия** панели инструментов в составное действие в окне конструктора.  
  
> [!NOTE]
>  При использовании функции размещения Windows Server AppFabric для размещения рабочих процессов на веб-ферме, AppFabric будет перемещать экземпляры между различными серверами AppFabric. Для этого необходимо, чтобы ресурсы можно было совместно использовать на всех узлах.  Ни одно из действий рабочих процессов .NET 4 по умолчанию не содержит операций, осуществляющих доступ к локальным ресурсам. Поскольку AppFabric не реализует ни одного механизма пометки рабочего процесса как неперемещаемого, разработчику не следует создавать пользовательские действия, в которых возникает ошибка при перемещении рабочего процесса.  
  
## <a name="see-also"></a>См. также

- [Рабочие процессы с блок-схемой](flowchart-workflows.md)
