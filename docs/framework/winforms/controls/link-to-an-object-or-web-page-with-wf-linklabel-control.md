---
title: "Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms | Microsoft Docs"
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
  - "связывание, с другими формами"
  - "LinkLabel - элемент управления [Windows Forms], примеры"
  - "LinkLabel - элемент управления [Windows Forms], связывание со объектом или веб-страницей"
  - "связи, с другими формами"
  - "элемент управления для связи с веб-страницей"
  - "Windows Forms, связывание с объектами"
  - "Windows Forms, создание связи с веб-страницей"
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms
Элемент управления форм Windows Forms <xref:System.Windows.Forms.LinkLabel> позволяет создать в форме ссылки в стиле веб.  При выполнении щелчка на ссылке имеется возможность изменения ее цвета, чтобы указать, что к этой ссылке уже обращались.  Дополнительные сведения об изменении цвета ссылки см. в разделе [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).  
  
## Создание связи с другой формой  
  
#### Создание связи с другой формой с помощью элемента управления LinkLabel  
  
1.  Присвойте соответствующее значение заголовка свойству <xref:System.Windows.Forms.LinkLabel.Text%2A>.  
  
2.  Укажите, какая часть заголовка будет представлена в качестве ссылки, используя свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>.  Представление ссылки зависит от определяющих внешний вид свойств метки ссылки.  Значение <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> представлено объектом <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, включающим два числа: начальную позицию знаков и их количество.  Свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> может быть задано в окне "Свойства" или в коде следующим образом:  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked> вызовите метод <xref:System.Windows.Forms.Form.Show%2A>, чтобы открыть другую форму в проекте, и задайте для свойства <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true`.  
  
    > [!NOTE]
    >  Экземпляр класса <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> переносит ссылку в элемент управления <xref:System.Windows.Forms.LinkLabel>, на котором выполнен щелчок мышью, поэтому не требуется приводить объект `sender` .  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## Создание связи с веб\-страницей  
 Элемент управления <xref:System.Windows.Forms.LinkLabel> также может применяться для отображения веб\-страницы с помощью используемого по умолчанию браузера.  
  
#### Запуск Internet Explorer и создание связи с веб\-страницей с помощью элемента управления LinkLabel  
  
1.  Присвойте соответствующее значение заголовка свойству <xref:System.Windows.Forms.LinkLabel.Text%2A>.  
  
2.  Укажите, какая часть заголовка будет представлена в качестве ссылки, используя свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>.  
  
3.  В блоке обработки исключений обработчика событий <xref:System.Windows.Forms.LinkLabel.LinkClicked> вызовите вторую процедуру, которая задает для свойства <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true` и использует метод <xref:System.Diagnostics.Process.Start%2A> для запуска используемого по умолчанию браузера по URL.  Для использования метода <xref:System.Diagnostics.Process.Start%2A> необходимо добавить ссылку на пространство имен <xref:System.Diagnostics?displayProperty=fullName>.  
  
    > [!IMPORTANT]
    >  Если приведенный ниже код выполняется в среде частичного доверия \(например, на диске c общим доступом\), при вызове метода `VisitLink` произойдет сбой компилятора JIT.  Инструкция`System.Diagnostics.Process.Start` вызывает запрос на ссылку, который не проходит.  Используемый в приведенном ниже фрагменте кода перехват исключения обработчиком catch при вызове метода `VisitLink` гарантирует, что в случае сбоя компилятора JIT ошибка будет постепенно обработана.  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## См. также  
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName>   
 [Общие сведения об элементе управления LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)   
 [Элемент управления LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)