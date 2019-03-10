---
title: Практическое руководство. Разделение окна по горизонтали
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: e11e1d6730c6c8c9c0a1ac170aeb5393bf3153b7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708045"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="51e47-102">Практическое руководство. Разделение окна по горизонтали</span><span class="sxs-lookup"><span data-stu-id="51e47-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="51e47-103">В следующем примере кода делает разделитель <xref:System.Windows.Forms.SplitContainer> элемента управления по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="51e47-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51e47-104"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> Свойство <xref:System.Windows.Forms.SplitContainer> управления определяет направление разделителя, а не сам элемент управления.</span><span class="sxs-lookup"><span data-stu-id="51e47-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="51e47-105">Разделение окна по горизонтали</span><span class="sxs-lookup"><span data-stu-id="51e47-105">To split a window horizontally</span></span>  
  
1.  <span data-ttu-id="51e47-106">В рамках процедуры, задать <xref:System.Windows.Forms.SplitContainer.Orientation%2A> свойство <xref:System.Windows.Forms.SplitContainer> управления <xref:System.Windows.Forms.Orientation.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="51e47-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51e47-107">См. также</span><span class="sxs-lookup"><span data-stu-id="51e47-107">See also</span></span>
- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="51e47-108">Элемент управления SplitContainer</span><span class="sxs-lookup"><span data-stu-id="51e47-108">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
