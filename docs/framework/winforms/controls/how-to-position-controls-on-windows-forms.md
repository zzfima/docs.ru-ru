---
title: Размещение элементов управления
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 144a0021c74f0fb5afec1d511315168fb28528e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735914"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Как располагать элементы управления на Windows Forms

Чтобы разместить элементы управления, используйте конструктор Windows Forms в Visual Studio или укажите свойство <xref:System.Windows.Forms.Control.Location%2A>.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Размещение элемента управления в области конструктора конструктор Windows Forms

В Visual Studio перетащите элемент управления в соответствующее место с помощью мыши.

> [!NOTE]
> Выберите элемент управления и переместите его с помощью клавиш со СТРЕЛКАми, чтобы более точно расположить его. Кроме того, *линии привязки* помогают точно разместить элементы управления в форме. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Размещение элемента управления с помощью окно свойств

1. В Visual Studio выберите элемент управления, который требуется разместить.

2. В окне **Свойства** введите значения для свойства <xref:System.Windows.Forms.Control.Location%2A>, разделенные запятыми, чтобы разместить элемент управления в контейнере.

   Первое число (X) — это расстояние от левой границы контейнера; второе число (Y) — это расстояние от верхней границы области контейнера, измеряемое в пикселях.

   > [!NOTE]
   > Можно развернуть свойство <xref:System.Windows.Forms.Control.Location%2A>, чтобы ввести значения **X** и **Y** по отдельности.

## <a name="position-a-control-programmatically"></a>Размещение элемента управления программным способом

1. Присвойте свойству <xref:System.Windows.Forms.Control.Location%2A> элемента управления значение <xref:System.Drawing.Point>.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Измените координату X расположения элемента управления с помощью подсвойства <xref:System.Windows.Forms.Control.Left%2A>.

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

Задайте подсвойство <xref:System.Windows.Forms.Control.Left%2A>, чтобы увеличить координату X элемента управления.

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
> Используйте свойство <xref:System.Windows.Forms.Control.Location%2A>, чтобы одновременно задать координаты X и Y элемента управления. Чтобы задать расположение по отдельности, используйте подсвойство <xref:System.Windows.Forms.Control.Left%2A> (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) элемента управления. Не пытайтесь неявно задать координаты X и Y структуры <xref:System.Drawing.Point>, представляющей расположение кнопки, так как эта структура содержит копию координат кнопки.

## <a name="see-also"></a>См. также:

- [Элементы управления Windows Forms](index.md)
- [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
- [Как задать расположение экрана Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
