---
title: Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 015e93fb551b8d48b8a57662b8def61c3cb46c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем
Панели элемента <xref:System.Windows.Forms.SplitContainer> управления поддаются, размеров и управлению пользователями. Однако будет время, если требуется программно управлять разделителем, где он расположен и определить, каким образом можно переместить.  
  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> И других свойствах на <xref:System.Windows.Forms.SplitContainer> управления позволяют точно контролировать поведение пользовательского интерфейса в соответствии с потребностями. Эти свойства перечислены в следующей таблице.  
  
|name|Описание|  
|----------|-----------------|  
|Свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Определяет, является ли разделитель при помощи клавиатуры или мыши.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Определяет расстояние в пикселях от левой или верхней границы для перемещаемой полосы-разделителя.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Определяет минимальное расстояние в пикселях, что разделитель может быть перемещен пользователем.|  
  
 Следующий пример изменяет <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> свойство для создания эффекта «привязка разделитель»; когда пользователь перетаскивает разделитель, увеличивается в единицах 10 точек, а не значение по умолчанию 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>Чтобы определить режим изменения размера SplitContainer  
  
1.  В процедуре, задайте <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> свойство до нужного размера, чтобы достичь поведение разделителя «привязка».  
  
     В следующем примере кода в форме <xref:System.Windows.Forms.Form.Load> событий, разделителя в <xref:System.Windows.Forms.SplitContainer> перехода 10 пикселей при перетаскивании элемента управления имеет значение.  
  
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
  
     (Visual C#) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Плавное перемещение разделителя влево или вправо не будет действовать ощутимого; Тем не менее когда указатель мыши выходит 10 точек в любом направлении, разделитель будет привязана к новой позиции.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
