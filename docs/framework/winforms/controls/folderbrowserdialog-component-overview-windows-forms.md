---
title: Общие сведения о компоненте FolderBrowserDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: aae18167b29c71ad692cc6ba447457cd079374b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074135"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="2576c-102">Общие сведения о компоненте FolderBrowserDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2576c-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="2576c-103">Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> компонент — это модальное диалоговое окно, которое используется для просмотра и выбора папки.</span><span class="sxs-lookup"><span data-stu-id="2576c-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="2576c-104">Новые папки можно также создать изнутри <xref:System.Windows.Forms.FolderBrowserDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="2576c-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2576c-105">Чтобы выбрать файлы, а не папки, используйте [OpenFileDialog](openfiledialog-component-windows-forms.md) компонента.</span><span class="sxs-lookup"><span data-stu-id="2576c-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="2576c-106"><xref:System.Windows.Forms.FolderBrowserDialog> Компонент отображается во время выполнения с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2576c-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="2576c-107">Задать <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> свойства, чтобы определить самую верхнюю папку и все вложенные папки, которые будут отображаться в представлении в виде дерева диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="2576c-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="2576c-108">После отображения диалоговое окно можно использовать <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> свойство, чтобы получить путь к папке, которая была выбрана.</span><span class="sxs-lookup"><span data-stu-id="2576c-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="2576c-109">При добавлении в форму, <xref:System.Windows.Forms.FolderBrowserDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2576c-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2576c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2576c-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="2576c-111">Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2576c-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="2576c-112">Компонент FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="2576c-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
