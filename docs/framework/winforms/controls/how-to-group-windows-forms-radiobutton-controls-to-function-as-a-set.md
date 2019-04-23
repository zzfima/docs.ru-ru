---
title: Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 857e61bc89e072aebcf34793d7e8504ece3318c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307273"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="6c42a-102">Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c42a-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="6c42a-103">Windows Forms <xref:System.Windows.Forms.RadioButton> элементы управления позволяют пользователям для выбора между двумя или несколькими параметрами, в которых можно назначить только один для процедуры или объекта.</span><span class="sxs-lookup"><span data-stu-id="6c42a-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="6c42a-104">Например, группы <xref:System.Windows.Forms.RadioButton> элементов управления может отображать выбор способа доставки заказа, но только один способ будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="6c42a-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="6c42a-105">Таким образом, только один <xref:System.Windows.Forms.RadioButton> за раз можно выбрать, даже если он является частью функциональной группы.</span><span class="sxs-lookup"><span data-stu-id="6c42a-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="6c42a-106">Группы переключателей путем их рисования внутри контейнеров, таких как <xref:System.Windows.Forms.Panel> управления <xref:System.Windows.Forms.GroupBox> управления или форма.</span><span class="sxs-lookup"><span data-stu-id="6c42a-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="6c42a-107">Всех переключателей, которые добавляются напрямую в одну группу становятся формы.</span><span class="sxs-lookup"><span data-stu-id="6c42a-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="6c42a-108">Чтобы добавить отдельные группы, необходимо разместить их внутри элементов управления или групп.</span><span class="sxs-lookup"><span data-stu-id="6c42a-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="6c42a-109">Дополнительные сведения о панелях и группах, см. в разделе [Обзор элемента управления панели](panel-control-overview-windows-forms.md) или [Обзор элемента управления GroupBox](groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6c42a-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="6c42a-110">Чтобы сгруппировать элементы управления RadioButton как набор функции, независимо от других наборов</span><span class="sxs-lookup"><span data-stu-id="6c42a-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="6c42a-111">Перетащите <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel> управления из **Windows Forms** вкладке **элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="6c42a-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="6c42a-112">Рисование <xref:System.Windows.Forms.RadioButton> элементов управления в <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c42a-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c42a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6c42a-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="6c42a-114">Общие сведения об элементе управления RadioButton</span><span class="sxs-lookup"><span data-stu-id="6c42a-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="6c42a-115">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="6c42a-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="6c42a-116">Общие сведения об элементе управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="6c42a-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6c42a-117">Общие сведения об элементе управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="6c42a-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6c42a-118">Элемент управления RadioButton</span><span class="sxs-lookup"><span data-stu-id="6c42a-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
