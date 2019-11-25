---
title: события
ms.date: 07/20/2015
helpviewer_keywords:
- events [Visual Basic], about events
- events [Visual Basic]
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
ms.openlocfilehash: 666e138a747c480ef9e8b593f8c6233105fcdc93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345122"
---
# <a name="events-visual-basic"></a>События (Visual Basic)
While you might visualize a Visual Studio project as a series of procedures that execute in a sequence, in reality, most programs are event driven—meaning the flow of execution is determined by external occurrences called *events*.  
  
 Событие — это сигнал, который сообщает приложению, что произошло нечто важное. Например, когда пользователь щелкает элемент управления на форме, эта форма инициирует событие `Click` и вызывает процедуру обработки события. События позволяют отдельным задачам взаимодействовать друг с другом. Давайте представим, что приложение выполняет задачу по сортировке в отдельном процессе. Если пользователь отменит эту сортировку, приложение отправит событие отмены, по которому процесс сортировки завершит свою работу.  
  
## <a name="event-terms-and-concepts"></a>Термины и основные понятия для событий  
 This section describes the terms and concepts used with events in Visual Basic.  
  
### <a name="declaring-events"></a>Объявление событий  
 События объявляются внутри классов, структур, модулей и интерфейсов с помощью ключевого слова `Event`, как показано в следующем примере:  
  
 [!code-vb[VbVbalrEvents#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#24)]  
  
### <a name="raising-events"></a>Создание событий  
 Событие действует как сообщение о том, что произошло нечто важное. Рассылка такого сообщения называется *созданием* события. In Visual Basic, you raise events with the `RaiseEvent` statement, as in the following example:  
  
 [!code-vb[VbVbalrEvents#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#25)]  
  
 События должны создаваться в пределах области действия класса, модуля или структуры, в которых они объявлены. Например, производный класс не может создавать события, унаследованные от базового класса.  
  
### <a name="event-senders"></a>Отправители событий  
 Любой объект, способный создать событие, считается *отправителем события* или *источником события*. Например, отправителями событий могут являться формы, элементы управления и пользовательские объекты.  
  
### <a name="event-handlers"></a>Обработчики событий  
 *Обработчики событий* — это процедуры, вызываемые при создании определенного события. В качестве обработчика событий можно использовать любую допустимую подпрограмму с подходящей сигнатурой. Но в качестве обработчика событий нельзя использовать функцию, поскольку она не может возвращать значение источнику события.  
  
 Visual Basic uses a standard naming convention for event handlers that combines the name of the event sender, an underscore, and the name of the event. Например, событие `Click` для кнопки с именем `button1` будет называться `Sub button1_Click`.  
  
> [!NOTE]
> Мы рекомендуем придерживаться этого соглашения об именовании при создании обработчиков событий и для пользовательских событий. Но это не обязательное условие, вы можете использовать любое допустимое имя процедуры.  
  
## <a name="associating-events-with-event-handlers"></a>Связывание событий с обработчиками событий  
 Чтобы обработчик событий мог выполнять свою функцию, его следует связать с соответствующим событием с помощью инструкции `Handles` или `AddHandler`.  
  
### <a name="withevents-and-the-handles-clause"></a>Оператор WithEvents и предложение Handles  
 Инструкция `WithEvents` и предложение `Handles` предоставляют декларативный способ указания обработчиков событий. Если объект объявлен с ключевым словом `WithEvents`, созданные им события могут обрабатываться любой процедурой с инструкцией `Handles` для этого события, как показано в следующем примере:  
  
 [!code-vb[VbVbalrEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#1)]  
  
 Инструкция `WithEvents` и предложение `Handles` часто являются наилучшим решением для обработки событий, так как декларативный синтаксис позволяет легко создавать, читать и отлаживать код программы. Но использование переменных `WithEvents` имеет ряд ограничений.  
  
- Нельзя использовать переменную `WithEvents` в качестве переменной объекта. То есть вы не можете объявить ее как `Object`. При объявлении переменной необходимо указать имя класса.  
  
- Because shared events are not tied to class instances, you cannot use `WithEvents` to declaratively handle shared events. Аналогично, нельзя использовать `WithEvents` или `Handles` для обработки событий от `Structure`. В обоих случаях для обработки таких событий можно использовать инструкцию `AddHandler`.  
  
- Вы не можете создавать массивы переменных типа `WithEvents`.  
  
 Переменные `WithEvents` позволяют одному обработчику событий обрабатывать один или несколько видов событий. Также можно создать несколько обработчиков для одного вида событий.  
  
 Предложение `Handles` является стандартным способом связывания события с обработчиком событий, но оно ограничено тем, что может связывать события с обработчиками событий только во время компиляции.  
  
 In some cases, such as with events associated with forms or controls, Visual Basic automatically stubs out an empty event handler and associates it with an event. For example, when you double-click a command button on a form in design mode, Visual Basic creates an empty event handler and a `WithEvents` variable for the command button, as in the following code:  
  
 [!code-vb[VbVbalrEvents#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#26)]  
  
### <a name="addhandler-and-removehandler"></a>AddHandler и RemoveHandler  
 Инструкция `AddHandler` похожа на предложение `Handles`, поскольку тоже позволяет задавать обработчик событий. Но `AddHandler` в сочетании с `RemoveHandler` обеспечивает большую гибкость, чем предложение `Handles`. Она позволяет динамически добавлять, удалять и изменять обработчики событий, связанные с событием. Если вы хотите обрабатывать общие события или события от структуры, необходимо использовать `AddHandler`.  
  
 `AddHandler` принимает два аргумента: имя события, которое предоставляет отправитель события, например элемент управления, и выражение, определяющее делегат. Класс делегата при использовании `AddHandler` не обязательно указывать явно, поскольку инструкция `AddressOf` всегда возвращает ссылку на делегат. Следующий пример связывает обработчик событий с событием, создаваемым объектом:  
  
 [!code-vb[VbVbalrEvents#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#28)]  
  
 Инструкция `RemoveHandler`, которая отсоединяет событие от обработчика событий, использует такой же синтаксис, как `AddHandler`. Пример:  
  
 [!code-vb[VbVbalrEvents#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#29)]  
  
 В следующем примере обработчик событий связывается с событием, а затем создается событие. Обработчик событий перехватывает это событие и выводит сообщение.  
  
 Затем первый обработчик событий удаляется, а с этим событием связывается другой обработчик событий. Теперь событие создается снова и отображается другое сообщение.  
  
 Наконец, второй обработчик событий удаляется и событие создается в третий раз. Поскольку теперь нет обработчиков событий, связанных с этим событием, никакие действия не выполняются.  
  
 [!code-vb[VbVbalrEvents#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class2.vb#38)]  
  
## <a name="handling-events-inherited-from-a-base-class"></a>Обработка событий, наследуемых от базового класса  
 *Производные классы*, которые наследуют характеристики из базового класса, могут обрабатывать события, создаваемые этим базовым классом, используя инструкцию `Handles MyBase`.  
  
### <a name="to-handle-events-from-a-base-class"></a>Обработка событий из базового класса  
  
- Объявите обработчик событий в производном классе, добавив инструкцию `Handles MyBase.`*eventname* в строку объявления процедуры обработчика событий, где *eventname* — это имя события в базовом классе, которое вы хотите обрабатывать. Пример:  
  
     [!code-vb[VbVbalrEvents#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#12)]  
  
## <a name="related-sections"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Пошаговое руководство. Объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|Предоставляет пошаговую инструкцию для объявления и создания событий класса.|  
|[Пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|Описывает способ создания процедуры обработчика событий.|  
|[Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|Показывает, как определить пользовательское событие, которое позволяет асинхронно вызывать обработчики событий.|  
|[Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|Показывает, как определить пользовательское событие, которое использует память только при обработке события.|  
|[Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|Перечисляет распространенные проблемы, возникающие для обработчиков событий в наследуемых компонентах.|  
|[События](../../../../standard/events/index.md)|Обзор модели событий .NET Framework.|  
|[Создание обработчиков событий в Windows Forms](../../../../framework/winforms/creating-event-handlers-in-windows-forms.md)|Описывает, как работать с событиями, связанными с объектами Windows Forms.|  
|[Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)|Предоставляет обзор делегатов в Visual Basic.|
