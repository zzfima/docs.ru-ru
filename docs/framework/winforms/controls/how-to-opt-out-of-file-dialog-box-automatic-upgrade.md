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
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла
Если классы <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> используются в приложении, их внешний вид и поведение зависят от версии Windows, в которой выполняется приложение. Если приложение, созданное на .NET Framework 2,0 или более ранней версии, отображается в Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с внешним видом и поведением Windows Vista. Начиная с .NET Framework 3,0, можно отказаться от автоматического обновления, чтобы отобразить <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с отображением и поведением в стиле [!INCLUDE[winxp](../../../../includes/winxp-md.md)].  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Отказ от автоматического обновления диалоговых окон  
  
1. Перед отображением диалогового окна задайте для свойства <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> значение `false`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.FileDialog>
