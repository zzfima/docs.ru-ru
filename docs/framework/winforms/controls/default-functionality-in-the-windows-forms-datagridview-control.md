---
title: Функциональные возможности по умолчанию в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746135"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="84423-102">Стандартная функциональность элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84423-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="84423-103">Элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> предоставляет пользователям значительный объем функциональных возможностей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="84423-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="84423-104">Функциональные возможности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="84423-104">Default Functionality</span></span>  
 <span data-ttu-id="84423-105">По умолчанию элемент управления <xref:System.Windows.Forms.DataGridView>:</span><span class="sxs-lookup"><span data-stu-id="84423-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <span data-ttu-id="84423-106">Автоматически отображает заголовки столбцов и заголовки строк, которые остаются видимыми при вертикальной прокрутке таблицы.</span><span class="sxs-lookup"><span data-stu-id="84423-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
- <span data-ttu-id="84423-107">Содержит заголовок строки, который содержит индикатор выбора для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="84423-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
- <span data-ttu-id="84423-108">Содержит прямоугольник выделения в первой ячейке.</span><span class="sxs-lookup"><span data-stu-id="84423-108">Has a selection rectangle in the first cell.</span></span>  
  
- <span data-ttu-id="84423-109">Содержит столбцы, размер которых может изменяться автоматически, когда пользователь дважды щелкает разделители столбцов.</span><span class="sxs-lookup"><span data-stu-id="84423-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
- <span data-ttu-id="84423-110">Автоматически поддерживает стили оформления для Windows XP и семейства Windows Server 2003, когда метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> вызывается из метода `Main` приложения.</span><span class="sxs-lookup"><span data-stu-id="84423-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="84423-111">Кроме того, содержимое элемента управления <xref:System.Windows.Forms.DataGridView> может быть изменено по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="84423-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
- <span data-ttu-id="84423-112">Если пользователь дважды щелкнет или нажмет клавишу F2 в ячейке, элемент управления автоматически поместит ячейку в режим редактирования и обновит содержимое ячейки как пользовательские типы.</span><span class="sxs-lookup"><span data-stu-id="84423-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
- <span data-ttu-id="84423-113">Если пользователь прокручивается до конца сетки, пользователь увидит строку для добавления новых записей.</span><span class="sxs-lookup"><span data-stu-id="84423-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="84423-114">Когда пользователь щелкает эту строку, в элемент управления <xref:System.Windows.Forms.DataGridView> добавляется новая строка со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="84423-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="84423-115">Когда пользователь нажимает клавишу ESC, эта новая строка исчезает.</span><span class="sxs-lookup"><span data-stu-id="84423-115">When the user presses ESC, this new row disappears.</span></span>  
  
- <span data-ttu-id="84423-116">Если пользователь щелкает заголовок строки, выбирается вся строка.</span><span class="sxs-lookup"><span data-stu-id="84423-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="84423-117">При привязке <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных путем установки его свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A> элемент управления:</span><span class="sxs-lookup"><span data-stu-id="84423-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
- <span data-ttu-id="84423-118">Автоматически использует имена столбцов источника данных в качестве текста заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="84423-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
- <span data-ttu-id="84423-119">Заполняется содержимым источника данных.</span><span class="sxs-lookup"><span data-stu-id="84423-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="84423-120"><xref:System.Windows.Forms.DataGridView> столбцы создаются автоматически для каждого столбца в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="84423-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
- <span data-ttu-id="84423-121">Создает строку для каждой видимой строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="84423-121">Creates a row for each visible row in the table.</span></span>  
  
- <span data-ttu-id="84423-122">Автоматически сортирует строки на основе базовых данных, когда пользователь щелкает заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="84423-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84423-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84423-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="84423-124">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="84423-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
