---
title: "Практическое руководство. Удаление элемента ToolStripMenuItem из меню MDI-приложения (Windows Forms) | Microsoft Docs"
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
  - "MDI - интерфейс, объединение пунктов меню"
  - "пункты меню, удаление из раскрывающихся меню MDI"
  - "MenuStrip - элемент управления [Windows Forms], слияние"
  - "MenuStrip - элемент управления [Windows Forms], удаление"
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Удаление элемента ToolStripMenuItem из меню MDI-приложения (Windows Forms)
В некоторых приложениях вид дочернего окна интерфейса MDI может отличаться от родительского окна MDI.  Например, если родительский интерфейс MDI — таблица, то дочерний интерфейс MDI может быть диаграммой.  В этом случае может потребоваться обновление содержимого меню родительского интерфейса MDI содержимым меню дочернего интерфейса MDI при активировании различных видов дочерних окон интерфейса MDI.  
  
 В следующей процедуре свойства <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> используются для удаления пункта меню из раскрывающейся части родительского меню MDI.  При закрытии дочернего окна MDI происходит восстановление удаленных пунктов меню в родительском меню MDI.  
  
### Чтобы удалить объект MenuStrip из раскрывающегося меню MDI, выполните следующие действия:  
  
1.  Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.  
  
2.  Добавьте <xref:System.Windows.Forms.MenuStrip> в `Form1` и присвойте свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> компонента <xref:System.Windows.Forms.MenuStrip> значение `true`.  
  
3.  Добавьте пункт меню верхнего уровня в `Form1`<xref:System.Windows.Forms.MenuStrip> установите его и  <xref:System.Windows.Forms.Control.Text%2A> свойство  `&File`.  
  
4.  Добавьте три пункта подменю в пункт меню `&File` и присвойте их свойствам <xref:System.Windows.Forms.ToolStripItem.Text%2A> значения `&Open`, `&Import from` и `E&xit`.  
  
5.  Добавьте два пункта подменю в пункт подменю `&Import from` и присвойте их свойствам <xref:System.Windows.Forms.ToolStripItem.Text%2A> значения `&Word` и `&Excel`.  
  
6.  Добавьте форму, добавьте к проекту a <xref:System.Windows.Forms.MenuStrip> в форму и установите  <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> свойство   `Form2`<xref:System.Windows.Forms.MenuStrip> В  `true`.  
  
7.  Добавьте пункт меню верхнего уровня в `Form2`<xref:System.Windows.Forms.MenuStrip> установите его и  <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойство  `&File`.  
  
8.  Добавьте пункт подменю `&Import from` в меню `&File` формы `Form2` и добавьте пункт подменю `&Word` в меню `&File`.  
  
9. Задайте свойства <xref:System.Windows.Forms.MergeAction> и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> пунктов меню `Form2` в соответствии со следующей таблицей.  
  
    |Пункт меню Form2|Значение MergeAction|Значение MergeIndex|  
    |----------------------|--------------------------|-------------------------|  
    |Файл|MatchOnly|\-1|  
    |Import from|MatchOnly|\-1|  
    |Word|Удалить|\-1|  
  
10. IN `Form1`создайте обработчик событий для события  <xref:System.Windows.Forms.Control.Click> событие   `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. В обработчик событий вставьте код, аналогичный следующему примеру кода, для создания и отображения новых экземпляров формы `Form2` как дочерних форм MDI формы `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
  
    ```  
  
     \[C\#\]  
  
    ```  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
12. Поместите код, аналогичный следующему примеру кода `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> зарегистрировать обработчик событий.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
  
    ```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`.  
  
-   Элемент управления <xref:System.Windows.Forms.MenuStrip> в форме `Form1` с именем `menuStrip1`, и элемент управления <xref:System.Windows.Forms.MenuStrip> в форме `Form2` с именем `menuStrip2`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)