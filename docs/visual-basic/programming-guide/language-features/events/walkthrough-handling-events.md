---
title: "Обработка событий (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword, walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 17cd0bddbe8c89cf60e19f3f2af6f448ad465d70
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a>Пошаговое руководство. Обработка событий (Visual Basic)
Это второе из двух разделов, которые демонстрируют, как работать с событиями. Первый раздел [Пошаговое руководство: объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), показано, как объявлять и создавать события. В этом разделе используется форма и класс из предыдущего примера для демонстрации способов обработки событий при их возникновении.  
  
 `Widget` Пример класса используются традиционные инструкции обработки событий. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]имеются и другие способы работы с событиями. В качестве упражнения можно изменить для использования в этом примере `AddHandler` и `Handles` инструкции.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Для обработки события PercentDone класса мини-приложения  
  
1.  Поместите следующий код в `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     `WithEvents` Ключевое слово указывает, что переменная `mWidget` используется для обработки событий объекта. Укажите тип объекта, указав имя класса, из которого объект будет создан.  
  
     Переменная `mWidget` объявляется в `Form1` из-за `WithEvents` переменные должны быть уровня класса. Это верно независимо от типа класса, который они помещены.  
  
     Переменная `mblnCancel` используется для отмены `LongTask` метод.  
  
## <a name="writing-code-to-handle-an-event"></a>Написание кода для обработки событий  
 Сразу после объявления переменной с помощью `WithEvents`, имя переменной появляется в левом раскрывающемся списке класса **редактор кода**. При выборе `mWidget`, `Widget` класса события отображаются в правом раскрывающемся списке. Выбор события отображает соответствующей процедуры события с префиксом `mWidget` и символ подчеркивания. Всем процедурам событий, связанным с `WithEvents` переменной, получают имя переменной в качестве префикса.  
  
#### <a name="to-handle-an-event"></a>Чтобы обработать событие  
  
1.  Выберите `mWidget` из левого раскрывающегося списка в **редактор кода**.  
  
2.  Выберите `PercentDone` событий из правого раскрывающегося списка. **Редактор кода** открывает `mWidget_PercentDone` процедуру обработки события.  
  
    > [!NOTE]
    >  **Редактор кода** может быть полезным, но не обязательно для вставки новых обработчиков событий. В этом пошаговом руководстве является наиболее простым способом просто скопируйте обработчиков событий непосредственно в код.  
  
3.  Добавьте следующий код в обработчик событий `mWidget_PercentDone`.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Каждый раз, когда `PercentDone` события, процедура события отображает процент выполнения в `Label` элемента управления. `DoEvents` Метод позволяет обновить надпись, а также предоставляет пользователю возможность воспользоваться **отменить** кнопки.  
  
4.  Добавьте следующий код для `Button2_Click` обработчик событий:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents №&6;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 При нажатии кнопки **отменить** кнопки при `LongTask` работает, `Button2_Click` событий выполняется сразу после `DoEvents` оператор разрешает обработки события. Переменной уровня класса `mblnCancel` равен `True`и `mWidget_PercentDone` событий, затем проверяет ее и устанавливает `ByRef Cancel` аргумент `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Подключение к объекту переменная WithEvents  
 `Form1`Теперь настроен для обработки `Widget` событий объекта. Все, что остается лишь найти `Widget` где-нибудь.  
  
 При объявлении переменной `WithEvents` во время разработки, объект не связан с ним. A `WithEvents` переменной — так же, как любой другой переменной объекта. Необходимо создать объект и назначить ему ссылку с `WithEvents` переменной.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Чтобы создать объект и назначить ему ссылку  
  
1.  Выберите **(события Form1)** из левого раскрывающегося списка в **редактор кода**.  
  
2.  Выберите `Load` событий из правого раскрывающегося списка. **Редактор кода** открывает `Form1_Load` процедуру обработки события.  
  
