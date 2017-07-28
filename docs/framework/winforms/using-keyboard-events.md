---
title: "Using Keyboard Events | Microsoft Docs"
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
  - "KeyPress event"
  - "keyboards, keyboard events"
  - "KeyUp event"
  - "KeyDown event"
  - "keyboard events"
  - "events [Windows Forms], keyboard"
ms.assetid: d3f3e14b-a459-4ee6-9875-8957e34f8ee9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Using Keyboard Events
В большинстве программ Windows Forms для обработки ввода с клавиатуры используются события клавиатуры.  В этом разделе содержится обзор событий клавиатуры, включая сведения об использовании каждого события и данные, которые предоставляются для каждого события.  См. также [Обзор обработчиков событий \(Windows Forms\)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)) и [Общие сведения о событиях \(Windows Forms\)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\))  
  
## События клавиатуры  
 Windows Forms содержит два события, которые возникают при нажатии пользователем клавиши клавиатуры, и одно событие, которое возникает при отпускании пользователем клавиши.  
  
-   Событие <xref:System.Windows.Forms.Control.KeyDown> возникает один раз  
  
-   Событие <xref:System.Windows.Forms.Control.KeyPress>, которое может встречаться несколько раз, если пользователь удерживает нажатую клавишу.  
  
-   Событие <xref:System.Windows.Forms.Control.KeyUp> возникает один раз при отпускании клавиши.  
  
 Когда пользователь нажимает клавишу, Windows Forms определяет, какое событие вызвать в зависимости от того, на что указывает сообщение клавиатуры — на клавишу с символом или на физическую клавишу.  Дополнительные сведения о символьных и физических клавишах см. в разделе [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
 В следующей таблице описаны указанные три метода.  
  
|События клавиатуры|Описание|Результаты|  
|------------------------|--------------|----------------|  
|<xref:System.Windows.Forms.Control.KeyDown>|Это событие возникает, когда пользователь нажимает физическую клавишу.|Обработчик <xref:System.Windows.Forms.Control.KeyDown> получает:<br /><br /> <ul><li>Параметр <xref:System.Windows.Forms.KeyEventArgs>, который предоставляет свойство <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> \(указывающее на физическую клавишу клавиатуры\).</li><li>Свойство <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> \(SHIFT, CTRL или ALT\).</li><li>Свойство <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> \(которое объединяет код клавиши и модификатор\).  Параметр <xref:System.Windows.Forms.KeyEventArgs> также предоставляет:<br /><br /> <ul><li>Свойство <xref:System.Windows.Forms.KeyEventArgs.Handled%2A>, которое может быть задано для предотвращения получения кода клавиши базовым элементом управления.</li><li>Свойство <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A>, которое может использоваться для подавления событий <xref:System.Windows.Forms.Control.KeyPress> и <xref:System.Windows.Forms.Control.KeyUp> для данного нажатия клавиши.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyPress>|Это событие возникает если в результате нажатия клавиши или клавиш получается символ.  Например, пользователь нажимает клавиши SHIFT и строчную "a", в результате получается символ заглавной буквы "A".|<xref:System.Windows.Forms.Control.KeyPress> возникает после <xref:System.Windows.Forms.Control.KeyDown>.<br /><br /> <ul><li>Обработчик <xref:System.Windows.Forms.Control.KeyPress> получает:</li><li>Параметр <xref:System.Windows.Forms.KeyPressEventArgs>, который содержит код символа нажатой клавиши.  Этот код является уникальным для каждой комбинации клавиш символа и модификатора.<br /><br />     Например клавиша "A" создаст<br /><br /> <ul><li>код символа 65, если она нажата при нажатой клавише "SHIFT"</li><li>Или клавиша CAPS LOCK вернет код 97, если она нажата сама по себе,</li><li>И код 1, если она нажата совместно с клавишей CTRL.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyUp>|Это событие возникает, когда пользователь отпускает физическую клавишу.|Обработчик <xref:System.Windows.Forms.Control.KeyUp> получает:<br /><br /> <ul><li>Параметр <xref:System.Windows.Forms.KeyEventArgs>,<br /><br /> <ul><li>который предоставляет свойство <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> \(указывающее на физическую клавишу клавиатуры\).</li><li>Свойство <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> \(SHIFT, CTRL или ALT\).</li><li>Свойство <xref:System.Globalization.SortKey.KeyData%2A> \(которое объединяет код клавиши и модификатор\).</li></ul></li></ul>|  
  
## См. также  
 [Keyboard Input in a Windows Forms Application](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md)   
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)