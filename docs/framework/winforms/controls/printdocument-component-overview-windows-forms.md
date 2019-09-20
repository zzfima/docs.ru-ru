---
title: Общие сведения о компоненте PrintDocument (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928999"
---
# <a name="printdocument-component-overview-windows-forms"></a>Общие сведения о компоненте PrintDocument (Windows Forms)

Компонент Windows Forms [PrintDocument](printdocument-component-windows-forms.md) позволяет определять свойства, описывающие печатаемое содержимое, и распечатывать документы в приложениях Windows. Его можно использовать в сочетании с компонентом [PrintDialog](printdialog-component-windows-forms.md) для управления всеми аспектами печати документов.

## <a name="working-with-the-printdocument-component"></a>Работа с компонентом PrintDocument

Ниже приведены два основных сценария, в <xref:System.Drawing.Printing.PrintDocument> которых участвует компонент:

- Простые задания печати, такие как печать отдельного текстового файла. В этом случае необходимо добавить <xref:System.Drawing.Printing.PrintDocument> компонент в форму Windows Forms, а затем добавить программную логику, которая выводит файл <xref:System.Drawing.Printing.PrintDocument.PrintPage> в обработчике событий. Логика программирования должна завершающейся с помощью <xref:System.Drawing.Printing.PrintDocument.Print%2A> метода для печати документа. Этот метод отправляет <xref:System.Drawing.Graphics> на принтер объект, содержащийся <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> в свойстве <xref:System.Drawing.Printing.PrintPageEventArgs> класса. Пример, демонстрирующий печать текстового документа с помощью <xref:System.Drawing.Printing.PrintDocument> компонента, см. в разделе как [ Распечатайте многостраничный текстовый файл в](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)Windows Forms.

- Более сложные задания печати, например ситуации, когда требуется повторное использование уже написанной логики печати. В этом случае необходимо создать новый компонент из компонента <xref:System.Drawing.Printing.PrintDocument> и переопределить (см. Дополнительные сведения о [переопределениях](../../../visual-basic/language-reference/modifiers/overrides.md) Visual Basic или [переопределении](../../../csharp/language-reference/keywords/override.md) для C#) <xref:System.Drawing.Printing.PrintDocument.PrintPage> события.

При добавлении в форму <xref:System.Drawing.Printing.PrintDocument> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](../advanced/windows-forms-print-support.md)
- [Компонент PrintDocument](printdocument-component-windows-forms.md)
