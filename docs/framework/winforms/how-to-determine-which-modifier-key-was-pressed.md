---
title: Практическое руководство. Определение нажатой управляющей клавиши
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 1c89149fc07f89028b21fa513fd84dee4e890968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Практическое руководство. Определение нажатой управляющей клавиши
При создании приложения, которое принимает пользователя нажатия клавиш, можно также для наблюдения за нажатием клавиш SHIFT, ALT и CTRL ключи. При нажатии клавиши-модификатора в сочетании с другими ключами или нажатием кнопки мыши, приложение может реагировать соответствующим образом. Например если нажата буквы S, это может вызвать просто «s» для отображения на экране, но при нажатии клавиш CTRL + S, текущий документ может быть сохранен. При обработке <xref:System.Windows.Forms.Control.KeyDown> событий, <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> свойство <xref:System.Windows.Forms.KeyEventArgs> полученных событием обработчик определяет, при нажатии клавиши-модификаторы. Кроме того <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> свойство <xref:System.Windows.Forms.KeyEventArgs> определяет символ, который в сочетании с побитового или с любыми клавиши-модификаторы также была нажата. Тем не менее если обрабатывается <xref:System.Windows.Forms.Control.KeyPress> событие или событие мыши, обработчик событий не получает эти сведения. В этом случае необходимо использовать <xref:System.Windows.Forms.Control.ModifierKeys%2A> свойство <xref:System.Windows.Forms.Control> класса. В любом случае необходимо выполнить операцию побитового и соответствующего <xref:System.Windows.Forms.Keys> значения и тестировании. <xref:System.Windows.Forms.Keys> Перечисление предоставляет варианты каждого ключа модификатор, поэтому важно выполнения битовой операции и правильное значение. Например, клавиша SHIFT представляется <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> и <xref:System.Windows.Forms.Keys.LShiftKey> правильное значение для тестирования является клавиша SHIFT <xref:System.Windows.Forms.Keys.Shift>. Аналогичным образом, для проверки CTLR и ALT как модификаторы вы должны использовать <xref:System.Windows.Forms.Keys.Control> и <xref:System.Windows.Forms.Keys.Alt> соответственно.  
  
> [!NOTE]
>  Программисты на Visual Basic могут просматривать ключевые данные через <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> свойство  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Для определения нажатой управляющей клавиши  
  
-   Используйте побитовый `AND` оператор с <xref:System.Windows.Forms.Control.ModifierKeys%2A> свойство и значение <xref:System.Windows.Forms.Keys> enumeration, чтобы определить, нажата ли определенной клавиши. В следующем примере кода показано, как определить, является ли нажата клавиша SHIFT, внутри <xref:System.Windows.Forms.Control.KeyPress> обработчика событий.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [Ввод с клавиатуры в приложении Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Как: определить ли CapsLock на Visual Basic](http://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
