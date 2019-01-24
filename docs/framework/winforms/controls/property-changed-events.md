---
title: События изменения свойств
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: d02c6f6f3b5a3add7d78f6c3813a36d08b2b9cb3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584861"
---
# <a name="property-changed-events"></a>События изменения свойств
Если требуется, чтобы элемент управления для отправки уведомлений, когда свойство с именем *PropertyName* изменения, определите событие с именем *PropertyName* `Changed` и метод с именем `On` *PropertyName* `Changed` , генерирующий данное событие. Соглашение об именовании в Windows Forms — добавить слово *Changed* к имени свойства. Связанный тип делегата события для события изменения свойств является <xref:System.EventHandler>, и типом данных события является <xref:System.EventArgs>. Базовый класс <xref:System.Windows.Forms.Control> определяет много событий изменения свойств, таких как <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>и другие. Общие сведения о событиях, см. в разделе [события](../../../../docs/standard/events/index.md) и [события элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 События изменения свойств полезны, так как они позволяют пользователям элемента управления для присоединения обработчиков событий, которые реагируют на изменения. Если элемент управления должен реагировать на событие изменения свойства, которое, переопределите соответствующие `On` *PropertyName* `Changed` метод вместо присоединения делегата к событию. Элемент управления обычно отвечает на событие изменения свойства, обновляя другие свойства, либо некоторые или все его поверхности рисования.  
  
 В следующем примере показан как `FlashTrackBar` пользовательский элемент управления отвечает на некоторые события изменения свойств, которые он наследует от <xref:System.Windows.Forms.Control>. Полный пример см. в разделе [как: Создание элемента управления Windows Forms, показывающего прогресс](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>См. также
- [События](../../../../docs/standard/events/index.md)
- [События элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)
- [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
