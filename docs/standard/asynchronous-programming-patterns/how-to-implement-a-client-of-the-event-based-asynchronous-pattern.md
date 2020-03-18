---
title: Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: 50aa36d2caf774638ad20323813f0de3703aab2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "69950721"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях
В приведенном ниже примере кода показано, как использовать компонент, который соответствует принципам [асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md). В форме для этого примера используется компонент `PrimeNumberCalculator`, который описывается в статье [Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Запустив проект с этим примером, вы увидите форму расчета простых чисел с сеткой и двумя кнопками: **Start New Task** (Выполнить новую задачу) и **Cancel** (Отменить). Вы можете нажать кнопку **Start New Task** (Выполнить новую задачу) несколько раз подряд, и при каждом нажатии запустится асинхронная операция вычисления, которая проверяет, является ли случайное проверяемое число простым. Форма периодически обновляется, отображая ход выполнения и накопленные результаты. Каждой операции присваивается уникальный идентификатор задачи. Результат вычисления отображается в столбце **Result** (Результат). Если проверяемое число не является простым, оно дополняется отметкой **Composite** (Составное) и значением его первого делителя.  
  
 Кнопка **Cancel** (Отменить) позволяет отменить все операции, ожидающие выполнения. Вы можете выбрать несколько элементов.  
  
> [!NOTE]
> Большинство чисел не будут простыми. Если после нескольких операций вам не удастся найти простое число, просто запустите еще несколько задач. Рано или поздно простые числа будут обнаружены.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
