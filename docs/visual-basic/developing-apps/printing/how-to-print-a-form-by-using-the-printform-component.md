---
title: Как выполнить Печать формы с помощью компонента PrintForm (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
ms.openlocfilehash: 0a1a62627390c8839625862b9d43d61fc07ebf12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521573"
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a>Как выполнить Печать формы с помощью компонента PrintForm (Visual Basic)
Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> позволяет быстро напечатать изображение формы точно, как на экране, без использования компонента <xref:System.Drawing.Printing.PrintDocument> . Следующие процедуры показывают, как вывести форму для печати на принтер, в окно предварительного просмотра печати и в EPS-файл.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-a-form-to-the-default-printer"></a>Печать формы на принтере по умолчанию  
  
1.  В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a>Отображение формы в окне предварительного просмотра  
  
1.  В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.  
  
3.  Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a>Печать формы в файл  
  
1.  В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToFile>.  
  
3.  При необходимости выберите <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> и введите полный путь и имя целевого файла.  
  
     Если пропустить этот шаг, пользователю будет предложено ввести имя файла во время выполнения.  
  
4.  Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>
- [Практическое руководство. Печать клиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [Практическое руководство. Печать клиентской и неклиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
- [Практическое руководство. Печать прокручиваемой формы](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
- [Компонент PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)
