---
title: Практическое руководство. Добавление столбцов в элемент управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: e82fbcf63047873ebc6e5c40b8b9fbeb14a672e5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038185"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="6f454-102">Практическое руководство. Добавление столбцов в элемент управления ListView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="6f454-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="6f454-103">Элемент управления <xref:System.Windows.Forms.ListView> Windows Forms может отображать несколько столбцов для каждого элемента списка в представлении **Details** .</span><span class="sxs-lookup"><span data-stu-id="6f454-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="6f454-104">Столбцы можно использовать для вывода нескольких типов сведений о каждом элементе списка.</span><span class="sxs-lookup"><span data-stu-id="6f454-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="6f454-105">Например, список файлов может отображать имя файла, тип файла, размер и дату последнего изменения файла.</span><span class="sxs-lookup"><span data-stu-id="6f454-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="6f454-106">Сведения о заполнении столбцов после их создания см. в разделе [как Отображение подэлементов в столбцах с Windows Forms элементом управления](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)ListView.</span><span class="sxs-lookup"><span data-stu-id="6f454-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>

<span data-ttu-id="6f454-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6f454-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="6f454-108">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f454-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>


### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="6f454-109">Добавление столбцов в конструктор</span><span class="sxs-lookup"><span data-stu-id="6f454-109">To add columns in the designer</span></span>

1. <span data-ttu-id="6f454-110">В окне **Свойства** присвойте <xref:System.Windows.Forms.ListView.View%2A> свойству <xref:System.Windows.Forms.View.Details>элемента управления значение.</span><span class="sxs-lookup"><span data-stu-id="6f454-110">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

2. <span data-ttu-id="6f454-111">В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств Visual <xref:System.Windows.Forms.ListView.Columns%2A> Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством.</span><span class="sxs-lookup"><span data-stu-id="6f454-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>

     <span data-ttu-id="6f454-112">Откроется **Редактор коллекции колумнхеадер** .</span><span class="sxs-lookup"><span data-stu-id="6f454-112">The **ColumnHeader Collection Editor** appears.</span></span>

3. <span data-ttu-id="6f454-113">Используйте кнопку **Добавить** , чтобы добавить новые столбцы.</span><span class="sxs-lookup"><span data-stu-id="6f454-113">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="6f454-114">Затем можно выбрать заголовок столбца и задать его текст (заголовок столбца), выравнивание текста и ширину.</span><span class="sxs-lookup"><span data-stu-id="6f454-114">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f454-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6f454-115">See also</span></span>

- [<span data-ttu-id="6f454-116">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="6f454-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="6f454-117">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f454-117">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="6f454-118">Практическое руководство. Отображение подэлементов в столбцах с Windows Forms элементом управления ListView</span><span class="sxs-lookup"><span data-stu-id="6f454-118">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="6f454-119">Практическое руководство. Отображение значков для элемента управления ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f454-119">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="6f454-120">Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6f454-120">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
