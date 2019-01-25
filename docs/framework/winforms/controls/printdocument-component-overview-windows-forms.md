---
title: Общие сведения о компоненте PrintDocument (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 2facbf0a567f81aa6debe2ca60f7f8eabc794bb0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532357"
---
# <a name="printdocument-component-overview-windows-forms"></a>Общие сведения о компоненте PrintDocument (Windows Forms)
Компонент Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) позволяет определять свойства, описывающие печатаемое содержимое, и распечатывать документы в приложениях Windows. Его можно использовать в сочетании с компонентом [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) для управления всеми аспектами печати документов.  
  
## <a name="working-with-the-printdocument-component"></a>Работа с компонентом PrintDocument  
 Два основных сценариях, включающих <xref:System.Drawing.Printing.PrintDocument> компонент:  
  
-   Простые задания печати, такие как печать отдельного текстового файла. В этом случае необходимо добавить <xref:System.Drawing.Printing.PrintDocument> компонента в форму Windows, затем добавить логику программирования, распечатывающую файл в <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчик событий. Логика программирования должна завершающейся с <xref:System.Drawing.Printing.PrintDocument.Print%2A> способ печати документа. Этот метод отправляет <xref:System.Drawing.Graphics> объектов, содержащихся в <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> свойство <xref:System.Drawing.Printing.PrintPageEventArgs> класса, на принтер. Пример, демонстрирующий способы печати текстового документа с помощью <xref:System.Drawing.Printing.PrintDocument> компонента, см. в разделе [как: Печать многостраничных текстовых файлов в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Более сложные задания печати, например ситуации, когда требуется повторное использование уже написанной логики печати. В этом случае необходимо наследовать новый компонент из <xref:System.Drawing.Printing.PrintDocument> компонента и переопределение (см. в разделе [переопределяет](~/docs/visual-basic/language-reference/modifiers/overrides.md) для Visual Basic или [переопределить](~/docs/csharp/language-reference/keywords/override.md) для C#) <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий.  
  
 При добавлении в форму, <xref:System.Drawing.Printing.PrintDocument> компонент появится в области в нижней части конструктора Windows Forms.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
- [Компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
