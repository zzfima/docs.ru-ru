---
title: Добавление и удаление узлов с помощью элемента управления TreeView в конструкторе
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732251"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление узлов с использованием элемента управления TreeView в формах Windows Forms с помощью конструктора

Поскольку элемент управления Windows Forms <xref:System.Windows.Forms.TreeView> отображает узлы иерархически, при добавлении узла необходимо обратить внимание на то, что имеет его родительский узел.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.TreeView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-nodes-in-the-designer"></a>Добавление или удаление узлов в конструкторе

1. Выберите элемент управления <xref:System.Windows.Forms.TreeView>.

2. В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.TreeView.Nodes%2A>.

     Откроется **Редактор TreeNode** .

3. Для добавления узлов должен существовать корневой узел. Если он не существует, необходимо сначала добавить корень, нажав кнопку **Добавить корень** . Затем можно добавить дочерние узлы, выбрав корень или любой другой узел и нажав кнопку **Добавить дочерний** элемент.

4. Чтобы удалить узлы, выберите узел для удаления и нажмите кнопку **Удалить** .

## <a name="see-also"></a>См. также раздел

- [Элемент управления TreeView](treeview-control-windows-forms.md)
- [Общие сведения об элементе управления TreeView](treeview-control-overview-windows-forms.md)
- [Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
