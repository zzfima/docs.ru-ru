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
ms.openlocfilehash: b42845ab996c0985fe6a48ac588e6d706905faac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195856"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="5036f-102">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="5036f-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="5036f-103">Вы можете использовать формы Windows <xref:System.Windows.Forms.TabControl> для отображения других элементов управления в структуру предприятия.</span><span class="sxs-lookup"><span data-stu-id="5036f-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="5036f-104">Ниже показано, как добавить кнопку на первой вкладке. Сведения о добавлении значка в часть метки страницы вкладки, см. в разделе [как: Изменение внешнего вида элемента управления TabControl в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="5036f-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="5036f-105">Чтобы добавить элемент управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="5036f-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="5036f-106">Используйте <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> метод из коллекции, возвращаемой <xref:System.Windows.Forms.Control.Controls%2A> свойство <xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="5036f-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5036f-107">См. также</span><span class="sxs-lookup"><span data-stu-id="5036f-107">See also</span></span>

- [<span data-ttu-id="5036f-108">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="5036f-108">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="5036f-109">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="5036f-109">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="5036f-110">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5036f-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="5036f-111">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="5036f-111">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="5036f-112">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5036f-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
