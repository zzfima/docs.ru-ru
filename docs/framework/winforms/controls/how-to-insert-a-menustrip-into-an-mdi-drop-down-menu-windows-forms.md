---
title: Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 6e189dd159c48b5779679d0563fab85e9b848992
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736404"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a>Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI (Windows Forms)
В некоторых приложениях вид дочернего окна многодокументного интерфейса (MDI) может отличаться от родительского окна MDI. Например, родительским окном MDI может быть электронная таблица, а дочерним окном MDI — диаграмма. В этом случае может потребоваться дополнить содержимое меню родительского окна MDI содержимым меню дочерней MDI-формы, по мере того как активируются дочерние окна MDI различных типов.  
  
 В следующей процедуре используются свойства <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> для вставки группы пунктов меню из дочернего меню MDI в раскрывающийся список родительского меню MDI. При закрытии дочернего окна MDI элементы вставленного меню удаляются из родительского интерфейса MDI.  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a>Вставка объекта MenuStrip в раскрывающееся меню MDI  
  
1. Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.  
  
2. Добавьте <xref:System.Windows.Forms.MenuStrip> на `Form1` и присвойте свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> для элемента <xref:System.Windows.Forms.MenuStrip> значение `true`.  
  
3. Добавьте пункт меню верхнего уровня в `Form1`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.Control.Text%2A> значение `&File`.  
  
4. Добавьте три пункта подменю в элемент меню `&File` и задайте для свойств <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Open`, `&Import from`и `E&xit`.  
  
5. Добавьте два пункта подменю в элемент вложенного меню `&Import from` и задайте для свойств <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Word` и `&Excel`.  
  
6. Добавьте в проект форму, добавьте <xref:System.Windows.Forms.MenuStrip> на форму и присвойте его свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> элемента `Form2`<xref:System.Windows.Forms.MenuStrip> значение `true`.  
  
7. Добавьте пункт меню верхнего уровня в `Form2`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&File`.  
  
8. Добавьте элементы подменю в меню `&File` `Form2` в следующем порядке: <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`и другой <xref:System.Windows.Forms.ToolStripSeparator>.  
  
9. Задайте свойства <xref:System.Windows.Forms.MergeAction> и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> пунктов меню `Form2`, как показано в следующей таблице.  
  
    |Пункт меню Form2|Значение Мержеактион|Значение Мержеиндекс|  
    |---------------------|-----------------------|----------------------|  
    |File|матчонли|-1|  
    |Separator|Insert|2|  
    |Сохранить|Insert|3|  
    |Сохранить и закрыть|Insert|4|  
    |Separator|Insert|5|  
  
10. Создайте обработчик событий для события <xref:System.Windows.Forms.Control.Click> элемента `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. В обработчик событий вставьте код, аналогичный приведенному в следующем примере для создания и отображения новых экземпляров `Form2` в качестве дочерних окон MDI `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. Поместите код, аналогичный приведенному в следующем примере, в `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>, для регистрации обработчика событий.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`;  
  
- элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form1` с именем `menuStrip1` и элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form2` с именем `menuStrip2`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Создание родительских MDI-форм](../advanced/how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних MDI-форм](../advanced/how-to-create-mdi-child-forms.md)
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
