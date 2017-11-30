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
ms.openlocfilehash: 4cbdc1cb96234e302458cbeac6d6ae26b63c956e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="2d4fc-102">Общие сведения о компоненте SaveFileDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2d4fc-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="2d4fc-103">Компонент Windows Forms <xref:System.Windows.Forms.SaveFileDialog> является стандартным диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="2d4fc-104">Он является таким же, как стандартные **сохранить файл** диалоговым окном, используемым операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="2d4fc-105">Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="2d4fc-106">Работа с помощью компонента SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="2d4fc-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="2d4fc-107">Компонент используется в качестве простого решения для пользователям сохранять файлы вместо настройки собственного диалогового.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="2d4fc-108">Использование стандартных диалоговых окон Windows, основные функциональные возможности приложений, создаваемых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="2d4fc-109">Имейте в виду, что при с помощью <xref:System.Windows.Forms.SaveFileDialog> компонента, необходимо написать свою собственную логику для сохранения файлов.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="2d4fc-110">Можно использовать <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы отобразить диалоговое окно во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="2d4fc-111">Файл можно открыть в режиме чтения и записи с помощью <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="2d4fc-112">При добавлении в форму, <xref:System.Windows.Forms.SaveFileDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2d4fc-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d4fc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2d4fc-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="2d4fc-114">Компонент SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="2d4fc-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
