---
title: "Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3acc1a731fa584a17c8a96f8a02986a504cd302d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора
Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления выводит на экран иерархию узлов аналогично файлов и папок на левой панели проводника в операционных системах Windows. Установив <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> свойства, можно предоставить контекстно-зависимые операции для пользователя при их правой кнопкой мыши <xref:System.Windows.Forms.TreeView> элемента управления. Связав <xref:System.Windows.Forms.ContextMenuStrip> компонента с отдельными <xref:System.Windows.Forms.TreeNode> элементы, можно добавить настраиваемый уровень функциональности контекстное меню для вашего <xref:System.Windows.Forms.TreeView> элементов управления.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Чтобы связать контекстное меню с TreeNode во время разработки  
  
1.  Добавить <xref:System.Windows.Forms.TreeView> управления в форму, а затем добавьте узлы <xref:System.Windows.Forms.TreeView> при необходимости. Дополнительные сведения см. в разделе [как: Добавление и удаление узлов с помощью элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Добавить <xref:System.Windows.Forms.ContextMenuStrip> в форму, компоненты и затем добавить элементы меню в контекстное меню, соответствующие операциям на уровне узла должны быть доступны во время выполнения. Дополнительные сведения см. в разделе [как: Добавление элементов меню в элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Снова откройте **TreeNodeEditor** диалоговое окно для <xref:System.Windows.Forms.TreeView> управления, выберите узел, который необходимо изменить и установите его <xref:System.Windows.Forms.ContextMenuStrip> свойства в контекстном меню, который был добавлен.  
  
4.  Если это свойство имеет значение, в контекстном меню отображается при щелчке правой кнопкой мыши узел.  
  
     Кроме того, необходимо написать код для обработки <xref:System.Windows.Forms.ToolStripItem.Click> событий для этих пунктов меню.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Общие сведения об элементе управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
