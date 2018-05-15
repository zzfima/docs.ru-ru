---
title: Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 380f8abe502c37e57207c43696158c1e3bdc7697
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="55b50-102">Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла</span><span class="sxs-lookup"><span data-stu-id="55b50-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="55b50-103">Когда <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> классы используются в приложении, их внешний вид и поведение зависит от версии приложения для Windows.</span><span class="sxs-lookup"><span data-stu-id="55b50-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="55b50-104">Когда приложение, где был создан [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] или более ранней версии отображается на [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] внешний вид и поведение.</span><span class="sxs-lookup"><span data-stu-id="55b50-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="55b50-105">Начиная с версии [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], вы можете отказаться от автоматического обновления для отображения <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-стиля, внешний вид и поведение.</span><span class="sxs-lookup"><span data-stu-id="55b50-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="55b50-106">Отказ от автоматического обновления диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="55b50-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="55b50-107">Задать <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> для `false` до отображения диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="55b50-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b50-108">См. также</span><span class="sxs-lookup"><span data-stu-id="55b50-108">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>
