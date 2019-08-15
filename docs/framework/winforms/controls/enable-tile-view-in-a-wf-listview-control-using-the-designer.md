---
title: Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040353"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="5c361-102">Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5c361-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="5c361-103">Функция мозаичного представления <xref:System.Windows.Forms.ListView> элемента управления позволяет обеспечить визуальный баланс между графическими и текстовыми сведениями.</span><span class="sxs-lookup"><span data-stu-id="5c361-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="5c361-104">Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления.</span><span class="sxs-lookup"><span data-stu-id="5c361-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="5c361-105">Мозаичное представление функции в сочетании с функциями группирования или вставки меток в <xref:System.Windows.Forms.ListView> элементе управления.</span><span class="sxs-lookup"><span data-stu-id="5c361-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="5c361-106">Мозаичное представление использует значок 32 x 32 и несколько строк текста, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="5c361-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="5c361-107">![Мозаичное представление в элементе управления ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Значки и текст мозаичного представления")</span><span class="sxs-lookup"><span data-stu-id="5c361-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="5c361-108">Свойства и методы мозаичного представления позволяют указать, какие поля столбцов должны отображаться для каждого элемента, а также совокупно управлять размером и внешним видом всех элементов в окне мозаичного представления.</span><span class="sxs-lookup"><span data-stu-id="5c361-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="5c361-109">Для ясности первая строка текста в плитке всегда является именем элемента. его нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="5c361-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="5c361-110">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="5c361-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="5c361-111">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5c361-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5c361-112">Функция мозаичного представления доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)], когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c361-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5c361-113">В предыдущих версиях операционных систем код, связанный с мозаичным представлением, не оказывает никакого влияния, элемент управления <xref:System.Windows.Forms.ListView> отображается в представлении крупных значков.</span><span class="sxs-lookup"><span data-stu-id="5c361-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="5c361-114">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c361-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="5c361-115">Задание мозаичного представления в конструкторе</span><span class="sxs-lookup"><span data-stu-id="5c361-115">To set tile view in the designer</span></span>

1. <span data-ttu-id="5c361-116">В Visual Studio выберите <xref:System.Windows.Forms.ListView> элемент управления в форме.</span><span class="sxs-lookup"><span data-stu-id="5c361-116">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="5c361-117">В окне **Свойства** выберите <xref:System.Windows.Forms.ListView.View%2A> свойство и щелкните плитка.</span><span class="sxs-lookup"><span data-stu-id="5c361-117">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c361-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5c361-118">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="5c361-119">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="5c361-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
