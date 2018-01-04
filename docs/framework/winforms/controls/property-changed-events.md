---
title: "События изменения свойств"
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
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad22d77043f00ab0caaa6d8b08b6b0a9eef1fed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="property-changed-events"></a>События изменения свойств
Если требуется, чтобы элемент управления для отправки уведомлений, когда свойство с именем *PropertyName* изменения, определите событие с именем *PropertyName* `Changed` и метод с именем `On` *PropertyName* `Changed` , вызывает событие. Соглашение об именовании в Windows Forms — добавить слово *Changed* к имени свойства. Связанный тип делегата события для события изменения свойств является <xref:System.EventHandler>, и тип данных события является <xref:System.EventArgs>. Базовый класс <xref:System.Windows.Forms.Control> определяет многие события изменения свойства, такие как <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>и др. Дополнительные сведения о событиях см. в разделе [событий](../../../../docs/standard/events/index.md) и [события элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 События изменения свойств полезны, потому что они позволяют пользователям элемента управления присоединять обработчики событий, реагирующие на изменения. Если элемент управления должен реагировать на событие изменения свойства, которое его вызывает, переопределите соответствующий `On` *PropertyName* `Changed` вместо присоединения делегата к событию. Элемент управления обычно отвечает на событие изменения свойства, обновляя другие свойства, либо все или некоторые из его поверхности.  
  
 В следующем примере показан способ `FlashTrackBar` пользовательский элемент управления отвечает на некоторые события изменения свойств, которые он наследует от <xref:System.Windows.Forms.Control>. Полный пример см. в разделе [как: создание Windows Forms элемента управления, показывает ход выполнения](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [События](../../../../docs/standard/events/index.md)  
 [События элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
