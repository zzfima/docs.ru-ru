---
title: Принцип работы ввод с клавиатуры
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: 369c434f5443334ccb8b136ce50ff2d5db8ece01
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963449"
---
# <a name="how-keyboard-input-works"></a>Принцип работы ввод с клавиатуры
Ввод с клавиатуры обрабатывается в Windows Forms посредством вызова событий клавиатуры в ответ на сообщения Windows. В большинстве приложений Windows Forms для обработки ввода с клавиатуры используются только события клавиатуры. Тем не менее, чтобы реализовать более сложные сценарии ввода с клавиатуры, например перехват клавиш до того, как они достигнут элемента управления, необходимо понимать, как работают сообщения клавиатуры. В этом разделе описываются типы данных ключа, распознаваемых приложением Windows Forms, и приводятся общие сведения о маршрутизацией сообщений клавиатуры. Сведения о событиях клавиатуры см. в разделе [Использование событий клавиатуры](using-keyboard-events.md).  
  
## <a name="types-of-keys"></a>Типы ключей  
 Windows Forms определяет ввод с клавиатуры как коды виртуальных клавиш, представленные побитовым <xref:System.Windows.Forms.Keys> перечислением. С помощью <xref:System.Windows.Forms.Keys> перечисления можно объединить ряд нажатых клавиш, чтобы получить одно значение. Эти значения соответствуют значениям, сопровождающим сообщения Windows WM_KEYDOWN и WM_SYSKEYDOWN. Большинство физических нажатий клавиш можно обнаружить, обрабатывая <xref:System.Windows.Forms.Control.KeyDown> события или. <xref:System.Windows.Forms.Control.KeyUp> Символьные ключи являются подмножеством <xref:System.Windows.Forms.Keys> перечисления и соответствуют значениям, сопровождающим сообщения Windows WM_CHAR и WM_SYSCHAR. Если сочетание нажатых клавиш приводит к вводу символа, можно обнаружить символ, обрабатывая <xref:System.Windows.Forms.Control.KeyPress> событие. Кроме того, можно использовать <xref:Microsoft.VisualBasic.Devices.Keyboard>, предоставляемый программным интерфейсом Visual Basic, чтобы узнать, какие ключи были нажаты, и отправить ключи. Дополнительные сведения см. в разделе [Доступ к клавиатуре](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md).  
  
## <a name="order-of-keyboard-events"></a>Порядок событий клавиатуры  
 Как было показано ранее, в элементе управления могут возникать 3 связанных с клавиатурой события. Общий порядок событий показывает следующая последовательность:  
  
1. Пользователь отправляет ключ "a", этот ключ предварительно обрабатывается, отправляется и <xref:System.Windows.Forms.Control.KeyDown> возникает событие.  
  
2. Пользователь содержит ключ "a", этот ключ предварительно обработан, подготовлен к <xref:System.Windows.Forms.Control.KeyPress> отправке, и возникает событие.  
  
     Пока пользователь удерживает нажатой данную клавишу, это событие возникает несколько раз.  
  
3. Пользователь отпускает клавишу "a", ключ предварительно обрабатывается, отправляется и <xref:System.Windows.Forms.Control.KeyUp> возникает событие.  
  
## <a name="preprocessing-keys"></a>Предварительная обработка сообщений клавиатуры  
 Как и другие сообщения, сообщения клавиатуры обрабатываются <xref:System.Windows.Forms.Control.WndProc%2A> в методе формы или элемента управления. Однако перед обработкой <xref:System.Windows.Forms.Control.PreProcessMessage%2A> сообщений клавиатуры метод вызывает один или несколько методов, которые могут быть переопределены для обработки специальных символьных ключей и физических ключей. Эти методы можно переопределить для обнаружения и фильтрации определенных клавиш перед обработкой сообщения элементом управления. В следующей таблице показаны выполняемые действия и связанные методы в порядке их осуществления.  
  
### <a name="preprocessing-for-a-keydown-event"></a>Предварительная обработка события KeyDown  
  
|Действие|Связанный метод|Примечания|  
|------------|--------------------|-----------|  
|Проверка клавиши для команд, например ярлыка для сочетаний клавиш или меню.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Этот метод обрабатывает клавишу для команд, которая имеет приоритет над обычными клавишами. Если этот метод возвращает `true`, сообщение о нажатии клавиши не отправляется, и событие клавиши не возникает. Если возвращается `false`, <xref:System.Windows.Forms.Control.IsInputKey%2A> вызывается метод`.`|  
|Проверьте наличие специального ключа, требующего предварительной обработки, или обычного ключа символа, который должен вызывать <xref:System.Windows.Forms.Control.KeyDown> событие и быть отправлен в элемент управления.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Если метод возвращает `true`значение, это означает, что элемент управления является обычным символом <xref:System.Windows.Forms.Control.KeyDown> и возникает событие. Если `false`задано значение, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> вызывается. **Примечание.**  Чтобы убедиться, что элемент управления получает ключ или сочетание клавиш, <xref:System.Windows.Forms.Control.PreviewKeyDown> можно обменять событие и задать <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> <xref:System.Windows.Forms.PreviewKeyDownEventArgs> `true` для ключа или ключей.|  
|Проверка клавиши навигации (ESC, TAB, ВВОД или клавиши со стрелками).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Этот метод обрабатывает физическую клавишу со специальными функциональными возможностями в элементе управления, например переключение фокуса между элементом управления и его родительским объектом. Если элемент управления интерпретации не обрабатывает ключ, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> вызывается в родительском элементе управления и так далее в самом верхнем элементе управления в иерархии. Если этот метод возвращает `true`, предварительная обработка завершается, и событие клавиатуры не возникает. Если возвращается `false` <xref:System.Windows.Forms.Control.KeyDown> , возникает событие.|  
  
