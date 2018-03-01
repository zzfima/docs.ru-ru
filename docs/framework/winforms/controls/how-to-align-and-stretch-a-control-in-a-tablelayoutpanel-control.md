---
title: "Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfc1c64bc0bd9cbebad44193fb5adbe529877487
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="408ac-102">Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="408ac-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>
<span data-ttu-id="408ac-103">Можно выравнивать и растягивать элементы управления в <xref:System.Windows.Forms.TableLayoutPanel> с <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="408ac-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="408ac-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="408ac-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="408ac-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="408ac-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="408ac-106">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="408ac-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-align-and-stretch-a-control"></a><span data-ttu-id="408ac-107">Выравнивание и Растягивание элемента управления</span><span class="sxs-lookup"><span data-stu-id="408ac-107">To align and stretch a control</span></span>  
  
1.  <span data-ttu-id="408ac-108">Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="408ac-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="408ac-109">Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в левый верхний угол элемента <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="408ac-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="408ac-110"><xref:System.Windows.Forms.Button> Управления выравнивается по центру ячейки.</span><span class="sxs-lookup"><span data-stu-id="408ac-110">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>  
  
3.  <span data-ttu-id="408ac-111">Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Left,Right`.</span><span class="sxs-lookup"><span data-stu-id="408ac-111">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="408ac-112"><xref:System.Windows.Forms.Button> Управления растягивается по ширине ячейки.</span><span class="sxs-lookup"><span data-stu-id="408ac-112">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>  
  
4.  <span data-ttu-id="408ac-113">Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Top,Bottom`.</span><span class="sxs-lookup"><span data-stu-id="408ac-113">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="408ac-114"><xref:System.Windows.Forms.Button> Управления растягивается в соответствии с высотой ячейки.</span><span class="sxs-lookup"><span data-stu-id="408ac-114">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>  
  
5.  <span data-ttu-id="408ac-115">Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="408ac-115">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="408ac-116"><xref:System.Windows.Forms.Button> Элемент управления расширяется для заполнения ячейки.</span><span class="sxs-lookup"><span data-stu-id="408ac-116">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>  
  
6.  <span data-ttu-id="408ac-117">Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="408ac-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="408ac-118"><xref:System.Windows.Forms.Button> Управления возвращает исходный размер и перемещается в левый верхний угол ячейки.</span><span class="sxs-lookup"><span data-stu-id="408ac-118">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="408ac-119">**Конструктор Windows Forms** задал <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="408ac-119">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>  
  
7.  <span data-ttu-id="408ac-120">Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства `Bottom,Right`.</span><span class="sxs-lookup"><span data-stu-id="408ac-120">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="408ac-121"><xref:System.Windows.Forms.Button> Элемент управления перемещается в правом нижнем углу ячейки.</span><span class="sxs-lookup"><span data-stu-id="408ac-121">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>  
  
8.  <span data-ttu-id="408ac-122">Установите для параметра <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства <xref:System.Windows.Forms.AnchorStyles.None>.</span><span class="sxs-lookup"><span data-stu-id="408ac-122">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="408ac-123"><xref:System.Windows.Forms.Button> Управления перемещается по центру ячейки.</span><span class="sxs-lookup"><span data-stu-id="408ac-123">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408ac-124">См. также</span><span class="sxs-lookup"><span data-stu-id="408ac-124">See Also</span></span>  
 [<span data-ttu-id="408ac-125">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="408ac-125">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
