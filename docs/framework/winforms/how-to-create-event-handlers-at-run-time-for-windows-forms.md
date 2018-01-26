---
title: "Практическое руководство. Создание обработчиков событий для Windows Forms во время выполнения"
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
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a636e42c85ef3703a2831583aea9839e13effeaa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Практическое руководство. Создание обработчиков событий для Windows Forms во время выполнения
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
  
5.  В методе внутри класса формы добавьте код, в соответствии с которым обработчик событий будет обрабатывать событие. Например, следующий код определяет обработчик событий `button1_Click` дескрипторы <xref:System.Windows.Forms.Control.Click> событие <xref:System.Windows.Forms.Button> управления:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> Метод демонстрируется в приведенном выше коде Visual Basic устанавливает обработчик событий click для кнопки.  
  
## <a name="see-also"></a>См. также  
 [Создание обработчиков событий в Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Общие сведения об обработчиках событий](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
