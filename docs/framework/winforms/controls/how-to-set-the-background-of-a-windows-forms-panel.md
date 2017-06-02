---
title: "Практическое руководство. Установка фона панели Windows Forms | Microsoft Docs"
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
  - "цвета фона, элементы управления панели [Windows Forms]"
  - "фоновые изображения, элементы управления панели [Windows Forms]"
  - "цвета, элементы управления панели [Windows Forms]"
  - "Panel - элемент управления [Windows Forms], фон"
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Установка фона панели Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.Panel> может отображать как цвет фона, так и фоновое изображение.  Свойство <xref:System.Windows.Forms.Control.BackColor%2A> задает цвет фона для представленных в панели элементов управления, таких как метки и переключатели.  Если свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> не задано, выбранный <xref:System.Windows.Forms.Control.BackColor%2A> заполняет панель полностью.  Если свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> задано, за присутствующими в панели элементами управления будет отображено указанное изображение.  
  
### Чтобы задать фон программными средствами  
  
1.  Задайте для свойства панели <xref:System.Windows.Forms.Control.BackColor%2A> значение типа <xref:System.Drawing.Color?displayProperty=fullName>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  Задайте свойство панели <xref:System.Windows.Forms.Control.BackgroundImage%2A>, используя метод <xref:System.Drawing.Image.FromFile%2A> класса <xref:System.Drawing.Image?displayProperty=fullName>.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Элемент управления Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)