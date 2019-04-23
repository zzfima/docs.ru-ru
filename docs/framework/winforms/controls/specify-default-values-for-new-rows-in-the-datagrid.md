---
title: Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: 8a90cbef7032fd3753a6c9ec0b856a4e2ea1db27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193698"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="237cb-102">Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="237cb-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="237cb-103">Ввод данных можно сделать более удобным при приложение по умолчанию заполняет значения для только что добавленных строк.</span><span class="sxs-lookup"><span data-stu-id="237cb-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="237cb-104">С помощью <xref:System.Windows.Forms.DataGridView> класса, можно заполнять в используемом по умолчанию значения с <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий.</span><span class="sxs-lookup"><span data-stu-id="237cb-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="237cb-105">Это событие возникает, когда пользователь вводит строку для новых записей.</span><span class="sxs-lookup"><span data-stu-id="237cb-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="237cb-106">Когда ваш код обрабатывает это событие, можно заполнить требуемые ячейки со значениями по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="237cb-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="237cb-107">В следующем примере кода демонстрируется указание значений по умолчанию для новых строк с помощью <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий.</span><span class="sxs-lookup"><span data-stu-id="237cb-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="237cb-108">Пример</span><span class="sxs-lookup"><span data-stu-id="237cb-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="237cb-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="237cb-109">Compiling the Code</span></span>  
 <span data-ttu-id="237cb-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="237cb-110">This example requires:</span></span>  
  
-   <span data-ttu-id="237cb-111">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="237cb-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="237cb-112">Объект `NewCustomerId` функция для создания уникальных `CustomerID` значения.</span><span class="sxs-lookup"><span data-stu-id="237cb-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="237cb-113">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="237cb-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="237cb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="237cb-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="237cb-115">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="237cb-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="237cb-116">Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="237cb-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
