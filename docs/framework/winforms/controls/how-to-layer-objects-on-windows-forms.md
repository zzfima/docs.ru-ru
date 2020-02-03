---
title: Создание слоев объектов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736338"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Как выполнять слои объектов на Windows Forms

При создании сложного пользовательского интерфейса или работе с формой многодокументного интерфейса (MDI) часто требуется послойировать как элементы управления, так и дочерние формы, чтобы создать более сложные пользовательские интерфейсы. Чтобы перемещать и контролировать элементы управления и окна в контексте группы, вы управляете их *z-порядком*. Z-порядок — это визуальное расположение элементов управления на форме вдоль оси z формы (глубина). Окно, расположенное в верхней части z-порядка, перекрывает все остальные окна. Все остальные окна перекрываются в нижней части z-порядка.

## <a name="to-layer-controls-at-design-time"></a>Для элементов управления "слой" во время разработки

1. В Visual Studio выберите элемент управления, который необходимо прослойировать.

2. В меню **Формат** выберите пункт **порядок**, а затем выберите команду **переместить на передний план** или **переместить на заднюю**.

## <a name="to-layer-controls-programmatically"></a>Программное управление слоями

Используйте методы <xref:System.Windows.Forms.Control.BringToFront%2A> и <xref:System.Windows.Forms.Control.SendToBack%2A>, чтобы управлять z-порядком элементов управления.

Например, если элемент управления <xref:System.Windows.Forms.TextBox>, `txtFirstName`, находится под другим элементом управления и требуется его поверх, используйте следующий код:

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> Windows Forms поддерживает *Включение элементов управления*. Включение элемента управления включает в себя размещение нескольких элементов управления внутри содержащего их элемента управления, например число элементов управления <xref:System.Windows.Forms.RadioButton> в элементе управления <xref:System.Windows.Forms.GroupBox>. Затем можно послойировать элементы управления внутри содержащего его элемента управления. Перемещение поля группы также приводит к перемещению элементов управления, так как они находятся внутри него.

## <a name="see-also"></a>См. также раздел

- [Элементы управления Windows Forms](index.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
