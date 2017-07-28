---
title: "Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "[Windows Forms] OpenFileDialog отказ от автоматического обновления"
  - "диалоговое окно [Windows Forms] файла, отказ от автоматического обновления"
  - "Диалоговое окно файла Windows Vista поле, отказ от автоматического обновления"
  - "[Windows Forms] SaveFileDialog отказ от автоматического обновления"
  - "AutoUpgradeEnabled - свойство"
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Отказ от автоматического обновления диалоговых окон открытия и сохранения файла
Когда <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> классы используются в приложении, их внешний вид и поведение в зависимости от версии Windows работает приложение. Когда приложение, который был создан на [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] или более ранней версии отображается на [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> автоматически отображаются с [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] внешний вид и поведение. Начиная с [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], можно отказаться от автоматического обновления для отображения <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> с [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-стиля, внешний вид и поведение.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Чтобы отказаться от автоматического обновления файла диалоговое окно  
  
1.  Задайте <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog> в `false` до отображения диалогового окна.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FileDialog>