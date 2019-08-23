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
ms.openlocfilehash: cd7b06030e0fb2bba74590ee80c07c34047c5b47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950612"
---
# <a name="how-to-invoke-a-print-dialog"></a>Практическое руководство. Вызов диалогового окна печати
Чтобы обеспечить возможность печати из приложения, можно просто создать и открыть <xref:System.Windows.Controls.PrintDialog> объект.  
  
## <a name="example"></a>Пример  
 Элемент управления <xref:System.Windows.Controls.PrintDialog> предоставляет единую точку входа для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], конфигурации и отправки задания [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Элемент управления легко использовать, и его можно создать с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметки или кода. В следующем примере показано, как создать и открыть элемент управления в коде и как выполнить печать из него. В нем также показано, как убедиться, что в диалоговом окне пользователь может задать конкретный диапазон страниц. В примере кода предполагается, что в корне диска C: имеется файл FixedDocumentSequence. XPS.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 После открытия диалогового окна пользователи смогут выбрать принтеры, установленные на компьютере. Они также смогут выбрать [средство записи документов XPS Microsoft](https://go.microsoft.com/fwlink/?LinkId=147319) для создания [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] файла вместо печати.  
  
> [!NOTE]
> Элемент управления, который рассматривается в этом разделе, <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> не следует путать с компонентом Windows Forms. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>  
  
 Строго говоря, <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> метод можно использовать без открытия диалогового окна. В этом смысле элемент управления можно использовать как незамеченный компонент печати. Но по соображениям <xref:System.Printing.PrintQueue.AddJob%2A> производительности лучше использовать либо метод, либо один из множества <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> методов <xref:System.Windows.Xps.XpsDocumentWriter>и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> . Дополнительные сведения см. в разделе [Программная печать XPS-файлов](how-to-programmatically-print-xps-files.md) и.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.PrintDialog>
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
- [Средство записи документов XPS (Майкрософт)](https://go.microsoft.com/fwlink/?LinkId=147319)
