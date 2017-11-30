---
title: "Обзор обработчиков событий (Windows Forms)"
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
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7353f3ab4513d8331b1d38cb01ad16c7d3cde165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="event-handlers-overview-windows-forms"></a>Обзор обработчиков событий (Windows Forms)
Обработчик событий — метод, связанный с событием. При возникновении события выполняется код в обработчик событий. Каждый обработчик событий предоставляет два параметра, которые дают возможность правильно обработать событие. В примере показан обработчик событий для <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> событий.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 Первый параметр`sender`, предоставляющий ссылку на объект, создавший событие. Второй параметр `e`, в приведенном выше примере передает объект события, которое обрабатывается. С помощью ссылки на свойства объекта (и в некоторых случаях его методы), можно получить сведения, такие как расположение указателя мыши для событий мыши или данных, передаваемых в события перетаскивания и вставки.  
  
 Обычно каждое событие создает обработчик событий с типом другой объект события для второго параметра. Некоторые обработчики событий, такие как <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp> события, имеют одинаковый тип объекта для второго параметра. Для этих типов событий можно использовать один и тот же обработчик событий для обработки обоих событий.  
  
 Также можно использовать один и тот же обработчик событий для обработки одного события для различных элементов управления. Например, если существует группа <xref:System.Windows.Forms.RadioButton> элементов управления в форме, можно создать один обработчик событий для <xref:System.Windows.Forms.Control.Click> событий и каждого элемента управления <xref:System.Windows.Forms.Control.Click> привязки к одному обработчику событий. Дополнительные сведения см. в разделе [как: подключение нескольких событий к одному обработчику событий в Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>См. также  
 [Создание обработчиков событий в Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Общие сведения о событиях](../../../docs/framework/winforms/events-overview-windows-forms.md)
