---
title: Способы выбора элемента управления Button
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740006"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Способы активации элемента управления Button в Windows Forms
Кнопку Windows Forms можно выбрать следующими способами.  
  
- Используйте мышь для нажатия кнопки.  
  
- Вызов события <xref:System.Windows.Forms.Control.Click> кнопки в коде.  
  
- Переместите фокус на кнопку, нажав клавишу TAB, а затем нажмите клавишу пробел или ввод.  
  
- Нажмите клавишу доступа (ALT + подчеркнутая буква) для кнопки. Дополнительные сведения о ключах доступа см. [в разделе как создать ключи доступа для элементов управления Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
- Если кнопка «Accept» («принять») является кнопкой формы, нажатие клавиши Ввод нажимает кнопку, даже если фокус находится на другом элементе управления, за исключением того, что другой элемент управления является другой кнопкой, многострочным текстовым полем или пользовательским элементом управления, который захватывает клавишу ВВОД.  
  
- Если кнопка в форме отменена, нажатие клавиши ESC нажимает кнопку, даже если фокус находится на другом элементе управления.  
  
- Вызовите метод <xref:System.Windows.Forms.Button.PerformClick%2A>, чтобы программно нажать кнопку.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Элемент управления Button](button-control-windows-forms.md)
