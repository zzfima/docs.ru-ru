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
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141696"
---
# <a name="event-handlers-overview-windows-forms"></a>Обзор обработчиков событий (Windows Forms)
Обработчик событий — это метод, связанный с событием. При поднятии события выполняется код в обработчике события. Каждый обработчик событий предоставляет два параметра, которые позволяют правильно обрабатывать событие. В следующем примере отображается <xref:System.Windows.Forms.Button> обработчик события для события элемента <xref:System.Windows.Forms.Control.Click> управления.  
  
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
  
 Первый параметр,`sender`обеспечивает ссылку на объект, который поднял событие. Второй параметр, `e`в приведенном выше примере, передает объект, специфичный для обрабатываемого события. Ссылаясь на свойства объекта (а иногда и его методы), можно получить информацию, такую как расположение мыши для событий мыши или данные, передаваемые в событиях перетаскивания.  
  
 Обычно каждое событие производит обработчик событий с другим типом объекта события для второго параметра. Некоторые обработчики событий, <xref:System.Windows.Forms.Control.MouseDown> например для событий и <xref:System.Windows.Forms.Control.MouseUp> событий, имеют один и тот же тип объекта для второго параметра. Для этих типов событий можно использовать один и тот же обработчик событий для обработки обоих событий.  
  
 Вы также можете использовать один и тот же обработчик событий для обработки одного и того же события для различных элементов управления. Например, если у вас <xref:System.Windows.Forms.RadioButton> есть группа элементов управления в форме, <xref:System.Windows.Forms.Control.Click> можно создать один <xref:System.Windows.Forms.Control.Click> обработчик событий и привязывать событие каждого элемента управления к одному обработчику событий. Для получения дополнительной информации [см. Как: Подключите несколько событий к обработчику одного события в формах Windows.](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
  
## <a name="see-also"></a>См. также раздел

- [Создание обработчиков событий в Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Общие сведения о событиях](events-overview-windows-forms.md)
