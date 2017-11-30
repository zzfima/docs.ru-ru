---
title: "Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cadf31d45f8650336c6ac6257a84655a978a9035
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="4530b-102">Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4530b-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="4530b-103">Функция мозаичного представления элемента <xref:System.Windows.Forms.ListView> позволяет обеспечить визуальный баланс между графическими и текстовыми представлениями информации.</span><span class="sxs-lookup"><span data-stu-id="4530b-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="4530b-104">Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления.</span><span class="sxs-lookup"><span data-stu-id="4530b-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="4530b-105">Вид мозаики работает в сочетании с группирования или вставки метки возможности <xref:System.Windows.Forms.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4530b-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="4530b-106">Мозаичное представление использует значок 32 x 32 и несколько строк текста, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4530b-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>  
  
 <span data-ttu-id="4530b-107">![Мозаичное представление в элементе управления ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span><span class="sxs-lookup"><span data-stu-id="4530b-107">![Tile View in a ListView Control](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span></span>  
  
 <span data-ttu-id="4530b-108">Мозаичное представление, свойства и методы позволяют указать, какие поля столбцов для отображения для каждого элемента и управлять размером и внешним видом всех элементов в окно представления плитки.</span><span class="sxs-lookup"><span data-stu-id="4530b-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="4530b-109">Для ясности первая строка текста заголовка всегда является имя элемента; его нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="4530b-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>  
  
 <span data-ttu-id="4530b-110">В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4530b-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="4530b-111">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4530b-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4530b-112">Функция мозаичного представления доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)], когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4530b-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4530b-113">В предыдущих версиях операционных систем код, связанный с мозаичным представлением, не оказывает никакого влияния, элемент управления <xref:System.Windows.Forms.ListView> отображается в представлении крупных значков.</span><span class="sxs-lookup"><span data-stu-id="4530b-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="4530b-114">Для получения дополнительной информации см. <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4530b-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="4530b-115">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="4530b-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4530b-116">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="4530b-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4530b-117">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="4530b-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="4530b-118">Выбор мозаичного представления в конструкторе</span><span class="sxs-lookup"><span data-stu-id="4530b-118">To set tile view in the designer</span></span>  
  
1.  <span data-ttu-id="4530b-119">Выберите <xref:System.Windows.Forms.ListView> элемент управления в форме.</span><span class="sxs-lookup"><span data-stu-id="4530b-119">Select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>  
  
2.  <span data-ttu-id="4530b-120">В **свойства** выберите <xref:System.Windows.Forms.ListView.View%2A> свойство и выберите **плитки**.</span><span class="sxs-lookup"><span data-stu-id="4530b-120">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4530b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4530b-121">See Also</span></span>  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [<span data-ttu-id="4530b-122">Возможности Windows XP и элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4530b-122">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="4530b-123">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="4530b-123">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
