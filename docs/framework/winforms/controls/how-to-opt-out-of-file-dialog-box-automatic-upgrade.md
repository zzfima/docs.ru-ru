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
ms.openlocfilehash: 6fd34e1127747739423f6402f128194a3a39f5e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089153"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Как выполнить: Отказ от автоматического обновления диалоговых окон
Когда <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> классы используются в приложении, их внешний вид и поведение зависят от версии приложения в Windows. Когда приложение, которое был создан на [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] или более ранней версии отображается на [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] внешний вид и поведение. Начиная с версии [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], можно отказаться от автоматического обновления для отображения <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-стиля, внешний вид и поведение.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Отказ от автоматического обновления диалоговых окон  
  
1.  Задайте <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> для `false` прежде, чем можно отобразить диалоговое окно.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.FileDialog>
