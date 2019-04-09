---
title: Стандартная функциональность элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: 26633b0abaa8c1c2916153b2236ecf9e4982fd68
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208869"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5a9bc-102">Стандартная функциональность элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a9bc-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5a9bc-103">Windows Forms <xref:System.Windows.Forms.DataGridView> управления предоставляет пользователям широкую функциональность по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="5a9bc-104">Стандартная функциональность</span><span class="sxs-lookup"><span data-stu-id="5a9bc-104">Default Functionality</span></span>  
 <span data-ttu-id="5a9bc-105">По умолчанию <xref:System.Windows.Forms.DataGridView> управления:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="5a9bc-106">Автоматически отображает заголовки столбцов и заголовки строк, которые остаются видимыми при прокрутке таблицы по вертикали.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="5a9bc-107">Содержит заголовок строки, который содержит индикатор выделения для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="5a9bc-108">Имеет рамку выделения в первой ячейке.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="5a9bc-109">Содержит столбцы, которые могут изменяться автоматически при двойном щелчке разделителей столбцов.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="5a9bc-110">Автоматически поддерживает стили оформления Windows XP и семействе Windows Server 2003 при <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод вызывается из приложения `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="5a9bc-111">Кроме того, содержимое <xref:System.Windows.Forms.DataGridView> элемента управления можно изменить по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="5a9bc-112">Если пользователь дважды щелкает или нажимает клавишу F2 в ячейке, элемент управления автоматически переходит в режим редактирования и обновляет содержимое ячейки, когда пользователь вводит текст.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="5a9bc-113">Если пользователь выполняет прокрутку в конец сетки, пользователь будет видеть, что присутствует строка для добавления новых записей.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="5a9bc-114">Когда пользователь щелкает эту строку, добавляется новая строка <xref:System.Windows.Forms.DataGridView> управления со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="5a9bc-115">При нажатии клавиши ESC, новая строка удаляется.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="5a9bc-116">Если пользователь щелкает заголовок строки, выбирается целой строки.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="5a9bc-117">При привязке <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных, задав его <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойства:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="5a9bc-118">Автоматически использует имена столбцов источника данных в качестве текста заголовка столбца.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="5a9bc-119">Заполняется содержимым источника данных.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-119">Is populated with the contents of the data source.</span></span> <xref:System.Windows.Forms.DataGridView> <span data-ttu-id="5a9bc-120">столбцы создаются автоматически для каждого столбца в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-120">columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="5a9bc-121">Создает строку для каждой видимой строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="5a9bc-122">Автоматически сортирует строки, на основе базовых данных, когда пользователь щелкает заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a9bc-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5a9bc-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="5a9bc-124">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="5a9bc-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
