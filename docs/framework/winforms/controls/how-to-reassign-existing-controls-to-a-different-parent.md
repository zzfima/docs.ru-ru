---
title: Практическое руководство. Переназначение существующих элементов управления другим родительским элементам
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: a65b3c2b596a2d88ce4236aeadd86993bb268aa6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039792"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="8f6fa-102">Практическое руководство. Переназначение существующих элементов управления другим родительским элементам</span><span class="sxs-lookup"><span data-stu-id="8f6fa-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="8f6fa-103">Можно назначать существующие в форме элементы управления новому контейнерному элементу управления.</span><span class="sxs-lookup"><span data-stu-id="8f6fa-103">You can assign controls that exist on your form to a new container control.</span></span>

## <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="8f6fa-104">Переназначение существующих элементов управления другим родительским элементам</span><span class="sxs-lookup"><span data-stu-id="8f6fa-104">To reassign existing controls to a different parent</span></span>

1. <span data-ttu-id="8f6fa-105">Перетащите три элемента управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму.</span><span class="sxs-lookup"><span data-stu-id="8f6fa-105">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>

     <span data-ttu-id="8f6fa-106">Расположите их рядом друг с другом, но не выравнивайте.</span><span class="sxs-lookup"><span data-stu-id="8f6fa-106">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="8f6fa-107">В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="8f6fa-107">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>

     <span data-ttu-id="8f6fa-108">Не перетаскивайте значок на форму.</span><span class="sxs-lookup"><span data-stu-id="8f6fa-108">Do not drag the icon onto the form.</span></span>

3. <span data-ttu-id="8f6fa-109">Переместите указатель мыши к трем элементам управления <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="8f6fa-109">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

     <span data-ttu-id="8f6fa-110">Указатель превратится в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="8f6fa-110">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="8f6fa-111">Нажмите и удерживайте кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="8f6fa-111">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="8f6fa-112">Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="8f6fa-112">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="8f6fa-113">Обведите таким образом три элемента управления <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="8f6fa-113">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="8f6fa-114">Отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="8f6fa-114">Release the mouse button.</span></span>

     <span data-ttu-id="8f6fa-115">Теперь три элемента управления <xref:System.Windows.Forms.Button> вставлены в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="8f6fa-115">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f6fa-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8f6fa-116">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="8f6fa-117">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f6fa-117">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="8f6fa-118">Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8f6fa-118">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="8f6fa-119">Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="8f6fa-119">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
