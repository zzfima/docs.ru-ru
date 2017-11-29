---
title: "Стандартная функциональность элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d6b15085c301f074ef6fcf9e60a75299c4b245b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3b48d-102">Стандартная функциональность элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b48d-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3b48d-103">Windows Forms <xref:System.Windows.Forms.DataGridView> управления предоставляет пользователям широкую функциональность по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b48d-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="3b48d-104">Функциональные возможности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3b48d-104">Default Functionality</span></span>  
 <span data-ttu-id="3b48d-105">По умолчанию <xref:System.Windows.Forms.DataGridView> управления:</span><span class="sxs-lookup"><span data-stu-id="3b48d-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="3b48d-106">Автоматически отображает заголовки столбцов и заголовки строк, которые остаются видимыми при прокрутке таблицы по вертикали.</span><span class="sxs-lookup"><span data-stu-id="3b48d-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="3b48d-107">Содержит заголовок строки с указателем выбора для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="3b48d-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="3b48d-108">Содержит прямоугольник выделения в первой ячейке.</span><span class="sxs-lookup"><span data-stu-id="3b48d-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="3b48d-109">Есть столбцы, которые могут быть изменены автоматически при двойном щелчке разделителей столбцов.</span><span class="sxs-lookup"><span data-stu-id="3b48d-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="3b48d-110">Автоматическая поддержка визуальных стилей в Windows XP и семейства Windows Server 2003 при <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод вызывается из приложения `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="3b48d-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="3b48d-111">Кроме того, содержимое <xref:System.Windows.Forms.DataGridView> управления могут редактироваться по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="3b48d-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="3b48d-112">Если пользователь дважды щелкает или нажимает клавишу F2 в ячейке, элемент управления автоматически переводит ячейку в режим редактирования и обновляет содержимое ячейки при вводе.</span><span class="sxs-lookup"><span data-stu-id="3b48d-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="3b48d-113">Если пользователь выполняет прокрутку к концу сетки, пользователь увидит наличии строка для добавления новых записей.</span><span class="sxs-lookup"><span data-stu-id="3b48d-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="3b48d-114">Когда пользователь нажимает эту строку, добавляется новая строка <xref:System.Windows.Forms.DataGridView> управления со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b48d-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="3b48d-115">При нажатии клавиши ESC новая строка удаляется.</span><span class="sxs-lookup"><span data-stu-id="3b48d-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="3b48d-116">При нажатии кнопки в заголовке строки выбирается целой строки.</span><span class="sxs-lookup"><span data-stu-id="3b48d-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="3b48d-117">При привязке <xref:System.Windows.Forms.DataGridView> управления к источнику данных, установив его <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойства:</span><span class="sxs-lookup"><span data-stu-id="3b48d-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="3b48d-118">Автоматически использует имена столбцов источника данных в виде текста заголовка столбца.</span><span class="sxs-lookup"><span data-stu-id="3b48d-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="3b48d-119">Заполняется содержимым источника данных.</span><span class="sxs-lookup"><span data-stu-id="3b48d-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="3b48d-120"><xref:System.Windows.Forms.DataGridView>столбцы создаются автоматически для каждого столбца в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="3b48d-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="3b48d-121">Создает строку для каждой видимой строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="3b48d-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="3b48d-122">Автоматически сортирует строки на основе базовых данных при щелчке заголовка столбца.</span><span class="sxs-lookup"><span data-stu-id="3b48d-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b48d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3b48d-123">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="3b48d-124">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="3b48d-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
