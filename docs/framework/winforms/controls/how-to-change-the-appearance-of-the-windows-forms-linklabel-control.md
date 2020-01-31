---
title: Изменение внешнего вида элемента управления LinkLabel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: 0b38722fb1647ea215c3bb8978dd3f54b300a0e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746630"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms
Текст, отображаемый элементом управления <xref:System.Windows.Forms.LinkLabel>, можно изменить в соответствии с различными целями. Например, обычно можно указать пользователю на то, что текст может быть щелчком, чтобы текст отображался в определенном цвете с подчеркиванием. После того, как пользователь щелкнет текст, цвет изменится на другой цвет. Для управления этим поведением можно задать пять различных свойств: <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>и <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>Изменение внешнего вида элемента управления LinkLabel  
  
1. Задайте для свойств <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> и <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> нужные цвета.  
  
     Это можно сделать либо программно, либо во время разработки в окне **Свойства** .  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. Задайте для свойства <xref:System.Windows.Forms.LinkLabel.Text%2A> соответствующий заголовок.  
  
     Это можно сделать либо программно, либо во время разработки в окне **Свойства** .  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Задайте свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, чтобы определить, какая часть заголовка будет указана как ссылка.  
  
     <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> значение представляется с <xref:System.Windows.Forms.LinkArea>, содержащим два числа: начальную точку символа и число символов. Это можно сделать либо программно, либо во время разработки в окне **Свойства** .  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Задайте для свойства <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> значение <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>или <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.  
  
     Если задано значение <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, часть заголовка, определяемая <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, будет подчеркнута только при наведении на нее указателя.  
  
5. В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked> задайте для свойства <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true`.  
  
     При посещении ссылки часто бывает проще изменить внешний вид, обычно по цвету. Текст изменится на цвет, указанный в свойстве <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [Общие сведения об элементе управления LinkLabel](linklabel-control-overview-windows-forms.md)
- [Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Элемент управления LinkLabel](linklabel-control-windows-forms.md)
