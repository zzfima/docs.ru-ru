---
title: Обработка событий (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 2ae32f0ac31c504e86d5cf39ed6a36cc5523a4a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053799"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Пошаговое руководство. Обработка событий (Visual Basic)
Это второе из двух разделов, которые демонстрируют, как работать с событиями. Первый раздел [Пошаговое руководство: Объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), показано, как объявлять и создавать события. Чтобы показать, как обрабатывать события при их возникновении в этом разделе используется форма и класс из предыдущего примера.  
  
 `Widget` Пример класса используются традиционные инструкции обработки событий. Visual Basic предоставляет другие методы для работы с событиями. В качестве упражнения, можно изменить пример и воспользоваться `AddHandler` и `Handles` инструкций.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Для обработки события PercentDone класса мини-приложения  
  
1. Поместите следующий код в `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     `WithEvents` Ключевое слово указывает, что переменная `mWidget` используется для обработки событий объекта. Необходимо указывать тип объекта, указав имя класса, из которого будет создан объект.  
  
     Переменная `mWidget` объявляется в `Form1` поскольку `WithEvents` переменные должны быть уровня класса. Это верно независимо от типа класса, который вы поместите их в.  
  
     Переменная `mblnCancel` используется для отмены `LongTask` метод.  
  
## <a name="writing-code-to-handle-an-event"></a>Написание кода для обработки события  
 Сразу после объявления переменной с помощью `WithEvents`, имя переменной, появляется в раскрывающемся списке слева класса **редактор кода**. При выборе `mWidget`, `Widget` класса события отображаются в правом стрелку раскрывающегося списка. Выбор события отображает соответствующей процедуры события с префиксом `mWidget` и символ подчеркивания. Все процедуры события, связанные с `WithEvents` переменной, получают имя переменной в качестве префикса.  
  
#### <a name="to-handle-an-event"></a>Чтобы обработать событие  
  
1. Выберите `mWidget` из левой стрелку раскрывающегося списка в **редактор кода**.  
  
2. Выберите `PercentDone` событий из правого раскрывающегося списка. **Редактор кода** открывает `mWidget_PercentDone` процедуру обработки события.  
  
    > [!NOTE]
    >  **Редактор кода** может быть полезным, но не обязательно для вставки новых обработчиков событий. В этом пошаговом руководстве более прямолинеен в просто скопируйте обработчики событий непосредственно в код.  
  
3. Добавьте следующий код в обработчик событий `mWidget_PercentDone` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     Каждый раз, когда `PercentDone` события, процедура события отображает процент выполнения в `Label` элемента управления. `DoEvents` Метод позволяет обновить надпись, а также предоставляет пользователю возможность воспользоваться **отменить** кнопки.  
  
4. Добавьте следующий код для `Button2_Click` обработчик событий:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 При нажатии кнопки **отменить** кнопку в активном `LongTask` работает под управлением, `Button2_Click` событие выполняется сразу же `DoEvents` оператор разрешает обработки события. Переменную уровня класса `mblnCancel` присваивается `True`и `mWidget_PercentDone` событий затем проверяет и устанавливает `ByRef Cancel` аргумент `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Подключение к объекту переменная WithEvents  
 `Form1` Теперь настроен для обработки `Widget` событий объекта. Остается лишь найти `Widget` где-нибудь.  
  
 При объявлении переменной `WithEvents` во время разработки, объект не связан с ним. Объект `WithEvents` переменная является так же, как и любой другой переменной объекта. Вам нужно создать объект и назначить ссылку на него с помощью `WithEvents` переменной.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Чтобы создать объект и назначить ссылку на него  
  
1. Выберите **(события Form1)** из левой стрелку раскрывающегося списка в **редактор кода**.  
  
2. Выберите `Load` событий из правого раскрывающегося списка. **Редактор кода** открывает `Form1_Load` процедуру обработки события.  
  
3. Добавьте следующий код для `Form1_Load` процедуру обработки события для создания `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 При выполнении этого кода Visual Basic создает `Widget` объекта и подключает его события к процедурам события, связанные с `mWidget`. Из этой точки, каждый раз, когда `Widget` вызывает его `PercentDone` событий, `mWidget_PercentDone` выполняется процедура обработки событий.  
  
#### <a name="to-call-the-longtask-method"></a>Чтобы вызвать метод LongTask  
  
- Добавьте следующий код в обработчик событий `Button1_Click` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Прежде чем `LongTask` вызывается метод, метки, что отображает процент завершения должен быть инициализирован и уровня класса `Boolean` флаг для отмены метода должно быть присвоено `False`.  
  
 `LongTask` вызывается для задачи с продолжительностью 12,2 секунды. `PercentDone` Событие возникает один раз каждые одной трети доли секунды. При каждом возникновении события, `mWidget_PercentDone` выполняется процедура обработки событий.  
  
 Когда `LongTask` это сделано, `mblnCancel` проверяется на предмет `LongTask` нормально, или если она остановлена, так как `mblnCancel` было присвоено `True`. Процент завершения обновляется только в первом случае.  
  
#### <a name="to-run-the-program"></a>Чтобы выполнить программу, выполните следующие действия.  
  
1. Нажмите клавишу F5, чтобы включить проект в режиме выполнения.  
  
2. Нажмите кнопку **запустить задачу** кнопки. Каждый раз `PercentDone` события, метка обновляется процент завершения задачи.  
  
3. Нажмите кнопку **отменить** кнопку, чтобы остановить задачу. Обратите внимание, что внешний вид **отменить** сразу после нажатия кнопки не изменяется. `Click` Событие не происходит до `My.Application.DoEvents` оператор разрешает обработку событий.  
  
    > [!NOTE]
    >  `My.Application.DoEvents` Метод отличается от обработки событий в точно так же, как и форму. Например, в этом пошаговом руководстве, необходимо нажать кнопку **отменить** дважды кнопку. Чтобы разрешить форме обрабатывать события напрямую, можно использовать многопоточность. Дополнительные сведения см. в разделе [управляемых потоков](../../../../standard/threading/index.md).
  
 Может оказаться полезным выполнить программу, нажав клавишу F11 и пошагово выполнять код строки за раз. Очевидно, что можно увидеть, как начинается выполнение `LongTask`и вкратце повторно вводит `Form1` каждый раз `PercentDone` события.  
  
 Что произойдет, если, во время выполнения обратно код `Form1`, `LongTask` снова вызывается метод? В худшем случае может произойти переполнение стека, если `LongTask` были вызывается при каждом возникновении события.  
  
 Может привести к переменной `mWidget` для обработки событий для другой `Widget` объекта, назначьте ссылку на новый `Widget` для `mWidget`. На самом деле, можно сделать в коде на `Button1_Click` этого каждый раз при нажатии кнопки.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Для обработки событий для разных мини-приложения  
  
- Добавьте следующую строку кода, чтобы `Button1_Click` процедуры, непосредственно перед строкой, которая считывает `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 Приведенный выше код создает новый `Widget` при каждом нажатии кнопки. Как только `LongTask` завершения метода, ссылка на `Widget` освобождается и `Widget` уничтожается.  
  
 Объект `WithEvents` переменная может содержать только одну ссылку одновременно, поэтому, если при назначении `Widget` объект `mWidget`, предыдущий `Widget` событий объекта больше не будет обрабатываться. Если `mWidget` является единственным объектной переменной, содержащей ссылку на старый `Widget`, уничтожения объекта. Если вы хотите обрабатывать события от нескольких `Widget` объекты, используют `AddHandler` инструкции для обработки событий из каждого объекта отдельно.  
  
> [!NOTE]
>  Можно объявить столько `WithEvents` переменные, как вам требуется. но массивы `WithEvents` переменные не поддерживаются.  
  
## <a name="see-also"></a>См. также

- [Пошаговое руководство: Объявление и вызов событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
