---
title: Создание стандартных рабочих мест для печати
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182570"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Практическое руководство. Создание стандартных задания печати в Windows Forms
Основой печати в формах <xref:System.Drawing.Printing.PrintDocument> Windows является компонент, в частности, <xref:System.Drawing.Printing.PrintDocument.PrintPage> событие. Написав код для <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработки события, можно указать, что печатать и как его распечатать.  
  
### <a name="to-create-a-print-job"></a>Для создания задания печати  
  
1. Добавьте <xref:System.Drawing.Printing.PrintDocument> компонент в форму.  
  
2. Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Вам придется кодировать свою собственную логику печати. Кроме того, вы должны будете указать материал, который будет напечатан.  
  
     В следующем примере кода образец изображения в форме красного прямоугольника создается в обработчике <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий, чтобы выступать в качестве материала, который будет напечатан.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Визуальный C и Визуальный C ) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     Вы также можете написать <xref:System.Drawing.Printing.PrintDocument.BeginPrint> код <xref:System.Drawing.Printing.PrintDocument.EndPrint> для событий и событий, возможно, включая целый ряд, представляющий общее количество страниц для печати, которые decremented как каждая страница печатает.  
  
    > [!NOTE]
    > Вы можете <xref:System.Windows.Forms.PrintDialog> добавить компонент в форму, чтобы обеспечить пользователям чистый и эффективный пользовательский интерфейс (Пользовательского интерфейса). Установка <xref:System.Windows.Forms.PrintDialog.Document%2A> свойства <xref:System.Windows.Forms.PrintDialog> компонента позволяет устанавливать свойства, связанные с печатным документом, с которым вы работаете, на вашей форме. Для получения дополнительной <xref:System.Windows.Forms.PrintDialog> информации о компоненте, см [PrintDialog Компонент](../controls/printdialog-component-windows-forms.md).  
  
     Для получения дополнительной информации о специфике Windows Формы печати рабочих мест, <xref:System.Drawing.Printing.PrintPageEventArgs>в том числе, как создать работу печати программно, см.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](windows-forms-print-support.md)
