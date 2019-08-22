---
title: Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7858ffd708c78d6397d533f613ccc2ea78d6cbed
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658526"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a>Пошаговое руководство. Размещение содержимого WPF на Windows Forms во время разработки

В этой статье показано, как использовать функции макета Windows Forms, такие как привязка и линии привязки, для упорядочения элементов управления Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Предварительные требования

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.

## <a name="create-the-project"></a>Создание проекта

Откройте Visual Studio и создайте новый проект Windows Forms приложения в Visual Basic или Visual C# с именем `ArrangeElementHost`.

> [!NOTE]
> При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.

## <a name="create-the-wpf-control"></a>Создание элемента управления WPF

После добавления в проект элемента управления WPF можно разместить его в форме.

1. Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>. Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`). Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF на Windows Forms во время](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)разработки.

2. Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.

3. В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.

4. Присвойте <xref:System.Windows.Controls.Control.Background%2A> свойству значение **Blue**.

5. Выполните построение проекта.

## <a name="host-wpf-controls-in-a-layout-panel"></a>Размещение элементов управления WPF на панели макета

Элементы управления WPF можно использовать на панели макета так же, как и другие элементы управления Windows Forms.

1. Откройте `Form1` в конструкторе Windows Forms.

2. В **области элементов**перетащите <xref:System.Windows.Forms.TableLayoutPanel> элемент управления на форму.

3. На панели смарт-тегов элементауправлениявыберитеудалитьпоследнюю<xref:System.Windows.Forms.TableLayoutPanel> строку.

4. Увеличьте высоту и ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.

5. В **области элементов**дважды щелкните `UserControl1` , чтобы `UserControl1` создать экземпляр в первой ячейке <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.

   Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.

6. В **области элементов**дважды щелкните `UserControl1` , чтобы создать другой экземпляр во <xref:System.Windows.Forms.TableLayoutPanel> второй ячейке элемента управления.

7. В окне **Структура документа** выберите `tableLayoutPanel1`.

8. В окне **Свойства** присвойте <xref:System.Windows.Forms.Control.Padding%2A> свойству значение **10, 10, 10, 10**.

   Размер обоих элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится в соответствии с новой структурой.

## <a name="use-snaplines-to-align-wpf-controls"></a>Использование линий привязки для выровняйте элементы управления WPF

Линии привязки позволяют легко выравнивать элементы управления в форме. Линии привязки также можно использовать для выравнивания элементов управления WPF. Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)помощью линий привязки.

1. Перетащите экземпляр `UserControl1` из **области элементов**в форму и поместите его в пространство под <xref:System.Windows.Forms.TableLayoutPanel> элементом управления.

   Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost3`.

2. С помощью линий привязки выровняйте левый край `elementHost3` относительно левого края элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.

3. С помощью линий привязки установите для `elementHost3` ту же ширину, что и для элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.

4. Перемещайте `elementHost3` в сторону элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления не появится центральная линия привязки.

5. В окне **Свойства** задайте для свойства Margin значение **20, 20, 20, 20**.

6. Перемещайте `elementHost3` от элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления снова не появится центральная линия привязки. Теперь центральная линия привязки указывает на поле шириной в 20 точек.

7. Перейти `elementHost3` вправо до тех пор, пока его левый элемент не будет сопоставлен с левым `elementHost1`ребром.

8. Изменяйте ширину элемента `elementHost3` до тех пор, пока его правый край не будет выровнен относительно правого края элемента управления `elementHost2`.

## <a name="anchor-and-dock-wpf-controls"></a>Привязка и закрепление элементов управления WPF

Поведение размещенного в форме элемента управления WPF при привязке и закреплении не отличается от поведения других элементов управления Windows Forms.

1. Выберите `elementHost1`.

2. В окне **Свойства** задайте <xref:System.Windows.Forms.Control.Anchor%2A> для свойства значение **сверху, снизу, слева, справа**.

3. Увеличьте размер элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.

   Элемент управления `elementHost1` заполнит всю ячейку.

4. Выберите `elementHost2`.

5. В окне **Свойства** присвойте <xref:System.Windows.Forms.Control.Dock%2A> свойству <xref:System.Windows.Forms.DockStyle.Fill>значение.

   Элемент управления `elementHost2` заполнит всю ячейку.

6. Выберите элемент управления <xref:System.Windows.Forms.TableLayoutPanel>.

7. Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Top>.

8. Выберите `elementHost3`.

9. Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

   Элемент управления `elementHost3` заполнит все оставшееся пространство в форме.

10. Измените размер формы.

    Размер всех трех элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится соответствующим образом.

    Дополнительные сведения см. в разделе [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)управления TableLayoutPanel.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Практическое руководство. Выровняйте элемент управления по краям форм во время разработки](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью линий привязки](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Миграция и взаимодействие систем](../../wpf/advanced/migration-and-interoperability.md)
- [Использование элементов управления WPF](using-wpf-controls.md)
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
