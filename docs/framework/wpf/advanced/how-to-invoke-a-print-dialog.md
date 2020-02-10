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
# <a name="how-to-invoke-a-print-dialog"></a>Практическое руководство. Вызов диалогового окна печати
Чтобы обеспечить возможность печати из приложения, можно просто создать и открыть объект <xref:System.Windows.Controls.PrintDialog>.  
  
## <a name="example"></a>Пример  
 Элемент управления <xref:System.Windows.Controls.PrintDialog> предоставляет единую точку входа для отправки заданий [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], конфигурации и XPS. Элемент управления легко использовать, и его можно создать с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметки или кода. В следующем примере показано, как создать и открыть элемент управления в коде и как выполнить печать из него. В нем также показано, как убедиться, что в диалоговом окне пользователь может задать конкретный диапазон страниц. В примере кода предполагается, что в корне диска C: имеется файл FixedDocumentSequence. XPS.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 После открытия диалогового окна пользователи смогут выбрать принтеры, установленные на компьютере. Кроме того, у них есть возможность выбрать [средство записи документов XPS Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer) для создания XPS-файла вместо печати.  
  
> [!NOTE]
> <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> элемент управления WPF, который рассматривается в этом разделе, не следует путать с <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType>ным компонентом Windows Forms.  
  
 Строго говоря, метод <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> можно использовать без открытия диалогового окна. В этом смысле элемент управления можно использовать как незамеченный компонент печати. Но по соображениям производительности лучше использовать либо метод <xref:System.Printing.PrintQueue.AddJob%2A>, либо один из многих методов <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> <xref:System.Windows.Xps.XpsDocumentWriter>. Дополнительные сведения см. в разделе [Программная печать XPS-файлов](how-to-programmatically-print-xps-files.md) и.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.PrintDialog>
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
- [Средство записи документов XPS (Майкрософт)](/windows/win32/printdocs/microsoft-xps-document-writer)
