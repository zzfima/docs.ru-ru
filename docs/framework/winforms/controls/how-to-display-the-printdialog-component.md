---
title: "Практическое руководство. Отображение компонента PrintDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d955febe528add4b774766a3b204f96eef5a119d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-the-printdialog-component"></a>Практическое руководство. Отображение компонента PrintDialog
<xref:System.Windows.Forms.PrintDialog> Компонент является стандартной Windows диалоговое окно печати, многие ваши пользователи будут знакомы с. Поскольку пользователям будет удобно работать с ней, он может оказаться эффективным для использования <xref:System.Windows.Forms.PrintDialog> компонента.  
  
### <a name="to-display-the-printdialog-component"></a>Отображение компонента PrintDialog  
  
-   Вызовите <xref:System.Windows.Forms.Form.ShowDialog%2A> метода в код приложения.  
  
     После отображения этого компонента пользователи смогут взаимодействовать с ним, задавая свойства задания печати. Они сохраняются в <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` класса (и <xref:System.Drawing.Printing.PageSettings> класса, если пользователь обращается к [компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) через <xref:System.Windows.Forms.PrintDialog> компонента) связанный с этим заданием печати. Затем можно вызывать заданные пользователями свойства для определения специфики задания печати.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание стандартных заданий печати в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [Практическое руководство. Захват данных, введенных пользователем в PrintDialog во время выполнения](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [Поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)
