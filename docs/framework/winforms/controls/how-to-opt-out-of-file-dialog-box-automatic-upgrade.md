---
title: "Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b785b9da22aa6f17c14b85263b94fb70fbef5f7a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла
Когда <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> классы используются в приложении, их внешний вид и поведение зависит от версии приложения для Windows. Когда приложение, где был создан [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] или более ранней версии отображается на [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] внешний вид и поведение. Начиная с версии [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], вы можете отказаться от автоматического обновления для отображения <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-стиля, внешний вид и поведение.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Отказ от автоматического обновления диалоговых окон  
  
1.  Задать <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> для `false` до отображения диалогового окна.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FileDialog>
