---
title: Практическое руководство. Размещение элементов управления в формах Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1cc2cb4c749b7290a6edf914a8e6a697006ef43c
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987070"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Практическое руководство. Располагать элементы управления на Windows Forms

Чтобы разместить элементы управления, используйте конструктор Windows Forms в Visual Studio или укажите <xref:System.Windows.Forms.Control.Location%2A> свойство.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Размещение элемента управления в области конструктора конструктор Windows Forms

В Visual Studio перетащите элемент управления в соответствующее место с помощью мыши.

> [!NOTE]
> Выберите элемент управления и переместите его с помощью клавиш со СТРЕЛКАми, чтобы более точно расположить его. Кроме того, *линии привязки* помогают точно разместить элементы управления в форме. Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)помощью линий привязки.

## <a name="position-a-control-using-the-properties-window"></a>Размещение элемента управления с помощью окно свойств

1. В Visual Studio выберите элемент управления, который требуется разместить.

2. В окне **Свойства** введите значения для <xref:System.Windows.Forms.Control.Location%2A> свойства, разделенные запятыми, чтобы разместить элемент управления в контейнере.

   Первое число (X) — это расстояние от левой границы контейнера; второе число (Y) — это расстояние от верхней границы области контейнера, измеряемое в пикселях.

   > [!NOTE]
   > Можно развернуть <xref:System.Windows.Forms.Control.Location%2A> свойство, чтобы ввести значения **X** и **Y** по отдельности.

## <a name="position-a-control-programmatically"></a>Размещение элемента управления программным способом

1. <xref:System.Drawing.Point>Присвойте <xref:System.Windows.Forms.Control.Location%2A> свойству элемента управления значение.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Измените координату X расположения элемента управления с помощью <xref:System.Windows.Forms.Control.Left%2A> подсвойства.

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a>Программное увеличение расположения элемента управления

<xref:System.Windows.Forms.Control.Left%2A> Задайте подсвойство, чтобы увеличить координату X элемента управления.

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <xref:System.Windows.Forms.Control.Location%2A> Используйте свойство, чтобы одновременно задать координаты X и Y элемента управления. Чтобы задать расположение по отдельности, используйте подсвойство <xref:System.Windows.Forms.Control.Left%2A> (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) элемента управления. Не пытайтесь неявно задать координаты <xref:System.Drawing.Point> X и Y структуры, представляющей расположение кнопки, так как эта структура содержит копию координат кнопки.

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
- [Практическое руководство. Задайте расположение экрана Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