### <a name="preprocessing-for-a-keypress-event"></a>Предварительная обработка события KeyPress  
  
|Действие|Связанный метод|Примечания|  
|------------|--------------------|-----------|  
|Убедитесь, что клавиша является обычным символом, который должен быть обработан элементом управления|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Если символ является обычным символом, этот метод возвращает `true`значение <xref:System.Windows.Forms.Control.KeyPress> , событие вызывается и дальнейшая Предварительная обработка не выполняется. В <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> противном случае будет вызван.|  
|Проверьте, не является ли символ назначенной клавишей (например, &OK на кнопке)|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Этот метод, аналогичный <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>, будет вызываться в иерархии элементов управления. Если элемент управления является контейнерным, он проверяет наличие назначенных клавиш, вызывая <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> сам себя и его дочерние элементы управления. Если <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> возвращает `true` ,<xref:System.Windows.Forms.Control.KeyPress> событие не происходит.|  
  
## <a name="processing-keyboard-messages"></a>Обработка сообщений клавиатуры  
 После того как сообщения клавиатуры <xref:System.Windows.Forms.Control.WndProc%2A> становятся доступны методу формы или элемента управления, они обрабатываются набором методов, которые могут быть переопределены. Каждый из этих методов возвращает <xref:System.Boolean> значение, указывающее, было ли сообщение клавиатуры обработано и использовано элементом управления. Если один из методов возвращает `true`, сообщение считается обработанным и не передается в базовый или родительский объект элемента управления для дальнейшей обработки. В противном случае сообщение остается в очереди сообщений и может быть обработано в другом методе в базовом или родительском объекте элемента управления. В следующей таблице представлены методы, обеспечивающие обработку сообщений клавиатуры.  
  
|Метод|Примечания|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Этот метод обрабатывает все сообщения клавиатуры, полученные <xref:System.Windows.Forms.Control.WndProc%2A> методом элемента управления.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Этот метод отправляет сообщение клавиатуры в родительский объект элемента управления. Если <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> возвращает `true`значение, событие Key не создается, в противном случае вызывается.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|При необходимости этот метод <xref:System.Windows.Forms.Control.KeyDown>вызывает <xref:System.Windows.Forms.Control.KeyPress>события, <xref:System.Windows.Forms.Control.KeyUp> и.|  
  
## <a name="overriding-keyboard-methods"></a>Переопределение методов клавиатуры  
 Существует множество методов переопределения, когда выполняется предварительная и основная обработка сообщений клавиатуры. Тем не менее некоторые методы отличаются большим удобством. В таблице ниже приведены задачи, которые может быть необходимо выполнить, и оптимальные способы переопределения методов для сообщений клавиатуры. Дополнительные сведения о переопределении методов см. [в разделе Переопределение свойств и методов в производных классах](../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes).  
  
|Задача|Метод|  
|----------|------------|  
|Перехватывает клавишу навигации и создает <xref:System.Windows.Forms.Control.KeyDown> событие. Например, в текстовом поле необходимо обработать клавиши TAB и Return.|Переопределите метод <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Примечание.**  Кроме того, <xref:System.Windows.Forms.Control.PreviewKeyDown> можно обменять событие и задать <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> <xref:System.Windows.Forms.PreviewKeyDownEventArgs> `true` для параметра значение для требуемого ключа или ключей.|  
|Выполнение специальной обработки ввода или навигации в элементе управления. Например, необходимо использовать клавиши со стрелками в элементе управления "Список", чтобы изменить выбранный элемент.|Переопределите метод <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>.|  
|Перехватывает клавишу навигации и создает <xref:System.Windows.Forms.Control.KeyPress> событие. Например, в элементе управления регулятора требуется выполнение нескольких нажатий клавиши со стрелкой для ускорения перехода между элементами.|Переопределите метод <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Выполнение специального ввода или обработки навигации во время <xref:System.Windows.Forms.Control.KeyPress> события. Например, в элементе управления "Список" при удержании нажатой клавиши "r" следует переходить между элементами, которые начинаются с буквы "r".|Переопределите метод <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>.|  
|Выполнение обработки пользовательских назначенных клавиш. Например, необходимо обрабатывать назначенные клавиши на кнопках, нарисованных владельцем, содержащихся на панели инструментов.|Переопределите метод <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [Объект My.Computer.Keyboard](../../visual-basic/language-reference/objects/my-computer-keyboard-object.md)
- [Доступ к клавиатуре](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md)
- [Использование событий клавиатуры](using-keyboard-events.md)
