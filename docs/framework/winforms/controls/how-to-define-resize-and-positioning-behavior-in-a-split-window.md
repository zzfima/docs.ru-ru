---
title: "Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем | Microsoft Docs"
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
  - "разделенные окна, изменение размеров"
  - "SplitContainer - элемент управления [Windows Forms], изменение размеров"
  - "окна разделителей, изменение размеров"
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем
Панели элемента управления <xref:System.Windows.Forms.SplitContainer> легко поддаются изменению размеров и управлению пользователем.  Однако могут возникнуть случаи, когда разделителем необходимо управлять программными средствами, то есть определять его положение и степень перемещения.  
  
 Свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> и другие свойства элемента управления <xref:System.Windows.Forms.SplitContainer> позволяют точно контролировать поведение пользовательского интерфейса в зависимости от потребностей.  Эти свойства перечислены в следующей таблице.  
  
|Имя|Описание|  
|---------|--------------|  
|Свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Определяет возможность перемещения разделителя при помощи клавиатуры или мыши.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Определяет расстояние от левой или верхней границы до перемещаемой полосы\-разделителя в пикселях.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Определяет минимальное расстояние, на которое разделитель может быть перемещен пользователем, в пикселях.|  
  
 Следующий пример изменяет свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> для создания эффекта "прыгающего разделителя" – когда пользователь перетаскивает разделитель, прибавляется по 10 пикселей вместо 1 по умолчанию.  
  
### Определение поведения изменения размера SplitContainer  
  
1.  В процедуре укажите для свойства <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> желаемый размер, чтобы достичь "скачкообразного" поведения разделителя.  
  
     В следующем примере кода в событии формы <xref:System.Windows.Forms.Form.Load> разделитель в элементе управления <xref:System.Windows.Forms.SplitContainer> будет прыгать через 10 пикселей при перетаскивании.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Плавное перемещение разделителя влево или вправо не даст ощутимого эффекта; однако при переходе указателя на 10 пикселей в любом направлении разделитель будет перепрыгивать в новое положение.  
  
## См. также  
 <xref:System.Windows.Forms.SplitContainer>   
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>