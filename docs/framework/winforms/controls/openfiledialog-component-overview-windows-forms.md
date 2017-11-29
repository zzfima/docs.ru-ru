---
title: "Общие сведения о компоненте OpenFileDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35c947e3efbb9b2e5df775f83ffc6068e49c84e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="01f5d-102">Общие сведения о компоненте OpenFileDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="01f5d-102">OpenFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="01f5d-103">Компонент Windows Forms <xref:System.Windows.Forms.OpenFileDialog> является стандартным диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="01f5d-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="01f5d-104">Он аналогичен **открыть файл** диалоговому операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="01f5d-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="01f5d-105">Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="01f5d-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="using-this-component"></a><span data-ttu-id="01f5d-106">С помощью данного компонента</span><span class="sxs-lookup"><span data-stu-id="01f5d-106">Using this Component</span></span>  
 <span data-ttu-id="01f5d-107">Этот компонент используется в приложении Windows в качестве простого решения для выбора файлов вместо настройки собственного диалогового.</span><span class="sxs-lookup"><span data-stu-id="01f5d-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="01f5d-108">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="01f5d-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="01f5d-109">Имейте в виду, что при с помощью <xref:System.Windows.Forms.OpenFileDialog> компонента, необходимо написать свою собственную логику для открытия файла.</span><span class="sxs-lookup"><span data-stu-id="01f5d-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>  
  
 <span data-ttu-id="01f5d-110">Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод для отображения диалогового окна во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="01f5d-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="01f5d-111">Можно разрешить пользователям выбрать несколько файлов, открываемых с <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="01f5d-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="01f5d-112">Кроме того, можно использовать <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> свойства, чтобы определить, если в диалоговом окне будет отображаться флажок только для чтения.</span><span class="sxs-lookup"><span data-stu-id="01f5d-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="01f5d-113"><xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Свойство указывает, будет ли установлен флажок только для чтения.</span><span class="sxs-lookup"><span data-stu-id="01f5d-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="01f5d-114">Наконец <xref:System.Windows.Forms.FileDialog.Filter%2A> свойство задает текущий строку фильтра имен файлов, которая определяет варианты, которые отображаются в поле «Тип файлов» в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="01f5d-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>  
  
 <span data-ttu-id="01f5d-115">При добавлении в форму, <xref:System.Windows.Forms.OpenFileDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="01f5d-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f5d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="01f5d-116">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="01f5d-117">Компонент OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="01f5d-117">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
