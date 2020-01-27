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
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="0b721-102">Общие сведения о компоненте PrintDocument (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0b721-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="0b721-103">Компонент Windows Forms [PrintDocument](printdocument-component-windows-forms.md) позволяет определять свойства, описывающие печатаемое содержимое, и распечатывать документы в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="0b721-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="0b721-104">Его можно использовать в сочетании с компонентом [PrintDialog](printdialog-component-windows-forms.md) для управления всеми аспектами печати документов.</span><span class="sxs-lookup"><span data-stu-id="0b721-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="0b721-105">Работа с компонентом PrintDocument</span><span class="sxs-lookup"><span data-stu-id="0b721-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="0b721-106">Ниже перечислены два основных сценария, в которых используется компонент <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="0b721-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="0b721-107">Простые задания печати, такие как печать отдельного текстового файла.</span><span class="sxs-lookup"><span data-stu-id="0b721-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="0b721-108">В этом случае необходимо добавить компонент <xref:System.Drawing.Printing.PrintDocument> в форму Windows Forms, а затем добавить программную логику, которая выводит файл в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="0b721-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="0b721-109">Логика программирования должна завершающейся с помощью метода <xref:System.Drawing.Printing.PrintDocument.Print%2A> для печати документа.</span><span class="sxs-lookup"><span data-stu-id="0b721-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="0b721-110">Этот метод отправляет на принтер объект <xref:System.Drawing.Graphics>, содержащийся в свойстве <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0b721-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="0b721-111">Пример, демонстрирующий печать текстового документа с помощью компонента <xref:System.Drawing.Printing.PrintDocument>, см. [в разделе Практические руководства. Печать многостраничного текстового файла в Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0b721-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="0b721-112">Более сложные задания печати, например ситуации, когда требуется повторное использование уже написанной логики печати.</span><span class="sxs-lookup"><span data-stu-id="0b721-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="0b721-113">В этом случае необходимо создать новый компонент из компонента <xref:System.Drawing.Printing.PrintDocument> и переопределить (см. Дополнительные сведения о [переопределениях](../../../visual-basic/language-reference/modifiers/overrides.md) Visual Basic или [переопределении](../../../csharp/language-reference/keywords/override.md) для C#) <xref:System.Drawing.Printing.PrintDocument.PrintPage> события.</span><span class="sxs-lookup"><span data-stu-id="0b721-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](../../../csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="0b721-114">При добавлении в форму <xref:System.Drawing.Printing.PrintDocument> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0b721-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b721-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b721-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="0b721-116">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b721-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="0b721-117">Компонент PrintDocument</span><span class="sxs-lookup"><span data-stu-id="0b721-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
