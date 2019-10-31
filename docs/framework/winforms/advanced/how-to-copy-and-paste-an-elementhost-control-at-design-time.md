---
title: Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3d1887eb1161f714962c2c26d6fe618749b26c0f
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197481"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Как копировать и вставить элемент управления ElementHost

В этой процедуре показано, как скопировать элемент управления Windows Presentation Foundation (WPF) в форму Windows в Visual Studio.

1. В Visual Studio добавьте новый <xref:System.Windows.Controls.UserControl> WPF в проект Windows Forms. Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`). Дополнительные сведения см. в разделе [Пошаговое руководство. Создание нового содержимого WPF на Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> `UserControl1` значение **200**.

3. Присвойте свойству <xref:System.Windows.Controls.Control.Background%2A> значение **Blue**.

4. Выполните построение проекта.

5. Откройте `Form1` в конструкторе Windows Forms.

6. Из **панели элементов**перетащите экземпляр `UserControl1` на форму.

   Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.

7. Выбрав `elementHost1`, нажмите клавиши **Ctrl**+**C** , чтобы скопировать его в буфер обмена.

8. Нажмите клавиши **Ctrl**+**V** , чтобы вставить скопированный элемент управления на форму.

   В форме создается новый элемент управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost2`.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Миграция и взаимодействие систем](../../wpf/advanced/migration-and-interoperability.md)
- [Использование элементов управления WPF](using-wpf-controls.md)
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
