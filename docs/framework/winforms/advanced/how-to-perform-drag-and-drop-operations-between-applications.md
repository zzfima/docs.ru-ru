---
title: "How to: Perform Drag-and-Drop Operations Between Applications | Microsoft Docs"
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
  - "drag and drop, between applications"
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Perform Drag-and-Drop Operations Between Applications
Выполнение операций перетаскивания между приложениями не отличается от реализации этой операции внутри приложения до тех пор, пока поведение участвующих приложений соответствует "контракту" между свойствами <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> и <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
 В следующей процедуре будет использоваться созданное вами приложение Windows и текстовый редактора WordPad, который входит в состав операционной системы Windows, для выполнения операций перетаскивания между приложениями.  WordPad имеет определенный набор допустимых действий для перетаскивания текста; приложение Windows, для которого будет написан код, будет использовать эти действия для успешного завершения операции перетаскивания.  
  
### Выполнение операции перетаскивания между приложениями  
  
1.  Создайте новое приложение Windows Forms.  
  
2.  Добавьте элемент управления <xref:System.Windows.Forms.TextBox> в форму.  
  
3.  Настройте элемент управления <xref:System.Windows.Forms.TextBox> для получения перетаскиваемых данных.  
  
     Дополнительные сведения см. в разделе [Пример. Выполнение операции перетаскивания в Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
4.  Запустите приложение Windows и во время выполнения приложения запустите WordPad.  
  
     WordPad — это текстовый редактор, установленный операционной системой Windows, который позволяет выполнять операции перетаскивания.  Чтобы открыть его, нажмите кнопку **Пуск**, выберите пункт **Выполнить** и введите `WordPad` в текстовом поле диалогового окна **Выполнить**, затем нажмите **ОК**.  
  
5.  После открытия WordPad введите в нем строку текста.  
  
6.  Используя мышь, выделите текст и перетащите выделенный текст на элемент управления <xref:System.Windows.Forms.TextBox> в приложение Windows.  
  
     Обратите внимание, что, когда указатель мыши находится над элементом управления <xref:System.Windows.Forms.TextBox>, \(и, следовательно, инициируется событие <xref:System.Windows.Forms.Control.DragEnter>\), курсор изменяется и можно отпустить выделенный текст на элемент управления <xref:System.Windows.Forms.TextBox>.  
  
     Кроме того, можно настроить элемент управления <xref:System.Windows.Forms.TextBox> так, чтобы можно было перетаскивать текстовые строки в WordPad.  Дополнительные сведения см. в разделе [Walkthrough: Performing a Drag\-and\-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
## См. также  
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)