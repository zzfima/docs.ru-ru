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
ms.openlocfilehash: bbde260cc7f05226c9b06325b45708e1cde3cf8c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976887"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="ee50c-102">Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла</span><span class="sxs-lookup"><span data-stu-id="ee50c-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="ee50c-103">Если классы <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> используются в приложении, их внешний вид и поведение зависят от версии Windows, в которой выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="ee50c-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="ee50c-104">Если приложение, созданное на .NET Framework 2,0 или более ранней версии, отображается в Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с внешним видом и поведением Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="ee50c-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the Windows Vista appearance and behavior.</span></span> <span data-ttu-id="ee50c-105">Начиная с .NET Framework 3,0, можно отказаться от автоматического обновления, чтобы отобразить <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с отображением и поведением в стиле [!INCLUDE[winxp](../../../../includes/winxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee50c-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="ee50c-106">Отказ от автоматического обновления диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="ee50c-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="ee50c-107">Перед отображением диалогового окна задайте для свойства <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ee50c-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee50c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ee50c-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
