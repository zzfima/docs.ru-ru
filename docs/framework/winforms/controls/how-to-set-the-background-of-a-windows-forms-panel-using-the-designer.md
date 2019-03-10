---
title: Практическое руководство. Меняем цвет фона панели формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 73b09b9240f417dbe80546e89f2fdfb1e4e4a483
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711919"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="04e33-102">Практическое руководство. Меняем цвет фона панели формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="04e33-102">How to: Set the Background of a Windows Forms Panel Using the Designer</span></span>
<span data-ttu-id="04e33-103">Windows Forms <xref:System.Windows.Forms.Panel> может отображать элемент управления цветом фона и фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="04e33-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="04e33-104"><xref:System.Windows.Forms.Control.BackColor%2A> Свойство задает цвет фона для элементов управления, содержащихся в панели, например, метки и переключатели.</span><span class="sxs-lookup"><span data-stu-id="04e33-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="04e33-105">Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство не задано, <xref:System.Windows.Forms.Control.BackColor%2A> выбора будет заполнить все панели.</span><span class="sxs-lookup"><span data-stu-id="04e33-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="04e33-106">Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство задано, элементы управления, содержащихся на панели отображается изображение.</span><span class="sxs-lookup"><span data-stu-id="04e33-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>  
  
 <span data-ttu-id="04e33-107">Следующая процедура требуется **приложения Windows** проект с формой, содержащей <xref:System.Windows.Forms.Panel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="04e33-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="04e33-108">Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="04e33-108">For information about how to set up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04e33-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="04e33-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="04e33-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="04e33-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="04e33-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="04e33-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="04e33-112">Для установки фона в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04e33-112">To set the background in the Windows Forms Designer</span></span>  
  
1.  <span data-ttu-id="04e33-113">Выберите элемент управления <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="04e33-113">Select the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
2.  <span data-ttu-id="04e33-114">В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackColor%2A> свойство для отображения окна с тремя вкладками.</span><span class="sxs-lookup"><span data-stu-id="04e33-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>  
  
3.  <span data-ttu-id="04e33-115">Выберите **Custom** вкладку, чтобы отобразить палитру цветов.</span><span class="sxs-lookup"><span data-stu-id="04e33-115">Select the **Custom** tab to display a palette of colors.</span></span>  
  
4.  <span data-ttu-id="04e33-116">Выберите **Web** или **системы** вкладку для отображения списка предопределенных имен цветов, а затем выберите цвет.</span><span class="sxs-lookup"><span data-stu-id="04e33-116">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>  
  
5.  <span data-ttu-id="04e33-117">В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="04e33-117">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>  
  
6.  <span data-ttu-id="04e33-118">В **откройте** диалоговом окне выберите файл, который вы хотите отобразить.</span><span class="sxs-lookup"><span data-stu-id="04e33-118">In the **Open** dialog box, select the file that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e33-119">См. также</span><span class="sxs-lookup"><span data-stu-id="04e33-119">See also</span></span>
- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="04e33-120">Элемент управления Panel</span><span class="sxs-lookup"><span data-stu-id="04e33-120">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="04e33-121">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="04e33-121">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="04e33-122">Практическое руководство. Группа элементов управления с помощью панели управления Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="04e33-122">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
