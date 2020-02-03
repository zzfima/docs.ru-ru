---
title: Указание значений по умолчанию для новых строк в элементе управления DataGridView
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
ms.openlocfilehash: 364f922aefc10e57f2ed7f3a0c2a5b25c922d87a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742930"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ea2a5-102">Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea2a5-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ea2a5-103">Вы можете сделать ввод данных более удобным, когда приложение заполнит значения по умолчанию для вновь добавленных строк.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="ea2a5-104">С помощью класса <xref:System.Windows.Forms.DataGridView> можно заполнить значения по умолчанию с помощью события <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="ea2a5-105">Это событие возникает, когда пользователь вводит строку для новых записей.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="ea2a5-106">Когда код обрабатывает это событие, можно заполнить нужные ячейки значениями по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="ea2a5-107">В следующем примере кода показано, как задать значения по умолчанию для новых строк с помощью события <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea2a5-108">Пример</span><span class="sxs-lookup"><span data-stu-id="ea2a5-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ea2a5-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ea2a5-109">Compiling the Code</span></span>  
 <span data-ttu-id="ea2a5-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ea2a5-110">This example requires:</span></span>  
  
- <span data-ttu-id="ea2a5-111">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="ea2a5-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="ea2a5-112">Функция `NewCustomerId` для создания уникальных значений `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
- <span data-ttu-id="ea2a5-113">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2a5-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ea2a5-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="ea2a5-115">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea2a5-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ea2a5-116">Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea2a5-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
