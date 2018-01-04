---
title: "Общие сведения об элементе управления CheckBox (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 39645a02cd66d37d61df72028ab129677edb757e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="60e2e-102">Общие сведения об элементе управления CheckBox (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="60e2e-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="60e2e-103">Элемент управления <xref:System.Windows.Forms.CheckBox> Windows Forms указывает, включено или отключено какое-либо условие.</span><span class="sxs-lookup"><span data-stu-id="60e2e-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="60e2e-104">Обычно он используется для предоставления пользователю выбора типа "Да/Нет" или "Истина/Ложь".</span><span class="sxs-lookup"><span data-stu-id="60e2e-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="60e2e-105">Элементы управления типа "флажок" можно объединять в группы для предоставления нескольких вариантов ответа, из которых пользователь может выбрать один или несколько.</span><span class="sxs-lookup"><span data-stu-id="60e2e-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="60e2e-106">Элемент управления флажком аналогична переключателя в том, что каждый используется для указания выбора, сделанного пользователем.</span><span class="sxs-lookup"><span data-stu-id="60e2e-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="60e2e-107">Они отличаются, в которых одновременно можно выбрать только один переключатель в группе.</span><span class="sxs-lookup"><span data-stu-id="60e2e-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="60e2e-108">Однако с помощью элемента управления "флажок" любое количество флажки могут быть выбраны.</span><span class="sxs-lookup"><span data-stu-id="60e2e-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="60e2e-109">Типа "флажок" может быть подключен к элементам в базе данных с помощью простой привязки данных.</span><span class="sxs-lookup"><span data-stu-id="60e2e-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="60e2e-110">Несколько флажков объединяются с помощью <xref:System.Windows.Forms.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="60e2e-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="60e2e-111">Это полезно для внешнего вида, а также для разработки пользовательского интерфейса, поскольку сгруппированных элементов управления можно перемещать одновременно в конструкторе форм.</span><span class="sxs-lookup"><span data-stu-id="60e2e-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="60e2e-112">Дополнительные сведения см. в разделе [привязки данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md) и [управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="60e2e-112">For more information, see [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) and [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="60e2e-113"><xref:System.Windows.Forms.CheckBox> Управления имеет два важных свойства <xref:System.Windows.Forms.CheckBox.Checked%2A> и <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e2e-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="60e2e-114"><xref:System.Windows.Forms.CheckBox.Checked%2A> Свойство возвращает либо `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="60e2e-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="60e2e-115"><xref:System.Windows.Forms.CheckBox.CheckState%2A> Свойство возвращает либо <xref:System.Windows.Forms.CheckState.Checked> или <xref:System.Windows.Forms.CheckState.Unchecked>; или если <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойству `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> могут также возвращать <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="60e2e-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="60e2e-116">В неопределенном состоянии поле отображается затененным, чтобы указать, что параметр будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="60e2e-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60e2e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="60e2e-117">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="60e2e-118">Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60e2e-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="60e2e-119">Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60e2e-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="60e2e-120">Элемент управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="60e2e-120">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
