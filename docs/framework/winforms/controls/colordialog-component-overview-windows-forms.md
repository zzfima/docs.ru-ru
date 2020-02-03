---
title: Общие сведения о компоненте ColorDialog
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736961"
---
# <a name="colordialog-component-overview-windows-forms"></a>Общие сведения о компоненте ColorDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.ColorDialog> является предварительно настроенным диалоговым окном, позволяющим пользователю выбрать цвет из палитры и добавить пользовательские цвета в эту палитру. Это то же диалоговое окно, которое вы видите в других приложениях Windows для выбора цветов. Он используется в приложении Windows в качестве простого решения вместо настройки собственного диалогового окна.  
  
 Цвет, выбранный в диалоговом окне, возвращается в свойстве <xref:System.Windows.Forms.ColorDialog.Color%2A>. Если свойство <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> имеет значение `false`, кнопка "определить пользовательский цвет" будет отключена, а пользователь будет ограничен стандартными цветами палитры. Если свойство <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> имеет значение `true`, пользователь не может выбрать другие цвета. Чтобы отобразить диалоговое окно, необходимо вызвать его метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ColorDialog>
- [Компонент ColorDialog](colordialog-component-windows-forms.md)
- [Элементы управления и компоненты диалоговых окон](dialog-box-controls-and-components-windows-forms.md)
- [Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
