---
title: События в элементах управления
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745751"
---
# <a name="events-in-windows-forms-controls"></a>События элементов управления Windows Forms
Windows Forms элемент управления наследует более 60 событий от <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. К ним относятся <xref:System.Windows.Forms.Control.Paint> событие, которое вызывает прорисовку элемента управления, события, связанные с отображением окна, такие как события <xref:System.Windows.Forms.Control.Resize> и <xref:System.Windows.Forms.Control.Layout>, а также события низкого уровня мыши и клавиатуры. Некоторые события низкого уровня синтезированы путем <xref:System.Windows.Forms.Control> в семантические события, такие как <xref:System.Windows.Forms.Control.Click> и <xref:System.Windows.Forms.Control.DoubleClick>. Дополнительные сведения о наследуемых событиях см. в разделе <xref:System.Windows.Forms.Control>.  
  
 Если для пользовательского элемента управления требуется переопределение функциональности наследуемых событий, переопределите наследуемый метод `On`*EventName*, а не присоединяйте делегат. Если вы не знакомы с моделью событий в .NET Framework, ознакомьтесь с разделом [Инициирование событий из компонента](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
## <a name="see-also"></a>См. также раздел

- [Переопределение метода OnPaint](overriding-the-onpaint-method.md)
- [Обработка введенных пользователем данных](handling-user-input.md)
- [Определение событий](defining-an-event-in-windows-forms-controls.md)
- [События](../../../standard/events/index.md)
