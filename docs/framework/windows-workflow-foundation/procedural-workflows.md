---
title: Процедурные рабочие процессы
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 2ef23f61e67e0b4c08f12322bac429762205ef8d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622842"
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
>  Если для размещения рабочих процессов в веб-ферме используется [!INCLUDE[dublin](../../../includes/dublin-md.md)], AppFabric будет перемещать экземпляры между различными серверами AppFabric. Для этого необходимо, чтобы ресурсы можно было совместно использовать на всех узлах.  Ни одно из действий рабочих процессов .NET 4 по умолчанию не содержит операций, осуществляющих доступ к локальным ресурсам. Поскольку AppFabric не реализует ни одного механизма пометки рабочего процесса как неперемещаемого, разработчику не следует создавать пользовательские действия, в которых возникает ошибка при перемещении рабочего процесса.  
  
## <a name="see-also"></a>См. также

- [Рабочие процессы с блок-схемой](flowchart-workflows.md)
