---
title: "Практическое руководство. Создание рамки вокруг элемента управления в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b8fc8774e1f861db989b05678235ea34e38318c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Практическое руководство. Создание рамки вокруг элемента управления в Windows Forms
В следующем примере кода демонстрируется создание границы или контура вокруг <xref:System.Windows.Forms.RichTextBox> элемента управления. В примере задается значение <xref:System.Windows.Forms.Panel> элемента управления <xref:System.Windows.Forms.Padding> равным 5, а свойству <xref:System.Windows.Forms.Control.Dock%2A> дочернего <xref:System.Windows.Forms.RichTextBox> управления <xref:System.Windows.Forms.DockStyle.Fill>. <xref:System.Windows.Forms.Control.BackColor%2A> Из <xref:System.Windows.Forms.Panel> задано для элемента управления <xref:System.Drawing.Color.Blue%2A>, которая создает синяя рамка вокруг <xref:System.Windows.Forms.RichTextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Padding>  
 [Поля и заполнение в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)
