---
title: Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: 0e565b56c31d0776f6e89bbbe0b0681ae184758e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922826"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a>Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel
Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> поддерживает свойства <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A> в своих дочерних элементах управления.  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a>Выравнивание дочернего элемента управления в ячейке TableLayoutPanel  
  
1. Создание элемента управления <xref:System.Windows.Forms.TableLayoutPanel> в форме.  
  
2. Присвойте свойствам <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> и <xref:System.Windows.Forms.TableLayoutPanel> <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> свойству элемента управления значение **1**.  
  
3. Создайте элемент управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>. Элемент <xref:System.Windows.Forms.Button> расположен в левом верхнем углу ячейки.  
  
4. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Left`. Элемент управления <xref:System.Windows.Forms.Button> выровняется по левому краю ячейки.  
  
    > [!NOTE]
    > Такое поведение отличается от поведения других контейнерных элементов управления. Когда свойству <xref:System.Windows.Forms.Control.Anchor%2A> присваивается значение<xref:System.Windows.Forms.Control.Anchor%2A>, дочерние элементы управления других контейнерных элементов управления не перемещаются, а расстояние между закрепленным элементом управления и границей родительского контейнера фиксируется.  
  
5. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Top, Left`. Элемент управления <xref:System.Windows.Forms.Button> займет левый верхний угол ячейки.  
  
6. Повторите шаг 5 со значением `Top, Right` , чтобы <xref:System.Windows.Forms.Button> переместить элемент управления в правый верхний угол ячейки. Повторите процедуру, используя значения `Bottom, Left` и `Bottom, Right`.  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a>Растяжение дочернего элемента управления в ячейке TableLayoutPanel  
  
1. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Left, Right`. Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он растянется по ширине ячейки.  
  
    > [!NOTE]
    > Такое поведение отличается от поведения других контейнерных элементов управления. В других элементах управления контейнера размер дочернего элемента управления не изменяется, <xref:System.Windows.Forms.Control.Anchor%2A> если свойство имеет `Left, Right` значение или `Top, Bottom`.  
  
2. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Top, Bottom`. Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он растянется по высоте ячейки.  
  
3. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Top, Bottom, Left, Right`. Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он заполнит ячейку.  
  
4. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `None`. Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он расположится по центру ячейки.  
  
5. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Dock%2A> на <xref:System.Windows.Forms.DockStyle.Left>. Элемент управления <xref:System.Windows.Forms.Button> выровняется по левому краю ячейки. Ширина элемента управления <xref:System.Windows.Forms.Button> сохранится, а высота изменится для заполнения ячейки по вертикали.  
  
    > [!NOTE]
    > Другие контейнерные элементы управления обладают аналогичным поведением.  
  
6. Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Dock%2A> на <xref:System.Windows.Forms.DockStyle.Fill>. Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он заполнит ячейку.  
  
## <a name="example"></a>Пример  
 На рисунке ниже показаны пять кнопок, прикрепленных в пяти отдельных ячейках <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Закрепление TableLayoutPanel](./media/vs-tlpanchor.gif "VS_TLPanchor")  
  
 На рисунке ниже показаны четыре кнопки, прикрепленные в углах четырех отдельных ячеек <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Закрепление TableLayoutPanel](./media/vs-tlpanchor2.gif "VS_TLPanchor2")  
  
 На рисунке ниже показаны три кнопки, растянутые в результате прикрепления в трех отдельных ячейках <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Закрепление TableLayoutPanel](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")  
  
 В примере кода ниже демонстрируются все сочетания значений свойств <xref:System.Windows.Forms.Control.Anchor%2A>, используемые для размещения элемента управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.TableLayoutPanel>
- [Элемент управления TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
