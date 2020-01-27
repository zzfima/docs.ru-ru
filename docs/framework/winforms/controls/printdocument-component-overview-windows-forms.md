---
title: Общие сведения о компоненте PrintDocument
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a82cc0cdcb8cfae796c9c6bf60ab73873f85a291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728537"
---
# <a name="printdocument-component-overview-windows-forms"></a>Общие сведения о компоненте PrintDocument (Windows Forms)

Компонент Windows Forms [PrintDocument](printdocument-component-windows-forms.md) позволяет определять свойства, описывающие печатаемое содержимое, и распечатывать документы в приложениях Windows. Его можно использовать в сочетании с компонентом [PrintDialog](printdialog-component-windows-forms.md) для управления всеми аспектами печати документов.

## <a name="working-with-the-printdocument-component"></a>Работа с компонентом PrintDocument

Ниже перечислены два основных сценария, в которых используется компонент <xref:System.Drawing.Printing.PrintDocument>.

- Простые задания печати, такие как печать отдельного текстового файла. В этом случае необходимо добавить компонент <xref:System.Drawing.Printing.PrintDocument> в форму Windows Forms, а затем добавить программную логику, которая выводит файл в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage>. Логика программирования должна завершающейся с помощью метода <xref:System.Drawing.Printing.PrintDocument.Print%2A> для печати документа. Этот метод отправляет на принтер объект <xref:System.Drawing.Graphics>, содержащийся в свойстве <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs>. Пример, демонстрирующий печать текстового документа с помощью компонента <xref:System.Drawing.Printing.PrintDocument>, см. [в разделе Практические руководства. Печать многостраничного текстового файла в Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).

- Более сложные задания печати, например ситуации, когда требуется повторное использование уже написанной логики печати. В этом случае необходимо создать новый компонент из компонента <xref:System.Drawing.Printing.PrintDocument> и переопределить (см. Дополнительные сведения о [переопределениях](../../../visual-basic/language-reference/modifiers/overrides.md) Visual Basic или [переопределении](../../../csharp/language-reference/keywords/override.md) для C#) <xref:System.Drawing.Printing.PrintDocument.PrintPage> события.

При добавлении в форму <xref:System.Drawing.Printing.PrintDocument> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также:

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](../advanced/windows-forms-print-support.md)
- [Компонент PrintDocument](printdocument-component-windows-forms.md)
