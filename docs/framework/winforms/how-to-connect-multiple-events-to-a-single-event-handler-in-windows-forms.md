---
title: Как подключить несколько событий к одному обработчику событий
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739604"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Практическое руководство. Подключение несколько событий к одному обработчику в Windows Forms
В структуре приложения может оказаться необходимым использовать один обработчик событий для нескольких событий или несколько событий выполняют одну и ту же процедуру. Например, зачастую очень мощная временная заставка для того, чтобы команда меню вызывала то же самое событие, что и кнопка в форме, если они предоставляют те же функциональные возможности. Это можно сделать с помощью представления событий окно свойств в C# или с `Handles` помощью раскрывающихся списков **имя класса** и **имя метода** в Visual Basic редакторе кода.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Подключение нескольких событий к одному обработчику событий в Visual Basic  
  
1. Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.  
  
2. В раскрывающемся списке **имя класса** выберите один из элементов управления, для которых требуется дескриптор обработчика событий.  
  
3. В раскрывающемся списке **имя метода** выберите одно из событий, которое должен обработать обработчик событий.  
  
4. Редактор кода вставляет соответствующий обработчик событий и размещает точку вставки в методе. В приведенном ниже примере это событие <xref:System.Windows.Forms.Control.Click> для элемента управления <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. Добавьте другие события, которые вы хотите обработать, в предложение `Handles`.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. Добавьте соответствующий код в обработчик событий.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Подключение нескольких событий к одному обработчику событий в C\#
  
1. Выберите элемент управления, к которому необходимо подключить обработчик событий.  
  
2. В окно свойств нажмите кнопку **события** (![кнопка события](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3. Щелкните имя события, которое требуется обработать.  
  
4. В разделе значение рядом с именем события нажмите кнопку раскрывающегося списка, чтобы отобразить список существующих обработчиков событий, соответствующих сигнатуре метода события, которое требуется обработать.  
  
5. Выберите из списка соответствующий обработчик событий.  
  
     Код будет добавлен в форму для привязки события к существующему обработчику событий.  
  
## <a name="see-also"></a>См. также раздел

- [Создание обработчиков событий в Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)
