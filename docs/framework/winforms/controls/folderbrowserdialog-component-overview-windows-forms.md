---
title: Общие сведения о компоненте FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745725"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="203c8-102">Общие сведения о компоненте FolderBrowserDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="203c8-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="203c8-103">Компонент Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> является модальным диалоговым окном, используемым для обзора и выбора папок.</span><span class="sxs-lookup"><span data-stu-id="203c8-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="203c8-104">Новые папки также можно создавать в компоненте <xref:System.Windows.Forms.FolderBrowserDialog>.</span><span class="sxs-lookup"><span data-stu-id="203c8-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="203c8-105">Для выбора файлов вместо папок используйте компонент [OpenFileDialog](openfiledialog-component-windows-forms.md) .</span><span class="sxs-lookup"><span data-stu-id="203c8-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="203c8-106">Компонент <xref:System.Windows.Forms.FolderBrowserDialog> отображается во время выполнения с помощью метода <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="203c8-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="203c8-107">Задайте свойство <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>, чтобы определить самую верхнюю папку и все вложенные папки, которые будут отображаться в представлении в виде дерева диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="203c8-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="203c8-108">После отображения диалогового окна можно использовать свойство <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>, чтобы получить путь к выбранной папке.</span><span class="sxs-lookup"><span data-stu-id="203c8-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="203c8-109">При добавлении в форму <xref:System.Windows.Forms.FolderBrowserDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="203c8-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="203c8-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="203c8-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="203c8-111">Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="203c8-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="203c8-112">Компонент FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="203c8-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
