---
title: Как выполнить Отображение компонента PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 5315dc8b47c8ca846376ac6d1da5a0bf46fd6241
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544001"
---
# <a name="how-to-display-the-printdialog-component"></a>Как выполнить Отображение компонента PrintDialog
<xref:System.Windows.Forms.PrintDialog> Компонент является стандартным, многие ваши пользователи будут знакомы с окном диалогового окна печати Windows. Так как пользователям будет удобно работать с ним, полезно было бы использовать <xref:System.Windows.Forms.PrintDialog> компонента.  
  
### <a name="to-display-the-printdialog-component"></a>Отображение компонента PrintDialog  
  
-   Вызовите <xref:System.Windows.Forms.Form.ShowDialog%2A> метода в код приложения.  
  
     После отображения этого компонента пользователи смогут взаимодействовать с ним, задавая свойства задания печати. Они сохраняются в <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` класс (и <xref:System.Drawing.Printing.PageSettings> класса, если пользователь обращается к [компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) через <xref:System.Windows.Forms.PrintDialog> компонент) связанные с этим заданием печати. Затем можно вызывать заданные пользователями свойства для определения специфики задания печати.  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Создание заданий печати стандартный Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [Практическое руководство. Захват данных пользователем в PrintDialog во время выполнения](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)
- [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
- [Поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
- [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)
