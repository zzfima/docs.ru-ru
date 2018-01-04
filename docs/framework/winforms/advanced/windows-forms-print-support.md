---
title: "Поддержка печати в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81f89ee41eb9f8b492ab12e30ae4580cdffbd8f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-print-support"></a>Поддержка печати в Windows Forms
Печать в Windows Forms состоит в основном из использования [компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) компонента, чтобы пользователь мог напечатать и [управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) управления [PrintDialog Компонент](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) и [компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) компоненты для обеспечения знакомый графический интерфейс для пользователей, привыкших к операционной системе Windows.  
  
 Обычно создается новый экземпляр <xref:System.Drawing.Printing.PrintDocument> набор компонентов, свойств, описывающих печатаемое содержимое с помощью <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings> классы и вызовите метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> способ печати документа.  
  
 В ходе работы при печати из приложения Windows <xref:System.Drawing.Printing.PrintDocument> компонент отображает диалоговое окно прерывания печати, которое оповестить пользователей о начале печати и чтобы разрешить задание печати отменяется.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание стандартных заданий печати в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 Описание способов использования <xref:System.Drawing.Printing.PrintDocument> компонента для печати в Windows Forms.  
  
 [Практическое руководство. Захват данных, введенных пользователем в PrintDialog во время выполнения](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Объясняется, как изменить выбранные параметры печати программными средствами с помощью <xref:System.Windows.Forms.PrintDialog> компонента.  
  
 [Практическое руководство. Выбор принтера, подключенного к компьютеру пользователя, в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Описывает изменение принтер для печати с помощью <xref:System.Windows.Forms.PrintDialog> компонента во время выполнения.  
  
 [Практическое руководство. Печать графических изображений в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 Справка по выводу графики на принтер.  
  
 [Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Справка по выводу текста на принтер.  
  
 [Практическое руководство. Выполнение заданий печати в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 Справка по оповещению пользователей о завершении задания печати.  
  
 [Практическое руководство. Печать формы Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 Показано, как напечатать копию текущей формы.  
  
 [Практическое руководство. Печать в Windows Forms с использованием предварительного просмотра](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 Показано, как использовать <xref:System.Windows.Forms.PrintPreviewDialog> для печати документа.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 Объясняется использование <xref:System.Drawing.Printing.PrintDocument> компонента.  
  
 [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 Объясняется использование <xref:System.Windows.Forms.PrintDialog> компонента.  
  
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 Объясняется использование <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.  
  
 [Компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 Объясняется использование <xref:System.Windows.Forms.PageSetupDialog> компонента.  
  
 <xref:System.Drawing.Printing>  
 Описываются классы в <xref:System.Drawing.Printing> пространства имен.
