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
ms.openlocfilehash: 6eb509fd10a5000a5423d624cec5b6d126990d73
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723959"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Практическое руководство. Добавление элемента управления на вкладку
Вы можете использовать формы Windows <xref:System.Windows.Forms.TabControl> для отображения других элементов управления в структуру предприятия. Ниже показано, как добавить кнопку на первой вкладке. Сведения о добавлении значка в часть метки страницы вкладки, см. в разделе [как: Изменение внешнего вида элемента управления TabControl в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Чтобы добавить элемент управления программными средствами  
  
1.  Используйте <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> метод из коллекции, возвращаемой <xref:System.Windows.Forms.Control.Controls%2A> свойство <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>См. также
- [Элемент управления TabControl](tabcontrol-control-windows-forms.md)
- [Общие сведения об элементе управления TabControl](tabcontrol-control-overview-windows-forms.md)
- [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [Практическое руководство. Блокировка доступа ко вкладкам](how-to-disable-tab-pages.md)
- [Практическое руководство. Добавление и удаление вкладок с помощью Windows Forms TabControl](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
