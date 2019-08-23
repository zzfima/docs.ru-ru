---
title: Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960629"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms
Проводник Windows — это общий вариант пользовательского интерфейса для приложений из-за его готовности.

 Проводник Windows — это, по сути <xref:System.Windows.Forms.TreeView> , элемент управления <xref:System.Windows.Forms.ListView> и элемент управления на отдельных панелях. Размеры панелей преобразуются в один и тот же разделитель. Такое размещение элементов управления очень эффективно для отображения и просмотра информации.

 Ниже показано, как упорядочивать элементы управления в форме, похожей на проводник Windows. Они не показывают, как добавить функции просмотра файлов в приложении проводника Windows.

## <a name="to-create-a-windows-explorer-style-windows-form"></a>Создание Windows Form в стиле проводника Windows

1. Создание нового проекта приложения Windows (**файл** > **создать** > **проект** > **визуальный C#**  элемент или **Visual Basic** > **классический рабочий стол**  > ) **Windows Forms приложение**).

2. Из **области элементов**:

    1. <xref:System.Windows.Forms.SplitContainer> Перетащите элемент управления на форму.

    2. Перетащите элемент управления в **SplitterPanel1** (панель <xref:System.Windows.Forms.SplitContainer> элемента управления с меткой Panel1). <xref:System.Windows.Forms.TreeView>

    3. Перетащите элемент управления в **SplitterPanel2** (панель <xref:System.Windows.Forms.SplitContainer> элемента управления с пометкой Panel2). <xref:System.Windows.Forms.ListView>

3. Выберите все три элемента управления, нажав клавишу CTRL и щелкнув их по очереди. При выборе <xref:System.Windows.Forms.SplitContainer> элемента управления щелкните линию разделения, а не панели.

    > [!NOTE]
    > Не используйте команду **выбрать все** в меню **Правка** . В этом случае свойство, необходимое на следующем шаге, не будет отображаться в окне **Свойства** .

4. В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

5. Нажмите клавишу F5 для запуска приложения.

     В этой форме представлен пользовательский интерфейс с двумя частями, аналогичный проводнику Windows.

    > [!NOTE]
    > При перетаскивании разделителя размеры панелей изменяются самим.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.SplitContainer>
- [Практическое руководство. Создание пользовательского интерфейса с несколькими панелями с помощью Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [Практическое руководство. Определение поведения изменения размера и позиционирования в окне с разделением](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [Практическое руководство. Разделение окна по горизонтали](how-to-split-a-window-horizontally.md)
- [Элемент управления SplitContainer](splitcontainer-control-windows-forms.md)
