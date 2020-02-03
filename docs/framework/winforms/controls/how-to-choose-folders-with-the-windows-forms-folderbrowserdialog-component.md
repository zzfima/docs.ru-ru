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
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="dd15f-102">Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd15f-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="dd15f-103">Часто в создаваемых приложениях Windows требуется предлагать пользователю выбрать папку, как правило, для сохранения набора файлов.</span><span class="sxs-lookup"><span data-stu-id="dd15f-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="dd15f-104">Компонент <xref:System.Windows.Forms.FolderBrowserDialog> Windows Forms позволяет легко выполнить эту задачу.</span><span class="sxs-lookup"><span data-stu-id="dd15f-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="dd15f-105">Выбор папки с помощью компонента FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="dd15f-105">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="dd15f-106">В процедуре проверьте свойство <xref:System.Windows.Forms.Form.DialogResult%2A> компонента <xref:System.Windows.Forms.FolderBrowserDialog>, чтобы увидеть, как было закрыто диалоговое окно, и получите значение свойства <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> компонента <xref:System.Windows.Forms.FolderBrowserDialog>.</span><span class="sxs-lookup"><span data-stu-id="dd15f-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="dd15f-107">Если необходимо задать самую верхнюю папку, которая будет отображаться в древовидном представлении диалогового окна, задайте свойство <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>, которое принимает член перечисления <xref:System.Environment.SpecialFolder>.</span><span class="sxs-lookup"><span data-stu-id="dd15f-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="dd15f-108">Кроме того, можно задать свойство <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>, которое указывает текстовую строку, отображаемую в верхней части представления в виде дерева обозревателя папок.</span><span class="sxs-lookup"><span data-stu-id="dd15f-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="dd15f-109">В приведенном ниже примере компонент <xref:System.Windows.Forms.FolderBrowserDialog> используется для выбора папки, аналогично созданию проекта в Visual Studio и предлагающего выбрать папку для ее сохранения.</span><span class="sxs-lookup"><span data-stu-id="dd15f-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="dd15f-110">В этом примере имя папки затем отображается в элементе управления <xref:System.Windows.Forms.TextBox> в форме.</span><span class="sxs-lookup"><span data-stu-id="dd15f-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="dd15f-111">Рекомендуется поместить расположение в область редактирования, например элемент управления <xref:System.Windows.Forms.TextBox>, чтобы пользователи могли изменять свой выбор в случае ошибки или других проблем.</span><span class="sxs-lookup"><span data-stu-id="dd15f-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="dd15f-112">В этом примере предполагается форма с <xref:System.Windows.Forms.FolderBrowserDialog>ным компонентом и элементом управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="dd15f-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

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
    > <span data-ttu-id="dd15f-113">Чтобы использовать этот класс, сборке требуется уровень привилегий, предоставляемый свойством <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>, которое является частью перечисления <xref:System.Security.Permissions.FileIOPermissionAccess>.</span><span class="sxs-lookup"><span data-stu-id="dd15f-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="dd15f-114">При выполнении в контексте частичного доверия процесс может выдавать исключение из-за недостаточных привилегий.</span><span class="sxs-lookup"><span data-stu-id="dd15f-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="dd15f-115">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="dd15f-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="dd15f-116">Сведения о том, как сохранять файлы, см. в разделе [Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="dd15f-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd15f-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dd15f-117">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="dd15f-118">Общие сведения о компоненте FolderBrowserDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dd15f-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="dd15f-119">Компонент FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="dd15f-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
