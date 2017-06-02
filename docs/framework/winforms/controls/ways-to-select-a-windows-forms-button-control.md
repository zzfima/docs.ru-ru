---
title: "Способы активации элемента управления Button в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Button - элемент управления [Windows Forms], выбор"
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Способы активации элемента управления Button в Windows Forms
Кнопку Windows Forms можно активировать одним из следующих способов.  
  
-   Щелкните кнопку мышью.  
  
-   Вызовите событие <xref:System.Windows.Forms.Control.Click> для этой кнопки в коде.  
  
-   Передайте фокус кнопке с помощью клавиши TAB и активируйте кнопку, нажав клавишу ПРОБЕЛ или ВВОД.  
  
-   Нажмите клавиши доступа \(ALT \+ подчеркнутая буква\) для этой кнопки.  Дополнительные сведения о клавишах быстрого доступа см. в разделе [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Если кнопка на форме используется для подтверждения, она активируется при нажатии клавиши ВВОД, даже если в фокусе находится другой элемент управления формы, за исключением тех случаев, когда этот элемент управления также является кнопкой, многострочным текстовым полем или пользовательским элементом управления, перехватывающим нажатия клавиши ввода.  
  
-   Если кнопка на форме используется для отмены, она активируется при нажатии клавиши ESC, даже если фокус находится на другом элементе управления.  
  
-   Вызовите метод <xref:System.Windows.Forms.Button.PerformClick%2A>, чтобы активировать кнопку программными средствами.  
  
## См. также  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)