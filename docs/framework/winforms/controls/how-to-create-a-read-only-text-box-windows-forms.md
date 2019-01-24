---
title: Как выполнить Создать только для чтения текстовое поле (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 89d331f6c7fad5880aff031eb808199292e493a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670346"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Как выполнить Создать только для чтения текстовое поле (Windows Forms)
Изменяемое поле текста в Windows Forms можно преобразовать в элемент управления только для чтения. Например текстовое поле может отобразить значение обычно изменяется, но в настоящее время не может быть из-за состояния приложения.  
  
### <a name="to-create-a-read-only-text-box"></a>Чтобы создать поле только для чтения текста  
  
1.  Задайте <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> свойства `true`. Со свойством, имеющим значение `true`, пользователи могут прокручивать и выделите текст в текстовом поле, не позволяя изменять. Объект **копирования** команда работает в текстовом поле, но **Вырезать** и **вставить** команд не.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Свойство оказывает влияние на взаимодействие с пользователем во время выполнения. По-прежнему изменением содержимого текстового поля программными средствами во время выполнения, изменив <xref:System.Windows.Forms.TextBox.Text%2A> свойства текстового поля.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления Windows Forms TextBox](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделите текст в элементе управления Windows Forms TextBox](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Просмотр нескольких строк в элементе управления Windows Forms TextBox](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
