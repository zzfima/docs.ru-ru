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
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666181"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Практическое руководство. Копирование и вставка элемента управления ElementHost

В этой процедуре показано, как скопировать элемент управления Windows Presentation Foundation (WPF) в форму Windows в Visual Studio.

1. В Visual Studio добавьте новый WPF <xref:System.Windows.Controls.UserControl> в проект Windows Forms. Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`). Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF на Windows Forms во время](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)разработки.

2. В окне **Свойства** задайте <xref:System.Windows.FrameworkElement.Width%2A> `UserControl1` для свойств и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.

3. Присвойте <xref:System.Windows.Controls.Control.Background%2A> свойству значение **Blue**.

4. Выполните построение проекта.

5. Откройте `Form1` в конструкторе Windows Forms.

6. Из **панели элементов**перетащите экземпляр `UserControl1` в форму.

   Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.

7. Выбрав "+ выбрано", нажмите клавиши CTRL C, чтобы скопировать его в буфер обмена. `elementHost1`

8. Нажмите клавиши **CTRL +** +, чтобы вставить скопированный элемент управления на форму.

   В форме <xref:System.Windows.Forms.Integration.ElementHost> будет создан `elementHost2` новый элемент управления с именем.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Миграция и взаимодействие систем](../../wpf/advanced/migration-and-interoperability.md)
- [Использование элементов управления WPF](using-wpf-controls.md)
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
