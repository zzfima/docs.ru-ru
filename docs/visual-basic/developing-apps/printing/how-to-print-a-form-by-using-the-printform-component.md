---
title: "Практическое руководство. Печать формы с помощью компонента PrintForm (Visual Basic) | Microsoft Docs"
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
  - "форма, печать"
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Печать формы с помощью компонента PrintForm (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> позволяет быстро напечатать изображение формы точно, как на экране, без использования компонента <xref:System.Drawing.Printing.PrintDocument>. Следующие процедуры показывают, как вывести форму для печати на принтер, в окно предварительного просмотра печати и в EPS\-файл.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### Печать формы на принтере по умолчанию  
  
1.  В **панели элементов** щелкните вкладку **Visual Basic PowerPacks**, а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction>.  
  
3.  Добавьте следующий код в соответствующий обработчик событий \(например, в обработчик событий `Click` для **Print**`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### Отображение формы в окне предварительного просмотра  
  
1.  В **панели элементов** щелкните вкладку **Visual Basic PowerPacks**, а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction>.  
  
3.  Добавьте следующий код в соответствующий обработчик событий \(например, в обработчик событий `Click` для **Print**`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### Печать формы в файл  
  
1.  В **панели элементов** щелкните вкладку **Visual Basic PowerPacks**, а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.  
  
     Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.  
  
2.  В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction>.  
  
3.  При необходимости выберите <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> и введите полный путь и имя целевого файла.  
  
     Если пропустить этот шаг, пользователю будет предложено ввести имя файла во время выполнения.  
  
4.  Добавьте следующий код в соответствующий обработчик событий \(например, в обработчик событий `Click` для **Print**`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>   
 [Практическое руководство. Печать клиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [Практическое руководство. Печать клиентской и неклиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)   
 [Практическое руководство. Печать прокручиваемой формы](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)