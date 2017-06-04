---
title: "Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms | Microsoft Docs"
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
  - "примеры [Windows Forms], текстовые поля"
  - "RichTextBox - элемент управления [Windows Forms], создание связи с веб-страницей"
  - "текстовые поля, отображение веб-ссылок"
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> позволяет выделять веб\-ссылки цветом и подчеркиванием.  Можно написать программу, которая при выборе ссылки будет открывать окно браузера с соответствующим веб\-узлом.  
  
### Чтобы создать ссылку на веб\-страницу с помощью элемента управления RichTextBox  
  
1.  Присвойте свойству <xref:System.Windows.Forms.RichTextBox.Text%2A> строковое значение, включающее допустимый URL\-адрес \(например, http:\/\/www.microsoft.com\/\).  
  
2.  Убедитесь, что свойство <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> имеет значение `true` \(принимается по умолчанию\).  
  
3.  Создает новый глобальный экземпляр объекта <xref:System.Diagnostics.Process>.  
  
4.  Напишите обработчик событий <xref:System.Windows.Forms.RichTextBox.LinkClicked>, который передает нужный текст в программу браузера.  
  
     В приведенном ниже примере событие <xref:System.Windows.Forms.RichTextBox.LinkClicked> открывает экземпляр Internet Explorer на странице, URL\-адрес которой задан в свойстве <xref:System.Windows.Forms.RichTextBox.Text%2A> элемента управления <xref:System.Windows.Forms.RichTextBox>.  В этом примере предполагается, что существует форма с элементом управления <xref:System.Windows.Forms.RichTextBox>.  
  
    > [!IMPORTANT]
    >  При вызове метода <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName> возникнет исключение <xref:System.Security.SecurityException>, вызванное недостаточными правами, если код выполняется в контексте с частичным доверием.  Дополнительные сведения см. в разделе [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
    ```vb  
    Public p As New System.Diagnostics.Process  
    Private Sub RichTextBox1_LinkClicked _  
       (ByVal sender As Object, ByVal e As _  
       System.Windows.Forms.LinkClickedEventArgs) _  
       Handles RichTextBox1.LinkClicked  
          ' Call Process.Start method to open a browser  
          ' with link text as URL.  
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)  
    End Sub  
  
    ```  
  
    ```csharp  
    public System.Diagnostics.Process p = new System.Diagnostics.Process();  
  
    private void richTextBox1_LinkClicked(object sender,   
    System.Windows.Forms.LinkClickedEventArgs e)  
    {  
       // Call Process.Start method to open a browser  
       // with link text as URL.  
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);  
    }  
  
    ```  
  
    ```cpp  
    public:  
       System::Diagnostics::Process ^ p;  
  
    private:  
       void richTextBox1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkClickedEventArgs ^  e)  
       {  
          // Call Process.Start method to open a browser  
          // with link text as URL.  
          p = System::Diagnostics::Process::Start("IExplore.exe",  
             e->LinkText);  
       }  
    ```  
  
     \([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Необходимо инициализировать процесс`p`, для чего достаточно включить в конструктор формы следующую инструкцию:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.richTextBox1.LinkClicked += new   
       System.Windows.Forms.LinkClickedEventHandler  
       (this.richTextBox1_LinkClicked);  
  
    ```  
  
    ```cpp  
    this->richTextBox1->LinkClicked += gcnew  
       System::Windows::Forms::LinkClickedEventHandler  
       (this, &Form1::richTextBox1_LinkClicked);  
    ```  
  
     По окончании работы с созданным процессом его необходимо немедленно остановить.  В рассматриваемом примере для этого достаточно добавить в программу следующий код:  
  
    ```vb  
    Public Sub StopWebProcess()  
       p.Kill()  
    End Sub  
  
    ```  
  
    ```csharp  
    public void StopWebProcess()  
    {  
       p.Kill();  
    }  
  
    ```  
  
    ```cpp  
    public: void StopWebProcess()  
    {  
       p->Kill();  
    }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>   
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>   
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)