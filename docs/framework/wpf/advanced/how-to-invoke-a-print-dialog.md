---
title: Практическое руководство. Вызов диалогового окна печати
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: f7ef3312d876324b44b055d70fd22e3fba075ec6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095181"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="d2f08-102">Практическое руководство. Вызов диалогового окна печати</span><span class="sxs-lookup"><span data-stu-id="d2f08-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="d2f08-103">Чтобы обеспечить возможность печати из приложения, можно просто создать и открыть объект <xref:System.Windows.Controls.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="d2f08-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2f08-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d2f08-104">Example</span></span>  
 <span data-ttu-id="d2f08-105">Элемент управления <xref:System.Windows.Controls.PrintDialog> предоставляет единую точку входа для отправки заданий [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], конфигурации и XPS.</span><span class="sxs-lookup"><span data-stu-id="d2f08-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and XPS job submission.</span></span> <span data-ttu-id="d2f08-106">Элемент управления легко использовать, и его можно создать с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметки или кода.</span><span class="sxs-lookup"><span data-stu-id="d2f08-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="d2f08-107">В следующем примере показано, как создать и открыть элемент управления в коде и как выполнить печать из него.</span><span class="sxs-lookup"><span data-stu-id="d2f08-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="d2f08-108">В нем также показано, как убедиться, что в диалоговом окне пользователь может задать конкретный диапазон страниц.</span><span class="sxs-lookup"><span data-stu-id="d2f08-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="d2f08-109">В примере кода предполагается, что в корне диска C: имеется файл FixedDocumentSequence. XPS.</span><span class="sxs-lookup"><span data-stu-id="d2f08-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="d2f08-110">После открытия диалогового окна пользователи смогут выбрать принтеры, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d2f08-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="d2f08-111">Кроме того, у них есть возможность выбрать [средство записи документов XPS Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer) для создания XPS-файла вместо печати.</span><span class="sxs-lookup"><span data-stu-id="d2f08-111">They will also have the option of selecting the [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer) to create an XML Paper Specification (XPS) file instead of printing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2f08-112"><xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> элемент управления WPF, который рассматривается в этом разделе, не следует путать с <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType>ным компонентом Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d2f08-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of WPF, which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="d2f08-113">Строго говоря, метод <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> можно использовать без открытия диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="d2f08-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="d2f08-114">В этом смысле элемент управления можно использовать как незамеченный компонент печати.</span><span class="sxs-lookup"><span data-stu-id="d2f08-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="d2f08-115">Но по соображениям производительности лучше использовать либо метод <xref:System.Printing.PrintQueue.AddJob%2A>, либо один из многих методов <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="d2f08-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="d2f08-116">Дополнительные сведения см. в разделе [Программная печать XPS-файлов](how-to-programmatically-print-xps-files.md) и.</span><span class="sxs-lookup"><span data-stu-id="d2f08-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f08-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2f08-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="d2f08-118">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="d2f08-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="d2f08-119">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="d2f08-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="d2f08-120">Средство записи документов XPS (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d2f08-120">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
