---
title: Общие сведения об обработчиках событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743497"
---
# <a name="event-handlers-overview-windows-forms"></a>Обзор обработчиков событий (Windows Forms)
Обработчик событий — это метод, привязанный к событию. При возникновении события выполняется код в обработчике событий. Каждый обработчик событий предоставляет два параметра, которые позволяют правильно управлять событием. В следующем примере показан обработчик событий для <xref:System.Windows.Forms.Control.Click> события элемента управления <xref:System.Windows.Forms.Button>.  
  
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
  
 Первый параметр,`sender`, предоставляет ссылку на объект, который вызвал событие. Второй параметр, `e`, в приведенном выше примере передает объект, относящийся к обрабатываемому событию. Ссылаясь на свойства объекта (и иногда его методы), можно получить такие сведения, как расположение мыши для событий мыши или данных, передаваемых в событиях перетаскивания.  
  
 Обычно каждое событие создает обработчик событий с другим типом объекта события для второго параметра. Некоторые обработчики событий, например, для событий <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp>, имеют одинаковый тип объекта для второго параметра. Для этих типов событий можно использовать один и тот же обработчик событий для обработки обоих событий.  
  
 Можно также использовать один и тот же обработчик событий для обработки одного и того же события для различных элементов управления. Например, если в форме имеется группа элементов управления <xref:System.Windows.Forms.RadioButton>, можно создать один обработчик событий для <xref:System.Windows.Forms.Control.Click> события и связать событие <xref:System.Windows.Forms.Control.Click> каждого элемента управления с одним обработчиком событий. Дополнительные сведения см. [в разделе руководство. Подключение нескольких событий к одному обработчику событий в Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>См. также раздел

- [Создание обработчиков событий в Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Общие сведения о событиях](events-overview-windows-forms.md)
