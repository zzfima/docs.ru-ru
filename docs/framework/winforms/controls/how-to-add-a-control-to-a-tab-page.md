---
title: Практическое руководство. Добавление элемента управления на вкладку
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 1bb2233cf9e288ae89ebb8cab3df4f6451dc8eed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Практическое руководство. Добавление элемента управления на вкладку
Можно использовать в Windows Forms <xref:System.Windows.Forms.TabControl> для отображения других элементов управления в структуру предприятия. Ниже показано, как добавить кнопку на первую вкладку. Сведения о добавлении значка в часть метки страницу вкладки см [как: изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Чтобы добавить элемент управления программными средствами  
  
1.  Используйте <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> метод в коллекцию, возвращаемую <xref:System.Windows.Forms.Control.Controls%2A> свойства <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Элемент управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [Практическое руководство. Блокировка доступа ко вкладкам](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
