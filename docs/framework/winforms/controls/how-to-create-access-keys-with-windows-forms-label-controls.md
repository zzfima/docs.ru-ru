---
title: "Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms | Microsoft Docs"
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
  - "клавиши доступа, создание для элементов управления"
  - "клавиши доступа, Windows Forms"
  - "элементы управления [Windows Forms], клавиши доступа"
  - "элементы управления диалогового окна, назначенные клавиши"
  - "сочетания клавиш, создание для элементов управления"
  - "Label - элемент управления [Windows Forms], создание сочетаний клавиш"
  - "назначенные клавиши"
  - "назначенные клавиши, добавление элементов управления в диалоговые окна"
  - "UseMnemonic - свойство, Label - элемент управления"
  - "элементы управления Windows Forms, клавиши доступа"
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms
Элементы управления форм Windows Forms <xref:System.Windows.Forms.Label> могут использоваться для определения клавиш быстрого доступа для других элементов управления.  Если в элементе управления "Label" определить клавишу быстрого доступа, пользователь с помощью сочетания клавиши ALT и заданной клавиши может передать фокус следующему в последовательности переходов элементу управления.  Поскольку метки не могут получать фокус, фокус автоматически передается следующему элементу управления в последовательности переходов.  Этот метод используется для присвоения сочетаний клавиш текстовым полям, полям со списком, спискам и наборам записей в табличном виде.  
  
### Чтобы присвоить сочетание клавиш доступа элементу управления с помощью метки  
  
1.  Нарисуйте сначала метку, а затем другой элемент управления.  
  
     \-или\-  
  
     Нарисуйте элементы управления в любом порядке и при свойте для свойства <xref:System.Windows.Forms.Control.TabIndex%2A> метки значение на единицу меньше, чем у другого элемента управления.  
  
2.  Присвойстве свойству метки <xref:System.Windows.Forms.Label.UseMnemonic%2A> значение `true`.  
  
3.  Для присвоения сочетания клавиш для метки используйте амперсанд \(&\) в свойстве <xref:System.Windows.Forms.Label.Text%2A> метки.  Дополнительные сведения содержатся в разделе [Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Может понадобиться отображение амперсандов в элементе управления "Label" вместо использования их для создания клавиш быстрого доступа.  Такое может произойти, если элемент управления "Label" привязан к полю в наборе записей, включающем амперсанды.  Для отображения амперсандов в элементе управления "Label" установите свойству <xref:System.Windows.Forms.Label.UseMnemonic%2A> значение `false`.  Если требуется отобразить амперсанды, и назначить клавишу быстрого доступа, задайте для свойства <xref:System.Windows.Forms.Label.UseMnemonic%2A> значение `true` и укажите клавишу доступа с помощью одного амперсанда \(&\), а отображаемый амперсанд — с помощью двух знаков амперсанда.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## См. также  
 [Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)   
 [Общие сведения об элементе управления Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Элемент управления Label](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)