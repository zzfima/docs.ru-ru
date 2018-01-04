---
title: "Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26f2ab0247c9d13a90560337c103a970afc8996c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fc531-102">Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fc531-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fc531-103">Ввод данных можно сделать более удобным при приложение по умолчанию заполняет значения для только что добавленных строк.</span><span class="sxs-lookup"><span data-stu-id="fc531-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="fc531-104">С <xref:System.Windows.Forms.DataGridView> класса, можно заполнить по умолчанию значения с <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий.</span><span class="sxs-lookup"><span data-stu-id="fc531-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="fc531-105">Это событие возникает, когда пользователь вводит строку для новых записей.</span><span class="sxs-lookup"><span data-stu-id="fc531-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="fc531-106">С помощью обработчика этого события, можно заполнить требуемые ячейки со значениями по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="fc531-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="fc531-107">В следующем примере кода демонстрируется задание значений по умолчанию для новых строк с помощью <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий.</span><span class="sxs-lookup"><span data-stu-id="fc531-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc531-108">Пример</span><span class="sxs-lookup"><span data-stu-id="fc531-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc531-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fc531-109">Compiling the Code</span></span>  
 <span data-ttu-id="fc531-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="fc531-110">This example requires:</span></span>  
  
-   <span data-ttu-id="fc531-111">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="fc531-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="fc531-112">Объект `NewCustomerId` функции для создания уникальных `CustomerID` значения.</span><span class="sxs-lookup"><span data-stu-id="fc531-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="fc531-113">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fc531-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc531-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fc531-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [<span data-ttu-id="fc531-115">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fc531-115">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fc531-116">Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fc531-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
