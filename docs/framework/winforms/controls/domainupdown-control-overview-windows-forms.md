---
title: "Общие сведения об элементе управления DomainUpDown (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5a86dc6c56c3afff8d8a3a4ca2c5d5efa8eac1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="adb04-102">Общие сведения об элементе управления DomainUpDown (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="adb04-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="adb04-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> элемент управления является набором текстового поля и пары кнопок для перемещения вверх или вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="adb04-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="adb04-104">Он выводит и задает текстовую строку в списке вариантов.</span><span class="sxs-lookup"><span data-stu-id="adb04-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="adb04-105">Пользователь может выбрать строку, щелкнув кнопок со стрелками вверх по списку, клавиши со стрелками вверх и вниз или введя строку, совпадающую с элементом в списке.</span><span class="sxs-lookup"><span data-stu-id="adb04-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="adb04-106">Того, можно использовать для этого элемента управления можно выбрать элементы из списка имен в алфавитном порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="adb04-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adb04-107">Чтобы отсортировать список, установите <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="adb04-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="adb04-108">Функции данного элемента управления очень похож на список или поле со списком, но оно занимает мало места.</span><span class="sxs-lookup"><span data-stu-id="adb04-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="adb04-109">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="adb04-109">Key Properties</span></span>  
 <span data-ttu-id="adb04-110">Ключевые свойства элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="adb04-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="adb04-111"><xref:System.Windows.Forms.DomainUpDown.Items%2A> Свойство содержит список объектов, текстовые значения отображаются в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="adb04-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="adb04-112">Если <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> равно `false`, элемент управления автоматически завершает текст, пользователь и сопоставляет его значение в списке.</span><span class="sxs-lookup"><span data-stu-id="adb04-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="adb04-113">Если <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> равно `true`, прокручивать за последний элемент перейти к первому элементу в списке и наоборот.</span><span class="sxs-lookup"><span data-stu-id="adb04-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="adb04-114">Основные методы элемента управления, <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="adb04-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="adb04-115">Этот элемент управления отображает только текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="adb04-115">This control displays only text strings.</span></span> <span data-ttu-id="adb04-116">Если требуется, чтобы элемент управления, отображающий числовые значения, используйте <xref:System.Windows.Forms.NumericUpDown> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="adb04-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="adb04-117">Дополнительные сведения см. в разделе [Обзор элемента управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="adb04-117">For more information, see [NumericUpDown Control Overview](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb04-118">См. также</span><span class="sxs-lookup"><span data-stu-id="adb04-118">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 [<span data-ttu-id="adb04-119">Элемент управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="adb04-119">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
