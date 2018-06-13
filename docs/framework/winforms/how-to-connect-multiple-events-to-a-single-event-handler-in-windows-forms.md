---
title: Практическое руководство. Подключение несколько событий к одному обработчику в Windows Forms
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
ms.openlocfilehash: 527a76376a4c1d5ad051f4768ca2bd42c3548b3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538584"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Практическое руководство. Подключение несколько событий к одному обработчику в Windows Forms
При разработке приложения может оказаться необходимо использовать один обработчик событий для нескольких событий или несколькими событиями выполните ту же процедуру. Например часто бывает мощные время заставки иметь команды меню вызова того же события, как кнопки на форме, если они предоставляют те же функциональные возможности. Это можно сделать с помощью представления событий окна свойств в C# или `Handles` ключевое слово и **имя класса** и **имя метода** раскрывающихся списков в редакторе кода Visual Basic.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Чтобы подключить несколько событий к одному обработчику в Visual Basic  
  
1.  Щелкните форму правой кнопкой мыши и выберите **Просмотр кода**.  
  
2.  Из **имя класса** раскрывающегося списка, выберите один из элементов управления, которые требуется обработка обработчика событий.  
  
3.  Из **имя метода** раскрывающегося списка, выберите одно из событий, которые вы хотите обработчик событий для обработки.  
  
4.  Редактор кода вставляет соответствующий обработчик событий и помещает курсор в методе. В приведенном ниже примере это <xref:System.Windows.Forms.Control.Click> событий для <xref:System.Windows.Forms.Button> элемента управления.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Добавьте другие события, необходимо обработать для `Handles` предложения.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Добавьте соответствующий код в обработчик событий.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Чтобы подключить несколько событий к одному обработчику событий в C#  
  
1.  Выберите элемент управления, к которому требуется подключить обработчик событий.  
  
2.  В окне «Свойства» щелкните **событий** кнопки (![кнопка событий](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3.  Щелкните имя события, которое необходимо обработать.  
  
4.  В разделе значений рядом с именем события нажмите кнопку раскрывающегося списка для отображения списка существующих обработчиков событий, которые соответствуют сигнатуре метода события, которое необходимо обработать.  
  
5.  Выберите соответствующий обработчик событий из списка.  
  
     Для привязки события в существующий обработчик событий в форму будет добавлен код.  
  
## <a name="see-also"></a>См. также  
 [Создание обработчиков событий в Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Общие сведения об обработчиках событий](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
