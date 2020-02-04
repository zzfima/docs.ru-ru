---
title: Как создавать обработчики событий во время выполнения
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
ms.openlocfilehash: 0b496a3da77c5bcf7a08c435edba468a7c5809cb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739506"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Практическое руководство. Создание обработчиков событий для Windows Forms во время выполнения

Помимо создания событий с помощью конструктор Windows Forms в Visual Studio можно также создать обработчик событий во время выполнения. Это позволит подключать обработчики событий в зависимости от условий в коде во время выполнения, а не при начальном запуске программы.

## <a name="create-an-event-handler-at-run-time"></a>Создание обработчика событий во время выполнения

1. Откройте форму, в которую нужно добавить обработчик событий.

2. Добавьте метод в форму с сигнатурой метода для события, которое будет необходимо обрабатывать.

     Например, при обработке события <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> необходимо создать метод, подобный следующему:

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

5. В методе внутри класса формы добавьте код, в соответствии с которым обработчик событий будет обрабатывать событие. Например, следующий код указывает обработчик событий `button1_Click` обрабатывающий событие <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button>:

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     Метод <xref:System.ComponentModel.EventHandlerList.AddHandler%2A>, показанный в приведенном выше коде Visual Basic, устанавливает обработчик событий щелчка для кнопки.

## <a name="see-also"></a>См. также раздел

- [Создание обработчиков событий в Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)
- [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
