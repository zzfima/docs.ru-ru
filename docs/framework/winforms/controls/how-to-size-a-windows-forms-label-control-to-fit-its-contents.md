---
title: "Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms | Microsoft Docs"
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
  - "надписи, установка размеров"
  - "Label - элемент управления [Windows Forms], установка размеров с учетом содержимого"
  - "подписи, установка размеров с учетом содержимого"
  - "размер, элементы управления"
  - "установка размеров элементов управления"
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms
Отображаемый элементом управления форм Windows <xref:System.Windows.Forms.Label> текст надписи может состоять из одной или нескольких строк. Имеется возможность использовать фиксированную длину текста или же автоматически изменять размер надписи в соответствии с длиной текста.  Свойство <xref:System.Windows.Forms.Label.AutoSize%2A> позволяет автоматически изменять размер элементов управления в соответствии с размером надписи; это свойство очень полезно в случае изменения надписи во время выполнения.  
  
### Чтобы размер элемента управления надписи динамически изменялся в соответствии с его содержимым  
  
1.  Установите для свойства <xref:System.Windows.Forms.Label.AutoSize%2A> значение `true`.  
  
 Если для свойства <xref:System.Windows.Forms.Label.AutoSize%2A> установлено значение `false`, слова, указанные в свойстве <xref:System.Windows.Forms.Label.Text%2A> и не помещающиеся на одну строку, будут перемещаться, если это возможно, на другую строку, однако размер элемента управления увеличиваться не будет.  
  
## См. также  
 [Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)   
 [Общие сведения об элементе управления Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Элемент управления Label](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)