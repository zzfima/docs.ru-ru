---
title: Практическое руководство. Создание обработчиков событий для Windows Forms во время выполнения
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
ms.openlocfilehash: 440086bfd5384fc46aec2997dbdd9937f7a1b65f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964330"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Практическое руководство. Создание обработчиков событий для Windows Forms во время выполнения

Помимо создания событий с помощью конструктор Windows Forms в Visual Studio можно также создать обработчик событий во время выполнения. Это позволит подключать обработчики событий в зависимости от условий в коде во время выполнения, а не при начальном запуске программы.

## <a name="create-an-event-handler-at-run-time"></a>Создание обработчика событий во время выполнения

1. Откройте форму, в которую нужно добавить обработчик событий.

2. Добавьте метод в форму с сигнатурой метода для события, которое будет необходимо обрабатывать.

     Например, при обработке <xref:System.Windows.Forms.Control.Click> события <xref:System.Windows.Forms.Button> элемента управления необходимо создать метод, подобный следующему:

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

3. Добавьте код в обработчик событий в зависимости от приложения.

4. Определите форму или элемент управления, для которого необходимо создать обработчик событий.

5. В методе внутри класса формы добавьте код, в соответствии с которым обработчик событий будет обрабатывать событие. Например, следующий код указывает обработчик `button1_Click` событий, <xref:System.Windows.Forms.Control.Click> обрабатывающий событие <xref:System.Windows.Forms.Button> элемента управления:

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> Метод, показанный в приведенном выше коде Visual Basic, устанавливает обработчик событий нажатия для кнопки.

## <a name="see-also"></a>См. также

- [Создание обработчиков событий в Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)
- [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
