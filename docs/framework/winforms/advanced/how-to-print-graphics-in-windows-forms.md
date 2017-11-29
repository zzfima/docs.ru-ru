---
title: "Практическое руководство. Печать графических изображений в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5f495135b3210f430c887451844bec8b154db33c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Практическое руководство. Печать графических изображений в Windows Forms
Как правило требуется печать графических изображений в приложении Windows. <xref:System.Drawing.Graphics> Класс предоставляет методы для рисования объектов на устройствах, таких как экран или принтер.  
  
### <a name="to-print-graphics"></a>Для печати графики  
  
1.  Добавить <xref:System.Drawing.Printing.PrintDocument> форму компонента.  
  
2.  В <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчик событий, используйте <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> свойство <xref:System.Drawing.Printing.PrintPageEventArgs> класса, чтобы дать указание принтера на какой тип графики для печати.  
  
     В следующем примере кода показан обработчик событий, используемый для создания синего эллипса внутри ограничивающего прямоугольника. Прямоугольник имеет следующее расположение и размеры: начиная от 100, 150 с шириной 250 и высотой 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [Поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
