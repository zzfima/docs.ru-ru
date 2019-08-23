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
ms.openlocfilehash: 37fa897f5a2e1c65cbd5db9189f1500e3427c920
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964310"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Практическое руководство. Определение нажатой управляющей клавиши
При создании приложения, которое принимает нажатия клавиш пользователя, может также потребоваться отслеживать клавиши, такие как SHIFT, ALT и CTRL. При нажатии клавиши-модификатора в сочетании с другими ключами или при нажатии кнопки мыши приложение может отвечать соответствующим образом. Например, если нажата буква S, это может привести к тому, что на экране появится символ "s", но при нажатии клавиш CTRL + S текущий документ может быть сохранен. При обработке <xref:System.Windows.Forms.Control.KeyDown> события <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> свойство объекта, <xref:System.Windows.Forms.KeyEventArgs> полученное обработчиком событий, указывает, какие клавиши модификатора нажаты. Кроме того, <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> свойство объекта <xref:System.Windows.Forms.KeyEventArgs> указывает символ, который был нажат, а также любые клавиши-модификаторы в сочетании с побитовой или. Однако при обработке <xref:System.Windows.Forms.Control.KeyPress> события или события мыши обработчик событий не получает эти сведения. В этом случае необходимо использовать <xref:System.Windows.Forms.Control.ModifierKeys%2A> свойство <xref:System.Windows.Forms.Control> класса. В любом случае необходимо выполнить побитовую операцию и для соответствующего <xref:System.Windows.Forms.Keys> значения и проверяемого значения. <xref:System.Windows.Forms.Keys> Перечисление предлагает варианты каждой клавиши-модификатора, поэтому важно выполнить побитовую операцию и с правильным значением. Например, клавиша SHIFT представлена с помощью <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> и <xref:System.Windows.Forms.Keys.LShiftKey> верное значение для тестирования смены в качестве клавиши-модификатора — <xref:System.Windows.Forms.Keys.Shift>. Аналогичным образом для проверки нажатия клавиш CTRL и Alt в качестве модификаторов <xref:System.Windows.Forms.Keys.Control> следует <xref:System.Windows.Forms.Keys.Alt> использовать значения и соответственно.  
  
> [!NOTE]
> Visual Basic Программисты также могут получить доступ к сведениям о ключах с помощью <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> свойства  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Определение нажатой клавиши Shift  
  
- Используйте побитовый `AND` оператор <xref:System.Windows.Forms.Control.ModifierKeys%2A> со свойством <xref:System.Windows.Forms.Keys> и значением перечисления, чтобы определить, нажата ли определенная клавиша-модификатор. В следующем примере кода показано, как определить, нажата ли клавиша SHIFT в <xref:System.Windows.Forms.Control.KeyPress> обработчике событий.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Ввод с клавиатуры в приложении Windows Forms](keyboard-input-in-a-windows-forms-application.md)
- [Практическое руководство. Определение наличия Капслокк в Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
