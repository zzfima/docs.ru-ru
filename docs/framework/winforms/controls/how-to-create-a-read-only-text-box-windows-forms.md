---
title: Практическое руководство. Создать только для чтения текстовое поле (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 0a29e1c4dcb0bcc8e7d292725e64ea967e160d06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707759"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Практическое руководство. Создать только для чтения текстовое поле (Windows Forms)
Изменяемое поле текста в Windows Forms можно преобразовать в элемент управления только для чтения. Например текстовое поле может отобразить значение обычно изменяется, но в настоящее время не может быть из-за состояния приложения.  
  
### <a name="to-create-a-read-only-text-box"></a>Чтобы создать поле только для чтения текста  
  
1.  Задайте <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> свойства `true`. Со свойством, имеющим значение `true`, пользователи могут прокручивать и выделите текст в текстовом поле, не позволяя изменять. Объект **копирования** команда работает в текстовом поле, но **Вырезать** и **вставить** команд не.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Свойство оказывает влияние на взаимодействие с пользователем во время выполнения. По-прежнему изменением содержимого текстового поля программными средствами во время выполнения, изменив <xref:System.Windows.Forms.TextBox.Text%2A> свойства текстового поля.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления Windows Forms TextBox](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox в Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделите текст в элементе управления Windows Forms TextBox](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Просмотр нескольких строк в элементе управления Windows Forms TextBox](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
