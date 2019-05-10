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
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211654"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Практическое руководство. Размещение элементов управления в формах Windows Forms

Размещение элементов управления, использовать конструктор Windows Forms в Visual Studio или задайте <xref:System.Windows.Forms.Control.Location%2A> свойство.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Разместить элемент управления в области конструктора в конструкторе Windows Forms

В Visual Studio перетащите элемент управления в соответствующее место с помощью мыши.

> [!NOTE]
> Выберите элемент управления и переместите его с помощью стрелки клавиш со стрелками для более точно. Кроме того *линии привязки* помочь для точного размещения. Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочение элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Положение элемента управления, с помощью окна свойств

1. В Visual Studio щелкните элемент управления, который можно разместить.

2. В **свойства** окне значения типов <xref:System.Windows.Forms.Control.Location%2A> свойств, разделенных запятыми, чтобы разместить элемент управления внутри контейнера.

     Первое число (X) является расстоянием от левой границы контейнера; второе число (Y) — это расстояние от верхней границы области контейнера, измеряется в пикселах.

    > [!NOTE]
    > Вы можете развернуть <xref:System.Windows.Forms.Control.Location%2A> свойство в тип **X** и **Y** отдельно.

## <a name="position-a-control-programmatically"></a>Поместите элемент управления программными средствами

1. Задайте <xref:System.Windows.Forms.Control.Location%2A> свойство элемента управления, <xref:System.Drawing.Point>.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Измените значение координаты X местоположения элемента управления с помощью <xref:System.Windows.Forms.Control.Left%2A> подсвойства.

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a>Увеличить расположение элемента управления программными средствами

Задайте <xref:System.Windows.Forms.Control.Left%2A> подсвойств координату X элемента управления.

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
> Используйте <xref:System.Windows.Forms.Control.Location%2A> одновременно помещает свойства X и Y элемента управления. Чтобы задать положение по отдельности, используйте элемент управления <xref:System.Windows.Forms.Control.Left%2A> (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) подсвойства. Не пытайтесь неявным образом значение координаты X и Y <xref:System.Drawing.Point> структура, представляющая расположение кнопки, так как эта структура содержит копию координат кнопки.

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Пошаговое руководство: Упорядочение элементов управления в формах Windows Forms, с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Упорядочение элементов управления в формах Windows Forms](arranging-controls-on-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
- [Практическое руководство. Задание расположения экрана Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
