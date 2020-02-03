---
title: Поддержка печати
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732491"
---
# <a name="windows-forms-print-support"></a>Поддержка печати в Windows Forms
Печать в Windows Forms состоит в основном с использованием компонента [PrintDocument](../controls/printdocument-component-windows-forms.md) , который позволяет пользователю печатать, и компоненты элемента управления [PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) , [компонента PrintDialog](../controls/printdialog-component-windows-forms.md) и [компонента PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) , чтобы обеспечить знакомый графический интерфейс для пользователей, привыкших к операционной системе Windows.  
  
 Как правило, создается новый экземпляр компонента <xref:System.Drawing.Printing.PrintDocument>, устанавливаются свойства, описывающие, что печатать с помощью классов <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings>, и вызывается метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> для фактической печати документа.  
  
 Во время печати из приложения Windows компонент <xref:System.Drawing.Printing.PrintDocument> покажет диалоговое окно "Прервать печать", чтобы предупредить пользователей о том, что происходит печать, и разрешить отмену задания печати.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Практическое руководство. Создание стандартных заданий печати в Windows Forms](how-to-create-standard-windows-forms-print-jobs.md)  
 Объясняется, как использовать компонент <xref:System.Drawing.Printing.PrintDocument> для печати из формы Windows Forms.  
  
 [Практическое руководство. Захват данных, введенных пользователем в PrintDialog во время выполнения](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Объясняется, как программным способом изменить выбранные параметры печати с помощью компонента <xref:System.Windows.Forms.PrintDialog>.  
  
 [Практическое руководство. Выбор принтера, подключенного к компьютеру пользователя, в Windows Forms](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Описывает изменение принтера для печати с использованием компонента <xref:System.Windows.Forms.PrintDialog> во время выполнения.  
  
 [Практическое руководство. Печать графических изображений в Windows Forms](how-to-print-graphics-in-windows-forms.md)  
 Описывает отправку графики на принтер.  
  
 [Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Описывает отправку текста на принтер.  
  
 [Практическое руководство. Выполнение заданий печати в Windows Forms](how-to-complete-windows-forms-print-jobs.md)  
 Объясняет, как предупредить пользователей о завершении задания печати.  
  
 [Практическое руководство. Печать формы Windows Forms](how-to-print-a-windows-form.md)  
 Показывает, как распечатать копию текущей формы.  
  
 [Практическое руководство. Печать в Windows Forms с использованием предварительного просмотра](how-to-print-in-windows-forms-using-print-preview.md)  
 Показывает, как использовать <xref:System.Windows.Forms.PrintPreviewDialog> для печати документа.  
  
## <a name="related-sections"></a>См. также  
 [Компонент PrintDocument](../controls/printdocument-component-windows-forms.md)  
 Объясняет использование компонента <xref:System.Drawing.Printing.PrintDocument>.  
  
 [Компонент PrintDialog](../controls/printdialog-component-windows-forms.md)  
 Объясняет использование компонента <xref:System.Windows.Forms.PrintDialog>.  
  
 [Элемент управления PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md)  
 Объясняет использование элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
 [Компонент PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md)  
 Объясняет использование компонента <xref:System.Windows.Forms.PageSetupDialog>.  
  
 <xref:System.Drawing.Printing>  
 Описывает классы в пространстве имен <xref:System.Drawing.Printing>.
