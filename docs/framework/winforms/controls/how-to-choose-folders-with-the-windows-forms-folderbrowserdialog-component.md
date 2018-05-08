---
title: Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms
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
ms.openlocfilehash: 657aad6efa195ec3d9741f4f91d4e01af4a54a19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms
Часто в создаваемых приложениях Windows требуется предлагать пользователю выбрать папку, как правило, для сохранения набора файлов. Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> компонент позволяет эта задача легко решается.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Выбор папки с помощью компонента FolderBrowserDialog  
  
1.  В процедуре, проверьте <xref:System.Windows.Forms.FolderBrowserDialog> компонента <xref:System.Windows.Forms.Form.DialogResult%2A> свойство, чтобы посмотреть, как окно было закрыто и получить значение <xref:System.Windows.Forms.FolderBrowserDialog> компонента <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> свойство.  
  
2.  Если требуется набор верхнего уровня папки, которая будет отображаться в представлении дерева в диалоговом окне задайте <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> свойства, которое принимает членом <xref:System.Environment.SpecialFolder> перечисления.  
  
3.  Кроме того, можно задать <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> свойство, которое указывает строку текста, который отображается в верхней части дерева папки в браузере.  
  
     В следующем примере <xref:System.Windows.Forms.FolderBrowserDialog> компонент используется для выбора папки аналогично при создании проекта в Visual Studio и будет предложено выбрать папку для сохранения в ней. В этом примере имя папки затем отображается в <xref:System.Windows.Forms.TextBox> элемента управления в форме. Рекомендуется поместить расположение в область редактирования, такие как <xref:System.Windows.Forms.TextBox> таким образом, пользователь может изменить свой выбор в случае ошибки или других проблем. В этом примере предполагается наличие формы с <xref:System.Windows.Forms.FolderBrowserDialog> компонента и <xref:System.Windows.Forms.TextBox> элемента управления.  
  
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
    >  С помощью этого класса, сборка требует уровня прав доступа, предоставленных <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> свойство, которое входит в состав объекта <xref:System.Security.Permissions.FileIOPermissionAccess> перечисления. При выполнении в контексте частичного доверия процесс может выдавать исключение из-за недостаточных привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).  
  
 Сведения о том, как сохранять файлы, см. в разделе [Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [Общие сведения о компоненте FolderBrowserDialog (Windows Forms)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [Компонент FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
