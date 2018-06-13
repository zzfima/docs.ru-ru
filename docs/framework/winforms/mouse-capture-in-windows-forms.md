---
title: Захват мыши в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: dfe983b9e407eddb9bed3bcc1a767cdeff38f2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538412"
---
# <a name="mouse-capture-in-windows-forms"></a>Захват мыши в Windows Forms
*Захват мыши* называется элемента управления вводом все мыши. Элемент управления захватил мышь, получает ввод от мыши ли указатель мыши находится в пределах его границ.  
  
## <a name="setting-mouse-capture"></a>Установка захвата мыши  
 В Windows Forms мышь захвачена элементом управления, когда пользователь нажимает кнопку мыши на элементе управления и кнопка мыши была отпущена элементом управления, когда пользователь отпускает кнопку мыши.  
  
 <xref:System.Windows.Forms.Control.Capture%2A> Свойство <xref:System.Windows.Forms.Control> класс указывает, является ли мышь захвачена элементом. Чтобы определить, когда элемент управления теряет захват мыши, обработку <xref:System.Windows.Forms.Control.MouseCaptureChanged> событий.  
  
 Захватить мышь может только окно переднего плана. Если окна на задний план пытается захватить мышь, получит сообщения о событиях мыши, которые возникают, когда указатель мыши находится в видимой части окна. Кроме того даже если мышь захвачена окно переднего плана, пользователь может по-прежнему щелкнуть другое окно, ее перевод на передний план. При захвате мыши сочетания клавиш не работают.  
  
## <a name="see-also"></a>См. также  
 [Ввод данных мышью в приложении Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
