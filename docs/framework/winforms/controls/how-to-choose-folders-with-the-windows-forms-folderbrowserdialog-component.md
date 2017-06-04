---
title: "Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms | Microsoft Docs"
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
  - "каталоги [Windows Forms], выбор"
  - "каталоги [Windows Forms], выбор"
  - "FolderBrowserDialog - компонент [Windows Forms], выбор каталогов"
  - "папки [Windows Forms], выбор"
  - "папки [Windows Forms], выбор"
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms
В создаваемых приложениях Windows пользователям часто приходится выбирать папку, обычно для сохранения набора файлов.  С помощью компонента Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> эта задача легко решается.  
  
### Выбор папок с помощью компонента FolderBrowserDialog  
  
1.  В процедуре проверьте свойство <xref:System.Windows.Forms.Form.DialogResult%2A> компонента <xref:System.Windows.Forms.FolderBrowserDialog>, чтобы узнать, как было закрыто диалоговое окно и получить значение свойства <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> компонента <xref:System.Windows.Forms.FolderBrowserDialog>.  
  
2.  Если необходимо задать папку самого верхнего уровня, которая будет отображаться в дереве этого диалогового окна, задайте свойство <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>, которое выбирает член перечисления [SpecialFolder](frlrfSystemEnvironmentSpecialFolderClassTopic).  
  
3.  Кроме того, можно задать свойство <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>, которое указывает строку текста, появляющуюся вверху дерева обозревателя папок.  
  
     В приведенном ниже примере компонент <xref:System.Windows.Forms.FolderBrowserDialog> используется для выбора папки в случае, подобном тому, когда при создании проекта в Visual Studio пользователя просят выбрать папку для сохранения в ней проекта.  В данном примере имя папки затем отображается в элементе управления <xref:System.Windows.Forms.TextBox> этой формы.  Прекрасное решение — поместить расположение в область, доступную для изменения, например элемент управления <xref:System.Windows.Forms.TextBox>, чтобы пользователь имел возможность изменить свой выбор в случае ошибки или других проблем.  В этом примере предполагается форма с компонентом <xref:System.Windows.Forms.FolderBrowserDialog> и элементом управления <xref:System.Windows.Forms.TextBox>.  
  
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
    >  Для использования этого класса сборка требует уровня привилегий, предоставляемого свойством [FileIOPermissionAttribute.PathDiscoveryProperty](frlrfSystemSecurityPermissionsFileIOPermissionAttributeClassPathDiscoveryTopic), являющимся частью перечисления <xref:System.Security.Permissions.FileIOPermissionAccess>.  Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из\-за недостатка привилегий.  Дополнительные сведения см. в разделе [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
 Сведения о сохранении файлов см. в разделе [Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## См. также  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [Общие сведения о компоненте FolderBrowserDialog \(Windows Forms\)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)   
 [Компонент FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)