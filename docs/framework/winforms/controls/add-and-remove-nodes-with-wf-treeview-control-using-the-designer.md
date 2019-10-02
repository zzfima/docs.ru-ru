---
title: Практическое руководство. Добавление и удаление узлов с использованием элемента управления TreeView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ef3a963b5621f0b972b02a007681f600fbdb1050
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040077"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление узлов с использованием элемента управления TreeView в формах Windows Forms с помощью конструктора

Поскольку элемент управления <xref:System.Windows.Forms.TreeView> Windows Forms отображает узлы иерархически, при добавлении узла необходимо обратить внимание на то, что имеет его родительский узел.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.TreeView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

### <a name="to-add-or-remove-nodes-in-the-designer"></a>Добавление или удаление узлов в конструкторе

1. Выберите элемент управления <xref:System.Windows.Forms.TreeView>.

2. В окне " **Свойства** " нажмите кнопку **с многоточием** (![...) в окно свойств кнопки Visual Studio <xref:System.Windows.Forms.TreeView.Nodes%2A> .](./media/visual-studio-ellipsis-button.png)) рядом со свойством.

     Откроется **Редактор TreeNode** .

3. Для добавления узлов должен существовать корневой узел. Если он не существует, необходимо сначала добавить корень, нажав кнопку **Добавить корень** . Затем можно добавить дочерние узлы, выбрав корень или любой другой узел и нажав кнопку **Добавить дочерний** элемент.

4. Чтобы удалить узлы, выберите узел для удаления и нажмите кнопку **Удалить** .

## <a name="see-also"></a>См. также

- [Элемент управления TreeView](treeview-control-windows-forms.md)
- [Общие сведения об элементе управления TreeView](treeview-control-overview-windows-forms.md)
- [Практическое руководство. Задание значков для элемента управления Windows Forms TreeView](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Практическое руководство. Перебор всех узлов элемента управления Windows Forms TreeView](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Практическое руководство. Определение того, какой узел TreeView был выбран](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
