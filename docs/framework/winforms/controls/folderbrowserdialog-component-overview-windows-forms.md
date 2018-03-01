---
title: "Общие сведения о компоненте FolderBrowserDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26d2b6294a503edd25b499da2ab67739cdf87174
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="a8b4f-102">Общие сведения о компоненте FolderBrowserDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a8b4f-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="a8b4f-103">Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> компонент является модальным диалоговым окном, который используется для просмотра и выбора папки.</span><span class="sxs-lookup"><span data-stu-id="a8b4f-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="a8b4f-104">Новые папки могут также создаваться внутри <xref:System.Windows.Forms.FolderBrowserDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a8b4f-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8b4f-105">Чтобы выбрать файлы, вместо папки, используйте [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) компонента.</span><span class="sxs-lookup"><span data-stu-id="a8b4f-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="a8b4f-106"><xref:System.Windows.Forms.FolderBrowserDialog> Компонент отображается во время выполнения с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a8b4f-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="a8b4f-107">Задать <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> свойства, чтобы определить папку верхнего уровня и все вложенные папки, которые будут отображаться в представлении дерева в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="a8b4f-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="a8b4f-108">После отображения диалоговое окно можно использовать <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> свойства, чтобы получить путь к папке, которая была выбрана.</span><span class="sxs-lookup"><span data-stu-id="a8b4f-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="a8b4f-109">При добавлении в форму, <xref:System.Windows.Forms.FolderBrowserDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a8b4f-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b4f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a8b4f-110">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="a8b4f-111">Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8b4f-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [<span data-ttu-id="a8b4f-112">Компонент FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="a8b4f-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
