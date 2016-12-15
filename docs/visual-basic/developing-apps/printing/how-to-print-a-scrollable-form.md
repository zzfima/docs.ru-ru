---
title: "Практическое руководство. Печать прокручиваемой формы (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "целая форма, печать"
  - "прокручиваемая форма, печать"
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Печать прокручиваемой формы (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> позволяет быстро напечатать изображение формы без использования компонента <xref:System.Drawing.Printing.PrintDocument>. По умолчанию печатается только видимая часть формы; если пользователь изменил размер формы во время выполнения, изображение может быть напечатано неправильно. В следующей процедуре описана печать всей клиентской области прокручиваемой формы, даже если был изменен размер формы.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### Печать всей клиентской области прокручиваемой формы  
  
1.  В **панели элементов** щелкните вкладку **Visual Basic PowerPacks**, а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction>.  
  
3.  Добавьте следующий код в соответствующий обработчик событий \(например, в обработчик событий `Click` для **Print**`Button`\).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  В некоторых операционных системах текст или графика, нарисованная с использованием метода <xref:System.Drawing.Graphics>, могут быть напечатаны неправильно. В этом случае нельзя выполнить печать с использованием параметра `Scrollable`.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)   
 [Практическое руководство. Печать клиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [Практическое руководство. Печать клиентской и неклиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)