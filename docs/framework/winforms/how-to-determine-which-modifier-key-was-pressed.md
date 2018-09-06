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
ms.openlocfilehash: f73dea640bc2059353b2a250188b901f360ea750
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43736235"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Практическое руководство. Определение нажатой управляющей клавиши
При создании приложения, которое принимает нажатия клавиш пользователем, можно также отслеживать за нажатием клавиш клавиши SHIFT, ALT и CTRL. При нажатии в сочетании с другими клавишами или с помощью щелчков мыши, приложение может реагировать соответствующим образом. Например если нажата буквы S, это может просто вызвать «s» для отображения на экране, но при нажатии клавиш CTRL + S, текущий документ может быть сохранен. Если вы обрабатываете <xref:System.Windows.Forms.Control.KeyDown> событий, <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> свойство <xref:System.Windows.Forms.KeyEventArgs> полученных событием обработчик определяет нажатии клавиши-модификаторы. Кроме того <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> свойство <xref:System.Windows.Forms.KeyEventArgs> определяет символ, который также была нажата в сочетании с операцию побитового или любые клавиши-модификаторы. Тем не менее если обрабатывается <xref:System.Windows.Forms.Control.KeyPress> события или события мыши, обработчик событий не получает эти сведения. В этом случае необходимо использовать <xref:System.Windows.Forms.Control.ModifierKeys%2A> свойство <xref:System.Windows.Forms.Control> класса. В любом случае необходимо выполнить операцию побитового и соответствующего <xref:System.Windows.Forms.Keys> значения и значения, вы тестируете. <xref:System.Windows.Forms.Keys> Перечисление предоставляет варианты каждого ключа модификатор, поэтому очень важно выполнить побитового и с правильным значением. Например, клавиша SHIFT представляется <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> и <xref:System.Windows.Forms.Keys.LShiftKey> правильное значение для тестирования является клавиша SHIFT <xref:System.Windows.Forms.Keys.Shift>. Аналогичным образом, для проверки CTLR и ALT качестве модификаторов вы должны использовать <xref:System.Windows.Forms.Keys.Control> и <xref:System.Windows.Forms.Keys.Alt> соответственно.  
  
> [!NOTE]
>  Программистов Visual Basic также доступны сведения о ключе через <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> свойство  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Чтобы определение нажатой управляющей клавиши  
  
-   Используйте побитовый `AND` оператор с <xref:System.Windows.Forms.Control.ModifierKeys%2A> свойство и значение <xref:System.Windows.Forms.Keys> перечисления, чтобы определить, нажата ли клавиша определенного модификатор. В следующем примере кода показано, как определить, нажата ли клавиша SHIFT в <xref:System.Windows.Forms.Control.KeyPress> обработчик событий.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [Ввод с клавиатуры в приложении Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Практическое: определение, если CapsLock в Visual Basic](https://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
