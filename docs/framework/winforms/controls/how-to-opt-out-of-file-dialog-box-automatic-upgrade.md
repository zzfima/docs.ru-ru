---
title: Как Отказ от автоматического обновления диалоговых окон
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 0753873ac37f26d6503397290ef4603702737a86
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170614"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Как Отказ от автоматического обновления диалоговых окон
Когда <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> классы используются в приложении, их внешний вид и поведение зависят от версии приложения в Windows. При отображении приложения, созданный на платформе .NET Framework 2.0 или более ранней версии на [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] внешний вид и поведение. Начиная с .NET Framework 3.0, можно отказаться от автоматического обновления для отображения <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-стиля, внешний вид и поведение.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Отказ от автоматического обновления диалоговых окон  
  
1. Задайте <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> для `false` прежде, чем можно отобразить диалоговое окно.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.FileDialog>
