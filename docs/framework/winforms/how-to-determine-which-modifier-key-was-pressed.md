---
title: "How to: Determine Which Modifier Key Was Pressed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "keyboard input"
  - "shift keys"
  - "events [Windows Forms], mouse"
  - "Keys.ControlKey enumeration member"
  - "keys, control keys"
  - "user input, checking for keyboard"
  - "keys, determining last pressed"
  - "keys, shift keys"
  - "keys, modifier keys"
  - "control keys"
  - "keys, alt keys"
  - "alt keys"
  - "Keys.Shift enumeration member"
  - "events [Windows Forms], keyboard"
  - "keyboards, keyboard input"
  - "Keys.Alt enumeration member"
  - "modifier keys"
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Determine Which Modifier Key Was Pressed
При создании приложения, которое должно реагировать на нажатие клавиш, часто бывает необходимо учитывать состояние клавиш CTRL, SHIFT и ALT.  Когда одна из этих клавиш нажата в сочетании с другими клавишами или нажатием кнопки мыши, приложение может реагировать соответствующим образом.  Например, если нажата клавиша с буквой S, это может просто привести к появлению "s" на экране, но при нажатии клавиш CTRL \+ S текущий документ может быть сохранен.  При обработке события <xref:System.Windows.Forms.Control.KeyDown> свойство <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> объекта <xref:System.Windows.Forms.KeyEventArgs>, получаемого обработчиком события, указывает какие из клавиш CTRL, SHIFT и ALT нажаты.  Можно также использовать свойство <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> объекта <xref:System.Windows.Forms.KeyEventArgs>, которое указывает нажатый знак, а также любую из клавиш CTRL, SHIFT и ALT, объединенную с побитовой операцией ИЛИ.  Однако если обрабатывается событие <xref:System.Windows.Forms.Control.KeyPress> или событие мыши, обработчик событий не получает этих сведений.  В этом случае необходимо использовать свойство <xref:System.Windows.Forms.Control.ModifierKeys%2A> класса <xref:System.Windows.Forms.Control>.  В любом случае, необходимо выполнить побитовую операцию И для соответствующего значения <xref:System.Windows.Forms.Keys> и проверяемого значения.  Перечисление <xref:System.Windows.Forms.Keys> предоставляет варианты каждой из клавиш CTRL, SHIFT и ALT, поэтому важно выполнить побитовую операцию И с правильным значением.  Например, клавиша SHIFT представляется значениями <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys> и <xref:System.Windows.Forms.Keys>. Правильным значением для проверки управляющей клавиши SHIFT является <xref:System.Windows.Forms.Keys>.  Аналогичным образом, для проверки клавиш CTLR и ALT следует использовать значения <xref:System.Windows.Forms.Keys> и <xref:System.Windows.Forms.Keys> соответственно.  
  
> [!NOTE]
>  Программистам на Visual Basic также доступны сведения о клавишах доступа через свойство <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>.  
  
### Чтобы определить, какая из клавиш CTRL, SHIFT и ALT нажата, выполните следующие действия.  
  
-   Используйте побитовый оператор `AND` для свойства <xref:System.Windows.Forms.Control.ModifierKeys%2A> и значения перечисления <xref:System.Windows.Forms.Keys>, чтобы определить нажата ли одна из клавиш CTRL, SHIFT и ALT.  В следующем примере кода показано, как определить, нажата ли клавиша SHIFT, внутри обработчика событий <xref:System.Windows.Forms.Control.KeyPress>.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## См. также  
 <xref:System.Windows.Forms.Keys>   
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>   
 [Keyboard Input in a Windows Forms Application](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [How to: Determine If CapsLock is On in Visual Basic](http://msdn.microsoft.com/ru-ru/91e60f5c-dd61-4222-ba5f-39af803afd8c)