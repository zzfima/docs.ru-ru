---
title: "Практическое руководство. Разделение окна по горизонтали | Microsoft Docs"
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
  - "SplitContainer - элемент управления [Windows Forms], горизонтальный разделитель"
  - "окна разделителей, изменение ориентации разделителя"
  - "окна разделителей, горизонтально"
  - "окна, горизонтальное разделение"
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Разделение окна по горизонтали
В следующем примере разделитель элемента управления <xref:System.Windows.Forms.SplitContainer> становится горизонтальным.  
  
> [!NOTE]
>  Свойство <xref:System.Windows.Forms.SplitContainer.Orientation%2A> элемента управления <xref:System.Windows.Forms.SplitContainer> определяет направление разделителя, а не самого элемента управления.  
  
### Разделение окна по горизонтали  
  
1.  Внутри процедуры присвойте свойству <xref:System.Windows.Forms.SplitContainer.Orientation%2A> элемента управления <xref:System.Windows.Forms.SplitContainer> значение <xref:System.Windows.Forms.Orientation>.  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.SplitContainer>   
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)