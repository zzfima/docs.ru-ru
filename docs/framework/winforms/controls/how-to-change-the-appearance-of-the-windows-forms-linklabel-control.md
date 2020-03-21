---
title: Изменение внешнего вида управления LinkLabel
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
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142134"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms
Вы можете изменить текст, <xref:System.Windows.Forms.LinkLabel> отображаемый элементом управления, в соответствии с различными целями. Например, обычно пользователь указывает, что текст можно нажать, установив текст для отображания определенного цвета с подчеркиванием. После того, как пользователь нажимает на текст, цвет меняется на другой цвет. Чтобы контролировать это поведение, вы можете установить <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>пять <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> различных свойств: <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, и свойства.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>Изменить внешний вид элемента управления LinkLabel  
  
1. Установите <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> и свойства цвета, которые вы хотите.  
  
     Это можно сделать как в программном плане, так и во время проектирования в окне **Свойств.**  
  
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
  
2. Установите <xref:System.Windows.Forms.LinkLabel.Text%2A> свойство на соответствующую подпись.  
  
     Это можно сделать как в программном плане, так и во время проектирования в окне **Свойств.**  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Установите <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойство, чтобы определить, какая часть подписи будет указана в виде ссылки.  
  
     Значение <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> представлено двумя <xref:System.Windows.Forms.LinkArea> числами, положением исходного символа и числом символов. Это можно сделать как в программном плане, так и во время проектирования в окне **Свойств.**  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Установите <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>свойство, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>или .  
  
     Если он установлен <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>на, часть подписи <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> определяется будет только подчеркнута, когда указатель опирается на него.  
  
5. В <xref:System.Windows.Forms.LinkLabel.LinkClicked> обработчике <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> событий `true`установите свойство на .  
  
     Когда ссылка была посещена, это обычная практика, чтобы изменить его внешний вид в некотором роде, как правило, по цвету. Текст будет меняться на цвет, указанный свойством. <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [Общие сведения об элементе управления LinkLabel](linklabel-control-overview-windows-forms.md)
- [Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Элемент управления LinkLabel](linklabel-control-windows-forms.md)
