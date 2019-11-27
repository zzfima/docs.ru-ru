---
title: Обработка событий
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: cb42f2e41e366cf8765cb9395d1a5641434bab40
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345073"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Пошаговое руководство. Обработка событий (Visual Basic)
Это второй из двух разделов, демонстрирующих работу с событиями. В первом разделе [Пошаговое руководство. объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)показано, как объявлять и создавать события. В этом разделе используется форма и класс из этого пошагового руководства, чтобы продемонстрировать, как обрабатывались события, когда они выполняются.  
  
 В примере класса `Widget` используются традиционные инструкции по обработке событий. Visual Basic предоставляет другие методы для работы с событиями. В качестве упражнения можно изменить этот пример, чтобы использовать инструкции `AddHandler` и `Handles`.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Для управления событием PercentDone класса Widget  
  
1. Поместите следующий код в `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     Ключевое слово `WithEvents` указывает, что переменная `mWidget` используется для управления событиями объекта. Тип объекта указывается путем указания имени класса, из которого будет создан объект.  
  
     Переменная `mWidget` объявляется в `Form1`, так как переменные `WithEvents` должны быть уровня класса. Это справедливо независимо от типа класса, в котором они размещены.  
  
     Переменная `mblnCancel` используется для отмены метода `LongTask`.  
  
## <a name="writing-code-to-handle-an-event"></a>Написание кода для обработчика события  
 Как только вы объявили переменную с помощью `WithEvents`, имя переменной отображается в левом раскрывающемся списке **редактора кода**класса. При выборе `mWidget`события класса `Widget` отображаются в правом раскрывающемся списке. При выборе события отображается соответствующая процедура события с префиксом `mWidget` и символом подчеркивания. Всем процедурам события, связанным с переменной `WithEvents`, присваивается имя переменной в виде префикса.  
  
#### <a name="to-handle-an-event"></a>Чтобы обработать событие  
  
1. Выберите `mWidget` из раскрывающегося списка слева в **редакторе кода**.  
  
2. Выберите событие `PercentDone` из раскрывающегося списка справа. **Редактор кода** открывает процедуру `mWidget_PercentDone` события.  
  
    > [!NOTE]
    > **Редактор кода** удобен, но не является обязательным для вставки новых обработчиков событий. В этом пошаговом руководстве более прямым просто скопировать обработчики событий непосредственно в код.  
  
3. Добавьте следующий код в обработчик событий `mWidget_PercentDone` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     При возникновении события `PercentDone` процедура события отображает процент завершения в элементе управления `Label`. Метод `DoEvents` позволяет перекрасить метку, а также дает пользователю возможность нажать кнопку **Отмена** .  
  
4. Добавьте следующий код для обработчика событий `Button2_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Если пользователь нажимает кнопку **Отмена** во время выполнения `LongTask`, событие `Button2_Click` выполняется, как только инструкция `DoEvents` разрешает обработку события. Переменная уровня класса `mblnCancel` имеет значение `True`, а событие `mWidget_PercentDone` проверяет его и задает для аргумента `ByRef Cancel` значение `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Подключение переменной WithEvents к объекту  
 `Form1` теперь настроен на обработку событий объекта `Widget`. Все, что остается, — найти `Widget` где-нибудь.  
  
 При объявлении переменной `WithEvents` во время разработки ни один из объектов не связан с ним. `WithEvents` переменная аналогична любой другой объектной переменной. Необходимо создать объект и присвоить ему ссылку на переменную `WithEvents`.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Создание объекта и присвоение ему ссылки  
  
1. Выберите **(события Form1)** в левом раскрывающемся списке в **редакторе кода**.  
  
2. Выберите событие `Load` из раскрывающегося списка справа. **Редактор кода** открывает процедуру `Form1_Load` события.  
  
3. Добавьте следующий код для процедуры `Form1_Load` события, чтобы создать `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 При выполнении этого кода Visual Basic создает объект `Widget` и подключает его события к процедурам событий, связанным с `mWidget`. С этого момента каждый раз, когда `Widget` вызывает событие `PercentDone`, выполняется процедура `mWidget_PercentDone` события.  
  
