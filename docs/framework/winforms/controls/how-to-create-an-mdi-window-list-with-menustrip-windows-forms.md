---
title: Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731011"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip (Windows Forms)
Используйте многодокументный интерфейс (MDI) для создания приложений, которые могут одновременно открывать несколько документов и копировать и вставлять содержимое из одного документа в другой.  
  
 В этой процедуре показано, как создать список всех активных дочерних форм в меню окна родительского элемента.  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>Создание списка окон MDI на MenuStrip  
  
1. Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.  
  
2. Добавьте на форму элемент <xref:System.Windows.Forms.MenuStrip>.  
  
3. Добавьте два пункта меню верхнего уровня в <xref:System.Windows.Forms.MenuStrip> и задайте для их свойств <xref:System.Windows.Forms.Control.Text%2A> значение `&File` и `&Window`.  
  
4. Добавьте пункт подменю в элемент меню `&File` и присвойте его свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Open`.  
  
5. Задайте для свойства <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> <xref:System.Windows.Forms.MenuStrip> значение `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
6. Добавьте форму в проект и добавьте в нее необходимый элемент управления, например другой <xref:System.Windows.Forms.MenuStrip>.  
  
7. Создайте обработчик событий для события <xref:System.Windows.Forms.Control.Click> элемента `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8. В обработчике событий вставьте код, аналогичный приведенному ниже, чтобы создать и отобразить новые экземпляры `Form2` как дочерние элементы MDI `Form1`.  
  
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
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. Поместите код, подобный приведенному ниже, в `&New`<xref:System.Windows.Forms.ToolStripMenuItem> для регистрации обработчика событий.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`;  
  
- элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form1` с именем `menuStrip1` и элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form2` с именем `menuStrip2`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Создание родительских MDI-форм](../advanced/how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних MDI-форм](../advanced/how-to-create-mdi-child-forms.md)
- [Элемент управления MenuStrip](menustrip-control-windows-forms.md)
