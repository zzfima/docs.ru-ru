---
title: "Практическое руководство. Печать прокручиваемой формы (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 380e0f833dc69718142809c99ed7615256dd2e73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a>Практическое руководство. Печать прокручиваемой формы (Visual Basic)
Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> позволяет быстро напечатать изображение формы без использования компонента <xref:System.Drawing.Printing.PrintDocument> . По умолчанию печатается только видимая часть формы; если пользователь изменил размер формы во время выполнения, изображение может быть напечатано неправильно. В следующей процедуре описана печать всей клиентской области прокручиваемой формы, даже если был изменен размер формы.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a>Печать всей клиентской области прокручиваемой формы  
  
1.  В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  В некоторых операционных системах текст или графика, нарисованная с использованием метода <xref:System.Drawing.Graphics> , могут быть напечатаны неправильно. В этом случае нельзя выполнить печать с использованием параметра `Scrollable` .  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [Компонент PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [Практическое руководство. Печать клиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [Практическое руководство. Печать клиентской и неклиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