3.  Добавьте следующий код для `Form1_Load` процедуру обработки события для создания `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 При выполнении этого кода [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает `Widget` объекта и подключает его события к процедурам события, связанным с `mWidget`. С этого момента, когда `Widget` вызывает его `PercentDone` событий, `mWidget_PercentDone` выполняется процедура обработки событий.  
  
#### <a name="to-call-the-longtask-method"></a>Чтобы вызвать метод LongTask  
  
-   Добавьте следующий код в обработчик событий `Button1_Click`.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents №&8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Прежде чем `LongTask` вызывается метод, метка отображается процент выполнения должен быть инициализирован и уровня класса `Boolean` флаг отмены метода должно быть присвоено `False`.  
  
 `LongTask`вызывается для задачи с продолжительностью 12,2 секунды. `PercentDone` Событие возникает один раз каждые треть секунды. Каждый раз при возникновении события `mWidget_PercentDone` выполняется процедура обработки событий.  
  
 Когда `LongTask` выполняется, `mblnCancel` проверяется на наличие `LongTask` нормально, или если он остановлен, так как `mblnCancel` было задано значение `True`. Процент завершения обновляется только в первом случае.  
  
#### <a name="to-run-the-program"></a>Чтобы выполнить программу, выполните следующие действия.  
  
1.  Нажмите клавишу F5, чтобы включить проект в режиме выполнения.  
  
2.  Щелкните **запустить задачу** кнопки. Каждый раз при `PercentDone` события, метка обновляется с указанием процента завершения задачи.  
  
3.  Щелкните **отменить** кнопку для отмены задачи. Обратите внимание, что внешний вид **отменить** сразу после нажатия кнопки не изменяется. `Click` Событие не происходит до `My.Application.DoEvents` оператор разрешает обработку событий.  
  
    > [!NOTE]
    >  `My.Application.DoEvents` Метод не обрабатывает события в точно так же, как формы. Например, в данном пошаговом руководстве необходимо нажать кнопку **отменить** кнопку дважды. Чтобы разрешить форме непосредственно обрабатывать события, можно использовать многопоточность. Дополнительные сведения см. в разделе [потоки](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Может оказаться полезным для запуска программы с F11 и пошаговое выполнение кода строки одновременно. Очевидно, можно увидеть, как начинается выполнение `LongTask`и кратко повторно вводит `Form1` каждый раз `PercentDone` события.  
  
 Что произойдет, если во время выполнения обратно в код `Form1`, `LongTask` снова вызван метод? В худшем случае может произойти переполнение стека, если `LongTask` вызывался каждый раз при возникновении события.  
  
 Может привести к переменной `mWidget` для обработки различных событий `Widget` объекта путем назначения ссылки на новый `Widget` в `mWidget`. На самом деле, может сделать код в `Button1_Click` этого каждый раз при нажатии кнопки.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Для обработки событий для другого объекта widget:  
  
-   Добавьте следующую строку кода, чтобы `Button1_Click` процедура, непосредственно перед строкой, которая считывает `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents №&9;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 Приведенный выше код создает новый `Widget` каждый раз при нажатии кнопки. Как только `LongTask` метод завершается, ссылка на `Widget` освобождается и `Widget` уничтожается.  
  
 Объект `WithEvents` переменная может содержать только одну ссылку на время, поэтому если при назначении `Widget` объект `mWidget`, предыдущий `Widget` событий объекта больше не будет обрабатываться. Если `mWidget` является единственной объектной переменной, содержащей ссылку на старый `Widget`, то объект уничтожается. Если требуется обрабатывать события из нескольких `Widget` объектов, используйте `AddHandler` инструкция для обработки событий из каждого объекта отдельно.  
  
> [!NOTE]
>  Можно объявить столько `WithEvents` переменные, как вам требуется. но массивы `WithEvents` переменные не поддерживаются.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Объявление и вызов событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)   
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
