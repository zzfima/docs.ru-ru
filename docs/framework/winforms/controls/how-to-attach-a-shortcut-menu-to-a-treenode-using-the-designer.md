---
title: Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040449"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора
Элемент управления <xref:System.Windows.Forms.TreeView> Windows Forms отображает иерархию узлов, аналогично файлам и папкам, отображаемым на левой панели функции проводника Windows в операционных системах Windows. Установив <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> свойство, можно предоставить пользователю контекстно-зависимые операции, если щелкнуть <xref:System.Windows.Forms.TreeView> элемент управления правой кнопкой мыши. Связав <xref:System.Windows.Forms.ContextMenuStrip> компонент с отдельными <xref:System.Windows.Forms.TreeNode> элементами, можно добавить в <xref:System.Windows.Forms.TreeView> элементы управления пользовательский уровень функциональности контекстного меню.

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Связывание контекстного меню с TreeNode во время разработки

1. Добавьте в форму <xref:System.Windows.Forms.TreeView> элементуправления,азатемдобавьтеузлыв<xref:System.Windows.Forms.TreeView> нужные элементы. Дополнительные сведения см. в разделе [Практическое руководство. Добавление и удаление узлов с помощью элемента управления](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)Windows Forms TreeView.

2. Добавьте в форму компонент, а затем добавьте пункты меню в контекстное меню, представляющее операции на уровне узла, которые необходимо сделать доступными во время выполнения. <xref:System.Windows.Forms.ContextMenuStrip> Дополнительные сведения см. в разделе [Практическое руководство. Добавление пунктов меню в ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).

3. Снова откройте диалоговое окно **тринодидитор** для <xref:System.Windows.Forms.TreeView> элемента управления, выберите изменяемый узел и присвойте его <xref:System.Windows.Forms.ContextMenuStrip> свойству добавленное контекстное меню.

4. Если это свойство задано, контекстное меню будет отображаться при щелчке правой кнопкой мыши на узле.

     Кроме того, необходимо написать код для управления <xref:System.Windows.Forms.ToolStripItem.Click> событиями этих пунктов меню.

## <a name="see-also"></a>См. также

- [Элемент управления TreeView](treeview-control-windows-forms.md)
- [Общие сведения об элементе управления TreeView](treeview-control-overview-windows-forms.md)
- [Элемент управления ContextMenuStrip](contextmenustrip-control.md)
