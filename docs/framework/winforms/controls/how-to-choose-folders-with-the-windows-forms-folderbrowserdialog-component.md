---
title: Выбор папок с помощью компонента FolderBrowserDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 313388442101f341cfed366143f3c9669fb45cbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742226"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms

Часто в создаваемых приложениях Windows требуется предлагать пользователю выбрать папку, как правило, для сохранения набора файлов. Компонент <xref:System.Windows.Forms.FolderBrowserDialog> Windows Forms позволяет легко выполнить эту задачу.

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Выбор папки с помощью компонента FolderBrowserDialog

1. В процедуре проверьте свойство <xref:System.Windows.Forms.Form.DialogResult%2A> компонента <xref:System.Windows.Forms.FolderBrowserDialog>, чтобы увидеть, как было закрыто диалоговое окно, и получите значение свойства <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> компонента <xref:System.Windows.Forms.FolderBrowserDialog>.

2. Если необходимо задать самую верхнюю папку, которая будет отображаться в древовидном представлении диалогового окна, задайте свойство <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>, которое принимает член перечисления <xref:System.Environment.SpecialFolder>.

3. Кроме того, можно задать свойство <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>, которое указывает текстовую строку, отображаемую в верхней части представления в виде дерева обозревателя папок.

    В приведенном ниже примере компонент <xref:System.Windows.Forms.FolderBrowserDialog> используется для выбора папки, аналогично созданию проекта в Visual Studio и предлагающего выбрать папку для ее сохранения. В этом примере имя папки затем отображается в элементе управления <xref:System.Windows.Forms.TextBox> в форме. Рекомендуется поместить расположение в область редактирования, например элемент управления <xref:System.Windows.Forms.TextBox>, чтобы пользователи могли изменять свой выбор в случае ошибки или других проблем. В этом примере предполагается форма с <xref:System.Windows.Forms.FolderBrowserDialog>ным компонентом и элементом управления <xref:System.Windows.Forms.TextBox>.

    ```vb
    Public Sub ChooseFolder()
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then
            TextBox1.Text = FolderBrowserDialog1.SelectedPath
        End If
    End Sub
    ```

    ```csharp
    public void ChooseFolder()
    {
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)
        {
            textBox1.Text = folderBrowserDialog1.SelectedPath;
        }
    }
    ```

    ```cpp
    public:
       void ChooseFolder()
       {
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)
          {
             textBox1->Text = folderBrowserDialog1->SelectedPath;
          }
       }
    ```

    > [!IMPORTANT]
    > Чтобы использовать этот класс, сборке требуется уровень привилегий, предоставляемый свойством <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>, которое является частью перечисления <xref:System.Security.Permissions.FileIOPermissionAccess>. При выполнении в контексте частичного доверия процесс может выдавать исключение из-за недостаточных привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../misc/code-access-security-basics.md).

Сведения о том, как сохранять файлы, см. в разделе [Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Общие сведения о компоненте FolderBrowserDialog (Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [Компонент FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
