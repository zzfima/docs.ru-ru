---
title: Способы активации элемента управления Button в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 86ef0da37ec35b991557af97a97bc9ca3da2d68c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717262"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Способы активации элемента управления Button в Windows Forms
Кнопки Windows Forms можно выбрать следующими способами:  
  
-   Нажмите кнопку мышью.  
  
-   Вызвать кнопки <xref:System.Windows.Forms.Control.Click> событий в коде.  
  
-   Перемещение фокуса на кнопку, нажав клавишу TAB и нажмите кнопку "", нажав клавишу ПРОБЕЛ или ВВОД.  
  
-   Нажмите клавишу доступа (ALT + подчеркнутая буква) для кнопки. Дополнительные сведения о ключах доступа см. в разделе [как: Определение клавиш доступа для Windows Forms, элементы управления](how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Если кнопка является кнопкой «принять», формы, нажатие клавиши ВВОД активирует кнопку, даже если другой элемент управления имеет фокус, если этот элемент управления является кнопкой, многострочного текстового поля или пользовательский элемент управления, который перехватывает клавишу ВВОД.  
  
-   Если кнопка является кнопкой «Отмена» в формате, нажав клавишу ESC нажимает кнопку, даже если другой элемент управления имеет фокус.  
  
-   Вызовите <xref:System.Windows.Forms.Button.PerformClick%2A> метод программными средствами выберите кнопку.  
  
## <a name="see-also"></a>См. также
- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Практическое руководство. Ответ на нажатие кнопки Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Элемент управления Button](button-control-windows-forms.md)
