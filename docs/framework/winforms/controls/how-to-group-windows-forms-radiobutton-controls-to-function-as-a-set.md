---
title: Группирование элементов управления RadioButton для работы в качестве набора
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732949"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="f7af8-102">Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f7af8-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="f7af8-103">Windows Forms элементы управления <xref:System.Windows.Forms.RadioButton> предназначены для того, чтобы предоставить пользователям выбор между двумя или более параметрами, из которых только один может быть назначен процедуре или объекту.</span><span class="sxs-lookup"><span data-stu-id="f7af8-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="f7af8-104">Например, группа элементов управления <xref:System.Windows.Forms.RadioButton> может отображать один или несколько перевозчиков пакетов для заказа, но будут использоваться только те из них.</span><span class="sxs-lookup"><span data-stu-id="f7af8-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="f7af8-105">Поэтому можно выбрать только один <xref:System.Windows.Forms.RadioButton> за раз, даже если он является частью функциональной группы.</span><span class="sxs-lookup"><span data-stu-id="f7af8-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="f7af8-106">Переключатели группируются путем их рисования внутри контейнера, например элемента управления <xref:System.Windows.Forms.Panel>, элемента управления <xref:System.Windows.Forms.GroupBox> или формы.</span><span class="sxs-lookup"><span data-stu-id="f7af8-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="f7af8-107">Все переключатели, добавленные непосредственно в форму, становятся одной группой.</span><span class="sxs-lookup"><span data-stu-id="f7af8-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="f7af8-108">Чтобы добавить отдельные группы, необходимо поместить их внутри панелей или групп.</span><span class="sxs-lookup"><span data-stu-id="f7af8-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="f7af8-109">Дополнительные сведения о панелях или полях групп см. в разделе Общие сведения об [элементе управления Panel](panel-control-overview-windows-forms.md) или [элементе управления GroupBox](groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f7af8-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="f7af8-110">Группировка элементов управления RadioButton как набора, который будет функционировать независимо от других наборов</span><span class="sxs-lookup"><span data-stu-id="f7af8-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="f7af8-111">Перетащите <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel> элемент управления с вкладки **Windows Forms** на **панели элементов** в форму.</span><span class="sxs-lookup"><span data-stu-id="f7af8-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="f7af8-112">Рисование <xref:System.Windows.Forms.RadioButton> элементов управления в <xref:System.Windows.Forms.GroupBox> или элементе управления <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="f7af8-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7af8-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7af8-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="f7af8-114">Общие сведения об элементе управления RadioButton</span><span class="sxs-lookup"><span data-stu-id="f7af8-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="f7af8-115">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="f7af8-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="f7af8-116">Общие сведения об элементе управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="f7af8-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="f7af8-117">Общие сведения об элементе управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="f7af8-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="f7af8-118">Элемент управления RadioButton</span><span class="sxs-lookup"><span data-stu-id="f7af8-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
