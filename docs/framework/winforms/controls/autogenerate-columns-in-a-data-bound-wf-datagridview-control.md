---
title: "Практическое руководство. Автоматическое создание столбцов связанного с данными элемента управления DataGridView в Windows Forms"
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
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1d6a790f8a43f4ea2f9d3ad2cdb282186554da6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="58fec-102">Практическое руководство. Автоматическое создание столбцов связанного с данными элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58fec-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="58fec-103">В следующем примере кода показано, как отобразить столбцы из связанного источника данных в <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="58fec-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="58fec-104">Когда <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> значение свойства `true` (по умолчанию), <xref:System.Windows.Forms.DataGridViewColumn> создается для каждого столбца в исходной таблице данных.</span><span class="sxs-lookup"><span data-stu-id="58fec-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="58fec-105">Если <xref:System.Windows.Forms.DataGridView> управления уже имеет столбцы при установке <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> свойства, существующие связанные столбцы по сравнению со столбцами в источнике данных и сохраняется при каждом обнаружении совпадения.</span><span class="sxs-lookup"><span data-stu-id="58fec-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="58fec-106">Несвязанные столбцы всегда сохраняются.</span><span class="sxs-lookup"><span data-stu-id="58fec-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="58fec-107">Привязанные столбцы, для которых нет совпадений в источнике данных будут удалены.</span><span class="sxs-lookup"><span data-stu-id="58fec-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="58fec-108">Столбцы в источнике данных, для которых нет совпадений в элементе управления создают новые <xref:System.Windows.Forms.DataGridViewColumn> объекты, которые добавляются в конец <xref:System.Windows.Forms.DataGridView.Columns%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="58fec-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58fec-109">Пример</span><span class="sxs-lookup"><span data-stu-id="58fec-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58fec-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="58fec-110">Compiling the Code</span></span>  
 <span data-ttu-id="58fec-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="58fec-111">This example requires:</span></span>  
  
-   <span data-ttu-id="58fec-112">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `customersDataGridView`;</span><span class="sxs-lookup"><span data-stu-id="58fec-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
-   <span data-ttu-id="58fec-113">Объект <xref:System.Data.DataSet> объект с именем `customersDataSet` , содержащий таблицу с именем `Customers`.</span><span class="sxs-lookup"><span data-stu-id="58fec-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
-   <span data-ttu-id="58fec-114">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> и <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58fec-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58fec-115">См. также</span><span class="sxs-lookup"><span data-stu-id="58fec-115">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="58fec-116">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58fec-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="58fec-117">Практическое руководство. Удаление автоматически сгенерированных столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58fec-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)