#### <a name="to-call-the-longtask-method"></a>Вызов метода LongTask  
  
- Добавьте следующий код в обработчик событий `Button1_Click` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Перед вызовом метода `LongTask`, метка, отображающая процент завершения, должна быть инициализирована, а флаг `Boolean` на уровне класса для отмены метода должен быть установлен в значение `False`.  
  
 `LongTask` вызывается с длительностью задачи в 12,2 секунд. Событие `PercentDone` возникает один раз в секунду. При каждом возникновении события выполняется процедура `mWidget_PercentDone` события.  
  
 Когда `LongTask`, `mblnCancel` тестируется, чтобы узнать, завершился ли `LongTask` в обычном режиме или остановлена, так как для `mblnCancel` было установлено значение `True`. Процент завершения обновляется только в первом случае.  
  
#### <a name="to-run-the-program"></a>Чтобы выполнить программу, выполните следующие действия.  
  
1. Нажмите клавишу F5, чтобы перевести проект в режим выполнения.  
  
2. Нажмите кнопку **запустить задачу** . При каждом возникновении события `PercentDone` метка обновляется в процентах от завершенной задачи.  
  
3. Нажмите кнопку **Отмена** , чтобы остановить задачу. Обратите внимание, что внешний вид кнопки **Отмена** не меняется сразу же после нажатия. Событие `Click` не может произойти, пока инструкция `My.Application.DoEvents` не разрешит обработку событий.  
  
    > [!NOTE]
    > Метод `My.Application.DoEvents` не обрабатывает события точно так же, как и форма. Например, в этом пошаговом руководстве необходимо дважды нажать кнопку **Отмена** . Чтобы форма могла напрямую управлять событиями, можно использовать многопоточность. Дополнительные сведения см. в разделе [управляемые потоки](../../../../standard/threading/index.md).
  
 Может оказаться полезным запустить программу с помощью F11 и пошаговое выполнение кода. Вы можете ясно видеть, как выполнение переходит `LongTask`, а затем ненадолго переводит `Form1` каждый раз при возникновении события `PercentDone`.  
  
 Что произойдет, если при завершении выполнения кода `Form1`метод `LongTask` был вызван повторно? В худшем случае может произойти переполнение стека, если `LongTask` вызывались каждый раз при возникновении события.  
  
 Можно сделать так, чтобы переменная `mWidget` обрабатывала события для другого `Widget` объекта, назначив для `mWidget`ссылку на новую `Widget`. На самом деле можно сделать код в `Button1_Click` делать это при каждом нажатии кнопки.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Для управления событиями для другого мини-приложения  
  
- Добавьте следующую строку кода в процедуру `Button1_Click`, непосредственно перед строкой, считывающей `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 Приведенный выше код создает новый `Widget` каждый раз при нажатии кнопки. После завершения метода `LongTask` ссылка на `Widget` освобождается, а `Widget` уничтожается.  
  
 `WithEvents` переменная может содержать только одну ссылку на объект за раз, поэтому, если вы назначите другой объект `Widget` для `mWidget`, события предыдущего `Widget` объекта больше не будут обрабатываться. Если `mWidget` является единственной объектной переменной, содержащей ссылку на старую `Widget`, объект уничтожается. Если требуется обрабатывать события из нескольких `Widget` объектов, используйте инструкцию `AddHandler` для обработки событий каждого объекта отдельно.  
  
> [!NOTE]
> Можно объявить столько `WithEvents` переменных, сколько требуется, но массивы `WithEvents` переменных не поддерживаются.  
  
## <a name="see-also"></a>См. также

- [Пошаговое руководство. Объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
