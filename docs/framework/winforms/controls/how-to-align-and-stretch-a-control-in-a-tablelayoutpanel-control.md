---
title: Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210366"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel

Вы можете выравнивание и Растягивание элементов управления в <xref:System.Windows.Forms.TableLayoutPanel> с <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A> свойства.

## <a name="align-and-stretch-a-control"></a>Выравнивание и Растягивание элемента управления

1. В Visual Studio перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.

2. Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в левый верхний угол объекта <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. <xref:System.Windows.Forms.Button> Элемент управления выравнивается по центру ячейки.

3. Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Left,Right`. <xref:System.Windows.Forms.Button> Управления растягивается по ширине ячейки.

4. Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Top,Bottom`. <xref:System.Windows.Forms.Button> Управления растягивается в соответствии с высотой ячейки.

5. Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>. <xref:System.Windows.Forms.Button> Элемент управления расширяется для заполнения ячейки.

6. Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.None>. <xref:System.Windows.Forms.Button> Управления возвращает становится равным исходному размеру и перемещает в левом верхнем углу ячейки. **Конструктор Windows Forms** задал <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Top, Left`.

7. Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Bottom,Right`. <xref:System.Windows.Forms.Button> Управления перемещается в правый нижний угол ячейки.

8. Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства <xref:System.Windows.Forms.AnchorStyles.None>. <xref:System.Windows.Forms.Button> Управления перемещается по центру ячейки.

## <a name="see-also"></a>См. также

- [Элемент управления TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
