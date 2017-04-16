---
title: "Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms | Microsoft Docs"
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
  - "Button - элемент управления [Windows Forms], текст кнопки"
  - "Button - элемент управления [Windows Forms], отображение текста"
  - "кнопки, текст"
  - "надписи, параметр"
  - "надписи, элементы управления Windows Forms"
  - "элементы управления [Windows Forms], надписи"
  - "примеры [Windows Forms], элементы управления"
  - "формы, надписи"
  - "подписи, добавление к элементу управления CommandButton"
  - "объект StdFont и элемент управления CommandButton"
  - "текст"
  - "Text - свойство, элемент управления Windows Forms"
  - "текст, элементы управления Windows Forms"
  - "Windows Forms, надписи"
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms
В элементах управления Windows Forms обычно отображается текст, связанный с их основной функцией.  Например, в элементе управления <xref:System.Windows.Forms.Button> обычно отображается заголовок, указывающий, какое действие выполняется при нажатии кнопки.  С помощью свойства <xref:System.Windows.Forms.Control.Text%2A> можно задавать или получать текст для всех элементов управления.  Шрифт можно менять с помощью свойства <xref:System.Windows.Forms.Control.Font%2A>.  Также с помощью конструктора можно задавать текст.  См. также [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms, с помощью конструктора](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [Практическое руководство. Установка изображения, отображаемого элементом управления Windows Forms, с помощью конструктора](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).  
  
### Программное задание текста, отображаемого элементом управления  
  
1.  Присвойте свойству <xref:System.Windows.Forms.Control.Text%2A> строку.  
  
     Чтобы создать подчеркнутую клавишу доступа, поставьте амперсанд \(&\) перед соответствующей буквой.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.Control.Font%2A> объект типа <xref:System.Drawing.Font>.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp#  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  Для отображения в элементах пользовательского интерфейса, например пунктах меню, специальных символов, которые обычно интерпретируются в них по\-другому, можно использовать escape\-символ.  Например, следующая строка кода задает текст пункта меню & Now For Something Completely Different:  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp#  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=fullName>   
 [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)