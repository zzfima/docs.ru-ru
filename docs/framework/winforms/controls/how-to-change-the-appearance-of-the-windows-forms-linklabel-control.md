---
title: "Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms | Microsoft Docs"
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
  - "примеры [Windows Forms], LinkLabel - элемент управления"
  - "LinkLabel - элемент управления [Windows Forms], изменение вида связей"
  - "LinkLabel - элемент управления [Windows Forms], примеры"
  - "свойства LinkLabel"
  - "связи, изменение внешнего вида"
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms
Отображаемый элементом управления <xref:System.Windows.Forms.LinkLabel> текст может быть изменен в соответствии с различными потребностями.  Например, обычно для того, чтобы указать, что по этому тексту можно щелкнуть мышью, его выделяют определенным цветом и подчеркиванием.  После того, как пользователь щелкнет текст, его цвет изменяется на другой.  Управление этим поведением может осуществляться путем задания пяти различных свойств: <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> и <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.  
  
### Изменение внешнего вида элемента управления LinkLabel  
  
1.  Присвойте свойствам <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> и <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> значения, соответствующие нужным цветам.  
  
     Для этого можно использовать программные средства или окно **Свойства** во время разработки.  
  
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
  
2.  Присвойте соответствующее значение заголовка свойству <xref:System.Windows.Forms.LinkLabel.Text%2A>.  
  
     Для этого можно использовать программные средства или окно **Свойства** во время разработки.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  Укажите, какая часть заголовка будет представлена в качестве ссылки, используя свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>.  
  
     Значение <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> представлено объектом <xref:System.Windows.Forms.LinkArea>, включающим два числа: начальную позицию знаков и их количество.  Для этого можно использовать программные средства или окно **Свойства** во время разработки.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  Установите для свойства <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> значение <xref:System.Windows.Forms.LinkBehavior>, <xref:System.Windows.Forms.LinkBehavior> или <xref:System.Windows.Forms.LinkBehavior>.  
  
     Если задано значение <xref:System.Windows.Forms.LinkBehavior>, часть заголовка, определяемая свойством <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, будет выделена подчеркиванием только при установке на ней указателя.  
  
5.  В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked> присвойте свойству <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true`.  
  
     После обращения к данной ссылке ее внешний вид обычно изменяется. Как правило, изменяется ее цвет.  Изменение цвета текста определяется свойством <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>   
 [Общие сведения об элементе управления LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [Практическое руководство. Создание связи с объектом или веб\-страницей с помощью элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [Элемент управления LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)