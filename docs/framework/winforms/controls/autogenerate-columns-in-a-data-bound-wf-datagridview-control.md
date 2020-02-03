---
title: Автоматически формировать столбцы в элементе управления DataGridView с привязкой к данным
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 860e640e095537358d2f8778c810aa577e9d7ff0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746229"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="46b96-102">Практическое руководство. Автоматическое создание столбцов связанного с данными элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46b96-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="46b96-103">В следующем примере кода показано, как отобразить столбцы из привязанного источника данных в элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="46b96-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="46b96-104">Если значение свойства <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> `true` (значение по умолчанию), для каждого столбца в таблице источника данных создается <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="46b96-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="46b96-105">Если в элементе управления <xref:System.Windows.Forms.DataGridView> уже есть столбцы при установке свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, существующие связанные столбцы сравниваются со столбцами в источнике данных и сохраняются при обнаружении соответствия.</span><span class="sxs-lookup"><span data-stu-id="46b96-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="46b96-106">Несвязанные столбцы всегда сохраняются.</span><span class="sxs-lookup"><span data-stu-id="46b96-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="46b96-107">Связанные столбцы, для которых нет совпадения в источнике данных, удаляются.</span><span class="sxs-lookup"><span data-stu-id="46b96-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="46b96-108">Столбцы в источнике данных, для которых нет совпадения в элементе управления, создают новые <xref:System.Windows.Forms.DataGridViewColumn> объекты, которые добавляются в конец коллекции <xref:System.Windows.Forms.DataGridView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="46b96-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46b96-109">Пример</span><span class="sxs-lookup"><span data-stu-id="46b96-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46b96-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="46b96-110">Compiling the Code</span></span>  
 <span data-ttu-id="46b96-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="46b96-111">This example requires:</span></span>  
  
- <span data-ttu-id="46b96-112">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `customersDataGridView`;</span><span class="sxs-lookup"><span data-stu-id="46b96-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
- <span data-ttu-id="46b96-113">Объект <xref:System.Data.DataSet> с именем `customersDataSet`, содержащий таблицу с именем `Customers`.</span><span class="sxs-lookup"><span data-stu-id="46b96-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
- <span data-ttu-id="46b96-114">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> и <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="46b96-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b96-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46b96-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="46b96-116">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46b96-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="46b96-117">Практическое руководство. Удаление автоматически сгенерированных столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46b96-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
