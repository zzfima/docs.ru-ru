---
title: Практическое руководство. Создание обработчиков событий во время выполнения для форм Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 7ebafd745290a40fa6f4f83910fb32d67cdcff75
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705272"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Практическое руководство. Создание обработчиков событий во время выполнения для форм Windows Forms
Помимо создания событий с помощью конструктора Windows Forms можно также создать обработчик событий во время выполнения. Это позволит подключать обработчики событий в зависимости от условий в коде во время выполнения, а не при начальном запуске программы.  
  
### <a name="to-create-an-event-handler-at-run-time"></a>Создание обработчика событий во время выполнения  
  
1.  Откройте форму в редакторе кода, в которую необходимо добавить обработчик событий.  
  
2.  Добавьте метод в форму с сигнатурой метода для события, которое будет необходимо обрабатывать.  
  
     Например, для обработки <xref:System.Windows.Forms.Control.Click> событие <xref:System.Windows.Forms.Button> элемента управления, необходимо создать метод, подобный следующему:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  Добавьте код в обработчик событий в зависимости от приложения.  
  
4.  Определите форму или элемент управления, для которого необходимо создать обработчик событий.  
  
5.  В методе внутри класса формы добавьте код, в соответствии с которым обработчик событий будет обрабатывать событие. Например, следующий код задает обработчик событий `button1_Click` дескрипторы <xref:System.Windows.Forms.Control.Click> событие <xref:System.Windows.Forms.Button> управления:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> Метод демонстрируется в приведенном выше коде Visual Basic, устанавливает обработчик событий щелчка для кнопки.  
  
## <a name="see-also"></a>См. также
- [Создание обработчиков событий в Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)
- [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
