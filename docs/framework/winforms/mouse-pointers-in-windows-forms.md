---
title: "Mouse Pointers in Windows Forms | Microsoft Docs"
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
  - "pointers, setting [Windows Forms]"
  - "mouse pointers"
  - "mouse cursors"
  - "mouse pointers, setting [Windows Forms]"
  - "cursors, setting [Windows Forms]"
  - "mouse, cursors"
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Mouse Pointers in Windows Forms
*Указатель* мыши \(называемый иногда курсором\) — это растровый рисунок, который задает точку фокуса на экране для ввода данных пользователем с помощью мыши.  В этом разделе приведен обзор указателей мыши в формах Windows Forms и описаны некоторые способы изменения указателя мыши и управления им.  
  
## Доступ к указателю мыши  
 Указатель мыши представлен классом <xref:System.Windows.Forms.Cursor>, и каждый класс <xref:System.Windows.Forms.Control> имеет свойство <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName>, определяющее указатель мыши для этого элемента управления.  Класс <xref:System.Windows.Forms.Cursor> содержит свойства, описывающие указатель мыши, например свойства <xref:System.Windows.Forms.Cursor.Position%2A> и <xref:System.Windows.Forms.Cursor.HotSpot%2A>, и методы, которые могут изменить внешний вид указателя, такие как <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A> и <xref:System.Windows.Forms.Cursor.DrawStretched%2A>.  
  
## Управление указателем мыши  
 Иногда может потребоваться ограничить область, в которой может быть использован указатель мыши, или изменить положение указателя.  Можно получить или задать текущее расположение мыши с помощью свойства <xref:System.Windows.Forms.Cursor.Position%2A> класса <xref:System.Windows.Forms.Cursor>.  Кроме того, можно ограничить область, в которой может быть использован указатель мыши, при помощи свойства <xref:System.Windows.Forms.Cursor.Clip%2A>.  Областью отсечения по умолчанию является весь экран.  
  
## Изменение указателя мыши  
 Изменение указателя мыши является важным способом предоставления отклика пользователю.  Например, указатель мыши может быть изменен в обработчиках событий <xref:System.Windows.Forms.Control.MouseEnter> и <xref:System.Windows.Forms.Control.MouseLeave>, чтобы сообщить пользователю о выполнении вычислений и ограничить взаимодействие пользователя с элементом управления.  Иногда указатель мыши изменяется из\-за системных событий, например когда приложение участвует в операции перетаскивания.  
  
 Основным способом изменения указателя мыши является установка для свойства <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName> или <xref:System.Windows.Forms.Control.DefaultCursor%2A> элемента управления нового класса <xref:System.Windows.Forms.Cursor>.  Примеры изменения указателя мыши приведены в примере кода в классе <xref:System.Windows.Forms.Cursor>.  Кроме того, класс <xref:System.Windows.Forms.Cursors> предоставляет набор объектов <xref:System.Windows.Forms.Cursor> для различных типов указателей, таких как указатель в виде руки.  Для отображения указателя ожидания, который приобретает вид песочных часов, когда указатель мыши находится над элементом управления, используется свойство <xref:System.Windows.Forms.Control.UseWaitCursor%2A> класса <xref:System.Windows.Forms.Control>.  
  
## См. также  
 <xref:System.Windows.Forms.Cursor>   
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Drag\-and\-Drop Functionality in Windows Forms](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)