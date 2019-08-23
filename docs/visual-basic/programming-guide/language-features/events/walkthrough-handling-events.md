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
ms.openlocfilehash: 12267e0a70419298bc581421c4f3a220088d205f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956302"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Пошаговое руководство. Обработка событий (Visual Basic)
Это второй из двух разделов, демонстрирующих работу с событиями. Первый раздел, [пошаговое руководство. Объявляя и вызывая](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)события, показывает, как объявлять и создавать события. В этом разделе используется форма и класс из этого пошагового руководства, чтобы продемонстрировать, как обрабатывались события, когда они выполняются.  
  
 В `Widget` примере класса используются традиционные инструкции по обработке событий. Visual Basic предоставляет другие методы для работы с событиями. В качестве упражнения можно изменить этот пример для использования `AddHandler` инструкций и. `Handles`  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Для управления событием PercentDone класса Widget  
  
1. Поместите следующий код в `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     Ключевое слово указывает, что `mWidget` переменная используется для управления событиями объекта. `WithEvents` Тип объекта указывается путем указания имени класса, из которого будет создан объект.  
  
     Переменная `mWidget` объявлена в `Form1` , поскольку `WithEvents` переменные должны быть уровня класса. Это справедливо независимо от типа класса, в котором они размещены.  
  
     Переменная `mblnCancel` используется для `LongTask` отмены метода.  
  
## <a name="writing-code-to-handle-an-event"></a>Написание кода для обработчика события  
 Как только вы объявили переменную с `WithEvents`помощью, имя переменной отображается в левом раскрывающемся списке **редактора кода**класса. При выборе `mWidget` `Widget` в правом раскрывающемся списке отображаются события класса. При выборе события отображается соответствующая процедура события с префиксом `mWidget` и символом подчеркивания. Всем процедурам события, связанным `WithEvents` с переменной, присваивается имя переменной в виде префикса.  
  
#### <a name="to-handle-an-event"></a>Чтобы обработать событие  
  
1. Выберите `mWidget` из левого раскрывающегося списка в **редакторе кода**.  
  
2. `PercentDone` Выберите событие из правого раскрывающегося списка. **Редактор кода** открывает `mWidget_PercentDone` процедуру события.  
  
    > [!NOTE]
    > **Редактор кода** удобен, но не является обязательным для вставки новых обработчиков событий. В этом пошаговом руководстве более прямым просто скопировать обработчики событий непосредственно в код.  
  
3. Добавьте следующий код в обработчик событий `mWidget_PercentDone` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     При каждом возникновении `Label` событияпроцедурасобытияотображаетпроцентзавершения`PercentDone` в элементе управления. Метод позволяет перекрасить метку, а также дает пользователю возможность нажать кнопку **Отмена.** `DoEvents`  
  
4. Добавьте следующий код для `Button2_Click` обработчика событий:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Если пользователь нажимает кнопку **Отмена** во время `LongTask` выполнения, `Button2_Click` событие выполняется сразу же после того `DoEvents` , как инструкция допускает обработку события. Переменной `mblnCancel` уровня класса присваивается `True`значение, а `mWidget_PercentDone` `ByRef Cancel` затем событие проверяется и присваивает аргументу значение. `True`  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Подключение переменной WithEvents к объекту  
 `Form1`теперь настроен на обработку `Widget` событий объекта. Все, что остается, — найти `Widget` кое-что.  
  
 При объявлении переменной `WithEvents` во время разработки объект не связан с ним. `WithEvents` Переменная аналогична любой другой объектной переменной. Необходимо создать объект и присвоить ему `WithEvents` ссылку на переменную.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Создание объекта и присвоение ему ссылки  
  
1. Выберите **(события Form1)** в левом раскрывающемся списке в **редакторе кода**.  
  
2. `Load` Выберите событие из правого раскрывающегося списка. **Редактор кода** открывает `Form1_Load` процедуру события.  
  
3. Добавьте следующий код для `Form1_Load` процедуры события, чтобы `Widget`создать:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 При выполнении этого кода Visual Basic создает `Widget` объект и подключает его события к процедурам событий, связанным с. `mWidget` С этого момента каждый раз, когда `Widget` `PercentDone` вызывает событие, `mWidget_PercentDone` выполняется процедура события.  
  
#### <a name="to-call-the-longtask-method"></a>Вызов метода LongTask  
  
- Добавьте следующий код в обработчик событий `Button1_Click` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Перед вызовом `Boolean`методанеобходимо инициализировать метку, которая отображает процент завершения, а флаг уровня класса для отмены `False`метода должен иметь значение. `LongTask`  
  
 `LongTask`вызывается с длительностью задачи в 12,2 секунд. `PercentDone` Событие вызывается раз в секунду с каждой третьей стороной. При каждом возникновении `mWidget_PercentDone` события выполняется процедура события.  
  
 По `LongTask` `LongTask` `mblnCancel` `True`завершении проверяется,завершилосьлинормальноезавершениеилиостановлено,таккакбылоустановленозначение.`mblnCancel` Процент завершения обновляется только в первом случае.  
  
#### <a name="to-run-the-program"></a>Чтобы выполнить программу, выполните следующие действия.  
  
1. Нажмите клавишу F5, чтобы перевести проект в режим выполнения.  
  
2. Нажмите кнопку **запустить задачу** . При каждом возникновении события метка обновляется в процентах от завершенной задачи. `PercentDone`  
  
3. Нажмите кнопку **Отмена** , чтобы остановить задачу. Обратите внимание, что внешний вид кнопки **Отмена** не меняется сразу же после нажатия. Событие не может произойти, `My.Application.DoEvents` пока инструкция не разрешит обработку событий. `Click`  
  
    > [!NOTE]
    > `My.Application.DoEvents` Метод не обрабатывает события точно так же, как и форма. Например, в этом пошаговом руководстве необходимо дважды нажать кнопку **Отмена** . Чтобы форма могла напрямую управлять событиями, можно использовать многопоточность. Дополнительные сведения см. в разделе [управляемые потоки](../../../../standard/threading/index.md).
  
 Может оказаться полезным запустить программу с помощью F11 и пошаговое выполнение кода. Вы можете ясно видеть `LongTask`, как работает выполнение, а затем ненадолго `Form1` перезапускать каждый раз `PercentDone` при возникновении события.  
  
 Что произойдет, если при обратном выполнении кода `Form1` `LongTask` метод был вызван повторно? В худшем случае может произойти переполнение стека `LongTask` , если вызывалось каждый раз при возникновении события.  
  
 Можно присвоить переменной `mWidget` обработку событий для другого `Widget` объекта, назначив ссылку на новый `Widget` объект в `mWidget`. На самом деле код `Button1_Click` можно сделать при каждом нажатии кнопки.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Для управления событиями для другого мини-приложения  
  
- Добавьте следующую строку кода в `Button1_Click` процедуру, непосредственно перед строкой, которая считывает: `mWidget.LongTask(12.2, 0.33)`  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 Приведенный выше код создает новый `Widget` при каждом нажатии кнопки. Как только `LongTask` метод завершается, ссылка `Widget` на освобождается и `Widget` уничтожается.  
  
 Переменная может содержать только одну ссылку на объект за раз, поэтому при присвоении другому `Widget` объекту `mWidget`значения события предыдущего `Widget` объекта больше не будут обрабатываться. `WithEvents` Если `mWidget` является единственной объектной переменной, содержащей ссылку на старую `Widget`, объект уничтожается. Если требуется обрабатывать события из нескольких `Widget` объектов, `AddHandler` используйте инструкцию для обработки событий из каждого объекта отдельно.  
  
> [!NOTE]
> Можно объявить столько переменных `WithEvents` , сколько требуется, но `WithEvents` массивы переменных не поддерживаются.  
  
## <a name="see-also"></a>См. также

- [Пошаговое руководство: Объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
