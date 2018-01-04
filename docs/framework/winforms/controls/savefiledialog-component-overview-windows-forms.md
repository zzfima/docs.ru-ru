---
title: "Общие сведения о компоненте SaveFileDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1505e2bc31afb4f44f0d635b06624528cb16ba15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="e0e56-102">Общие сведения о компоненте SaveFileDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e0e56-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e0e56-103">Компонент Windows Forms <xref:System.Windows.Forms.SaveFileDialog> является стандартным диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="e0e56-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="e0e56-104">Он является таким же, как стандартные **сохранить файл** диалоговым окном, используемым операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="e0e56-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="e0e56-105">Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="e0e56-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="e0e56-106">Работа с помощью компонента SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="e0e56-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="e0e56-107">Компонент используется в качестве простого решения для пользователям сохранять файлы вместо настройки собственного диалогового.</span><span class="sxs-lookup"><span data-stu-id="e0e56-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="e0e56-108">Использование стандартных диалоговых окон Windows, основные функциональные возможности приложений, создаваемых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="e0e56-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="e0e56-109">Имейте в виду, что при с помощью <xref:System.Windows.Forms.SaveFileDialog> компонента, необходимо написать свою собственную логику для сохранения файлов.</span><span class="sxs-lookup"><span data-stu-id="e0e56-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="e0e56-110">Можно использовать <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы отобразить диалоговое окно во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e0e56-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="e0e56-111">Файл можно открыть в режиме чтения и записи с помощью <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e0e56-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="e0e56-112">При добавлении в форму, <xref:System.Windows.Forms.SaveFileDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e0e56-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e56-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e0e56-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="e0e56-114">Компонент SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="e0e56-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
