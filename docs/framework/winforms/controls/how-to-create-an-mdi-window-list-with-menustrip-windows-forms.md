---
title: "Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip (Windows Forms) | Microsoft Docs"
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
  - "MDI - интерфейс, создание списка окон"
  - "MenuStrip - элемент управления [Windows Forms], создание списка окон"
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip (Windows Forms)
Для создания приложений, которые могут одновременно открывать несколько документов, а также копировать содержимое из одного документа и вставлять в другой, используется интерфейс MDI.  
  
 Эта процедура показывает, как создать список всех активных дочерних форм на меню родительского окна.  
  
### Чтобы создать список окон MDI для объекта MenuStrip, выполните следующие действия.  
  
1.  Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.  
  
2.  Добавьте элемент <xref:System.Windows.Forms.MenuStrip> в форму.  
  
3.  Добавьте два пункта меню верхнего уровня в элемент <xref:System.Windows.Forms.MenuStrip> и присвойте его свойствам <xref:System.Windows.Forms.Control.Text%2A> значения `&File` и `&Window` .  
  
4.  Добавьте пункт подменю в пункт меню `&File` и присвойте его свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Open`.  
  
5.  Установка <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> свойство   <xref:System.Windows.Forms.MenuStrip> к  `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
6.  Добавьте в проект форму, а в форму — требуемые элементы управления, такие как другой <xref:System.Windows.Forms.MenuStrip>.  
  
7.  Создайте обработчик событий для события <xref:System.Windows.Forms.Control.Click> событие   `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8.  В обработчик событий вставьте код, аналогичный следующему, для создания и отображения новых экземпляров формы `Form2` как дочерних MDI\-форм формы `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
  
    ```  
  
     \[C\#\]  
  
    ```  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
9. Код размещения в like `&New`<xref:System.Windows.Forms.ToolStripMenuItem> зарегистрировать обработчик событий.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
  
    ```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`.  
  
-   Элемент управления <xref:System.Windows.Forms.MenuStrip> в форме `Form1` с именем `menuStrip1`, и элемент управления <xref:System.Windows.Forms.MenuStrip> в форме `Form2` с именем `menuStrip2`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)