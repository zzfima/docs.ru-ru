---
title: Практическое руководство. Переназначение существующих элементов управления другим родительским элементам
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84e662e0bd2689115abe128c6442e4462eed3e18
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987035"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="65f9e-102">Практическое руководство. Переназначить существующие элементы управления другому родителю</span><span class="sxs-lookup"><span data-stu-id="65f9e-102">How to: Reassign existing controls to a different parent</span></span>

<span data-ttu-id="65f9e-103">Можно назначать существующие в форме элементы управления новому контейнерному элементу управления.</span><span class="sxs-lookup"><span data-stu-id="65f9e-103">You can assign controls that exist on your form to a new container control.</span></span>

1. <span data-ttu-id="65f9e-104">В Visual Studio перетащите на форму <xref:System.Windows.Forms.Button> три элемента управления из **панели элементов** .</span><span class="sxs-lookup"><span data-stu-id="65f9e-104">In Visual Studio, drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span> <span data-ttu-id="65f9e-105">Расположите их рядом друг с другом, но не выравнивайте.</span><span class="sxs-lookup"><span data-stu-id="65f9e-105">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="65f9e-106">В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="65f9e-106">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span> <span data-ttu-id="65f9e-107">(Не перетаскивайте значок на форму.)</span><span class="sxs-lookup"><span data-stu-id="65f9e-107">(Do not drag the icon onto the form.)</span></span>

3. <span data-ttu-id="65f9e-108">Переместите указатель мыши к трем элементам управления <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="65f9e-108">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

   <span data-ttu-id="65f9e-109">Указатель превратится в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="65f9e-109">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="65f9e-110">Нажмите и удерживайте кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="65f9e-110">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="65f9e-111">Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="65f9e-111">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="65f9e-112">Обведите таким образом три элемента управления <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="65f9e-112">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="65f9e-113">Отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="65f9e-113">Release the mouse button.</span></span>

   <span data-ttu-id="65f9e-114">Теперь три элемента управления <xref:System.Windows.Forms.Button> вставлены в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="65f9e-114">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="65f9e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="65f9e-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="65f9e-116">Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="65f9e-116">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="65f9e-117">Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="65f9e-117">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
