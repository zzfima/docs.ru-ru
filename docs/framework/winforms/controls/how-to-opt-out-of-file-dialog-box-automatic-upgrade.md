---
title: 'Как выполнить: Отказ от автоматического обновления диалоговых окон'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: e12134768d41589dedbeb5a00cab4244c7324f97
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722622"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="546fb-102">Как выполнить: Отказ от автоматического обновления диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="546fb-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="546fb-103">Когда <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> классы используются в приложении, их внешний вид и поведение зависят от версии приложения в Windows.</span><span class="sxs-lookup"><span data-stu-id="546fb-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="546fb-104">Когда приложение, которое был создан на [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] или более ранней версии отображается на [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] внешний вид и поведение.</span><span class="sxs-lookup"><span data-stu-id="546fb-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="546fb-105">Начиная с .NET Framework 3.0, можно отказаться от автоматического обновления для отображения <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-стиля, внешний вид и поведение.</span><span class="sxs-lookup"><span data-stu-id="546fb-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="546fb-106">Отказ от автоматического обновления диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="546fb-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="546fb-107">Задайте <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> для `false` прежде, чем можно отобразить диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="546fb-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546fb-108">См. также</span><span class="sxs-lookup"><span data-stu-id="546fb-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
