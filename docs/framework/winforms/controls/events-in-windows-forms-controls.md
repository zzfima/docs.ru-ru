---
title: События элементов управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: dfbac71335615af52de3b5862c4058981f965654
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720807"
---
# <a name="events-in-windows-forms-controls"></a>События элементов управления Windows Forms
Элемент управления Windows Forms наследует более шестидесяти событий <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. К ним относятся <xref:System.Windows.Forms.Control.Paint> событие, которое вызывает в элементе управления для отрисовки, события, связанные с отображением окна, такие как <xref:System.Windows.Forms.Control.Resize> и <xref:System.Windows.Forms.Control.Layout> события и низкоуровневые события мыши и клавиатуры. Некоторые низкоуровневые события синтезируются элементом <xref:System.Windows.Forms.Control> в семантические события, такие как <xref:System.Windows.Forms.Control.Click> и <xref:System.Windows.Forms.Control.DoubleClick>. Дополнительные сведения о наследуемых событиях см. в разделе <xref:System.Windows.Forms.Control>.  
  
 Если для пользовательского элемента управления требуется переопределение функциональности наследуемых событий, переопределите наследуемый метод `On` *EventName*, а не присоединяйте делегат. Если вы не знакомы с моделью событий в .NET Framework, ознакомьтесь с разделом [Инициирование событий из компонента](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
## <a name="see-also"></a>См. также
- [Переопределение метода OnPaint](overriding-the-onpaint-method.md)
- [Обработка введенных пользователем данных](handling-user-input.md)
- [Определение событий](defining-an-event-in-windows-forms-controls.md)
- [События](../../../standard/events/index.md)
