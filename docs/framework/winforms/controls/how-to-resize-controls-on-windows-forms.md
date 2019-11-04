---
title: Практическое руководство. Изменение размера элементов управления в формах Windows Forms
ms.date: 03/30/2017
f1_keywords:
- Size.Height
- Size.Width
helpviewer_keywords:
- controls [Windows Forms], resizing
- size [Windows Forms], controls
- Windows Forms controls, size
ms.assetid: d2dba441-a8c0-4705-b8e8-2e5d86d6e7ec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3aacc9434199eb7881e362a67e1fe0c08784c4a7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459551"
---
# <a name="how-to-resize-controls-on-windows-forms"></a>Как изменить размер элементов управления на Windows Forms

Можно изменить размер отдельных элементов управления, а также изменить размер нескольких элементов управления одного вида, например <xref:System.Windows.Forms.Button> и элементов управления <xref:System.Windows.Forms.GroupBox>.

## <a name="to-resize-a-control"></a>Изменение размера элемента управления

В Visual Studio выберите элемент управления, размер которого нужно изменить, и перетащите один из восьми маркеров изменения размера.

> [!NOTE]
> Выберите элемент управления и нажмите клавиши **со стрелками** , удерживая нажатой клавишу **SHIFT** , чтобы изменить размер элемента управления на один пиксель за раз. Нажмите клавишу **стрелка вниз** или клавишу **со стрелкой вправо** , удерживая нажатыми клавиши **SHIFT** и **CTRL** , чтобы изменить размер элемента управления с большим шагом.

## <a name="to-resize-multiple-controls-on-a-form"></a>Изменение размера нескольких элементов управления в форме

1. В Visual Studio удерживайте нажатой клавишу **CTRL** или **SHIFT** и выберите элементы управления, размер которых необходимо изменить. Размер первого выбранного элемента управления используется для других элементов управления.

2. В меню **Формат** выберите пункт **сделать тот же размер**и выберите один из четырех параметров. Первые три команды изменяют размеры элементов управления в соответствии с первым выбранным элементом управления.

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
- [Инструкции. изменение размера Windows Forms с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))
