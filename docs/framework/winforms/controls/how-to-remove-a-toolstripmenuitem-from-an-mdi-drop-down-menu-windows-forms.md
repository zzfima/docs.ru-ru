---
title: Практическое руководство. Удаление элемента ToolStripMenuItem из меню MDI-приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 3198195cf0991734826508aa65818505bf2038c8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735852"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a>Практическое руководство. Удаление элемента ToolStripMenuItem из меню MDI-приложения (Windows Forms)
В некоторых приложениях вид дочернего окна многодокументного интерфейса (MDI) может отличаться от родительского окна MDI. Например, родительским окном MDI может быть электронная таблица, а дочерним окном MDI — диаграмма. В этом случае может потребоваться дополнить содержимое меню родительского окна MDI содержимым меню дочерней MDI-формы, по мере того как активируются дочерние окна MDI различных типов.  
  
 В следующей процедуре используются свойства <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> для удаления пункта меню из раскрывающейся части родительского меню MDI. При закрытии дочернего окна MDI удаленные элементы меню восстанавливаются в родительском меню MDI.  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a>Удаление объекта MenuStrip из раскрывающегося меню MDI  
  
1. Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.  
  
2. Добавьте <xref:System.Windows.Forms.MenuStrip> на `Form1` и присвойте свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> для элемента <xref:System.Windows.Forms.MenuStrip> значение `true`.  
  
3. Добавьте пункт меню верхнего уровня в `Form1`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.Control.Text%2A> значение `&File`.  
  
4. Добавьте три пункта подменю в элемент меню `&File` и задайте для свойств <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Open`, `&Import from`и `E&xit`.  
  
5. Добавьте два пункта подменю в элемент вложенного меню `&Import from` и задайте для свойств <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Word` и `&Excel`.  
  
6. Добавьте в проект форму, добавьте <xref:System.Windows.Forms.MenuStrip> на форму и присвойте его свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> элемента `Form2`<xref:System.Windows.Forms.MenuStrip> значение `true`.  
  
7. Добавьте пункт меню верхнего уровня в `Form2`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&File`.  
  
8. Добавьте элемент подменю `&Import from` в меню `&File` `Form2`и добавьте пункт подменю `&Word` в меню `&File`.  
  
9. Задайте свойства <xref:System.Windows.Forms.MergeAction> и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> пунктов меню `Form2`, как показано в следующей таблице.  
  
    |Пункт меню Form2|Значение Мержеактион|Значение Мержеиндекс|  
    |---------------------|-----------------------|----------------------|  
    |Файл|матчонли|-1|  
    |Импорт из|матчонли|-1|  
    |Word|Удалить|-1|  
  
10. В `Form1`Создайте обработчик событий для <xref:System.Windows.Forms.Control.Click> события `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. В обработчике событий вставьте код, аналогичный следующему примеру кода, чтобы создать и отобразить новые экземпляры `Form2` как дочерние элементы MDI `Form1`:  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
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
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`;  
  
- элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form1` с именем `menuStrip1` и элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form2` с именем `menuStrip2`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Создание родительских MDI-форм](../advanced/how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних MDI-форм](../advanced/how-to-create-mdi-child-forms.md)
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
