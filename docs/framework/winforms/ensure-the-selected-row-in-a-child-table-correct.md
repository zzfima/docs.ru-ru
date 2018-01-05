---
title: "Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице"
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
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c06692f19fe31bfcf2ae1f9778d847f412a007e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a><span data-ttu-id="8c027-102">Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице</span><span class="sxs-lookup"><span data-stu-id="8c027-102">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>
<span data-ttu-id="8c027-103">Зачастую при работе с привязкой данных в формах Windows Forms, данные будут отображаться в виде представлений «родительский-дочерний» или «основной-подробности».</span><span class="sxs-lookup"><span data-stu-id="8c027-103">Oftentimes when you work with data binding in Windows Forms, you will display data in what is called a parent/child or master/details view.</span></span> <span data-ttu-id="8c027-104">Это относится к сценариям привязки данных, где отображаются данные из одного источника в двух элементах управления.</span><span class="sxs-lookup"><span data-stu-id="8c027-104">This refers to a data-binding scenario where data from the same source is displayed in two controls.</span></span> <span data-ttu-id="8c027-105">Изменение выделения в одном элементе управления вызывает изменение данных, отображаемых во втором элементе управления.</span><span class="sxs-lookup"><span data-stu-id="8c027-105">Changing the selection in one control causes the data displayed in the second control to change.</span></span> <span data-ttu-id="8c027-106">Например, первый элемент управления может содержать список клиентов, а второй — список заказов, связанных с выбранным клиентом из первого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8c027-106">For example, the first control might contain a list of customers and the second a list of orders related to the selected customer in the first control.</span></span>  
  
 <span data-ttu-id="8c027-107">Начиная с .NET Framework версии 2.0, при отображении данных в представлении «родительский-дочерний» может потребоваться предпринять дополнительные действия, чтобы убедиться в том, что выбранная строка в дочерней таблице не сбрасывается на первую строку таблицы.</span><span class="sxs-lookup"><span data-stu-id="8c027-107">Starting with the .NET Framework version 2.0, when you display data in a parent/child view you might have to take extra steps to make sure that the currently selected row in the child table is not reset to the first row of the table.</span></span> <span data-ttu-id="8c027-108">Для этого необходимо кэшировать позицию дочерней таблицы и сбрасывать ее после изменения родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="8c027-108">In order to do this, you will have to cache the child table position and reset it after the parent table changes.</span></span> <span data-ttu-id="8c027-109">Обычно сброс дочерних таблиц происходит после первого изменения поля в строке родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="8c027-109">Typically the child reset occurs the first time a field in a row of the parent table changes.</span></span>  
  
### <a name="to-cache-the-current-child-position"></a><span data-ttu-id="8c027-110">Кэширование текущей позиции дочерней таблицы</span><span class="sxs-lookup"><span data-stu-id="8c027-110">To Cache the Current Child Position</span></span>  
  
1.  <span data-ttu-id="8c027-111">Объявите целочисленную переменную для хранения позиции в дочернем списке и логическую переменную для хранения признака, следует ли кэшировать позицию дочерней таблицы.</span><span class="sxs-lookup"><span data-stu-id="8c027-111">Declare an integer variable to store the child list position and a Boolean variable to store whether to cache the child position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2.  <span data-ttu-id="8c027-112">Обработайте событие <xref:System.Windows.Forms.CurrencyManager.ListChanged> для привязки <xref:System.Windows.Forms.CurrencyManager> и проверьте значение <xref:System.ComponentModel.ListChangedType> из <xref:System.ComponentModel.ListChangedType.Reset>.</span><span class="sxs-lookup"><span data-stu-id="8c027-112">Handle the <xref:System.Windows.Forms.CurrencyManager.ListChanged> event for the binding's <xref:System.Windows.Forms.CurrencyManager> and check for a <xref:System.ComponentModel.ListChangedType> of <xref:System.ComponentModel.ListChangedType.Reset>.</span></span>  
  
3.  <span data-ttu-id="8c027-113">Проверьте текущую позицию <xref:System.Windows.Forms.CurrencyManager>.</span><span class="sxs-lookup"><span data-stu-id="8c027-113">Check the current position of the <xref:System.Windows.Forms.CurrencyManager>.</span></span> <span data-ttu-id="8c027-114">Если она больше, чем первая запись в списке (обычно 0), сохраните ее в переменной.</span><span class="sxs-lookup"><span data-stu-id="8c027-114">If it is greater than first entry in the list (typically 0), save it to a variable.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="8c027-115">Обработайте событие <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> родительского списка для родительского диспетчера денежного формата.</span><span class="sxs-lookup"><span data-stu-id="8c027-115">Handle the parent list's <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> event for the parent currency manager.</span></span> <span data-ttu-id="8c027-116">В обработчике задайте логическое значение, указывающее, что он не относится к сценарию кэширования.</span><span class="sxs-lookup"><span data-stu-id="8c027-116">In the handler, set the Boolean value to indicate it is not a caching scenario.</span></span> <span data-ttu-id="8c027-117">Если возникает <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>, то в родительском объекте происходит изменение, которое  является изменением позиции в списке, а не изменением значения элемента.</span><span class="sxs-lookup"><span data-stu-id="8c027-117">If the <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> occurs, the change to the parent is a list position change and not an item value change.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a><span data-ttu-id="8c027-118">Сброс позиции дочерней таблицы</span><span class="sxs-lookup"><span data-stu-id="8c027-118">To Reset the Child Position</span></span>  
  
1.  <span data-ttu-id="8c027-119">Обработайте событие <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> для дочерней привязки<xref:System.Windows.Forms.CurrencyManager>.</span><span class="sxs-lookup"><span data-stu-id="8c027-119">Handle the <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> event for the child binding's <xref:System.Windows.Forms.CurrencyManager>.</span></span>  
  
2.  <span data-ttu-id="8c027-120">Установите позицию в дочерней таблице на кэшированную позицию, сохраненную в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="8c027-120">Reset the child table position to the cached position saved in the previous procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="8c027-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8c027-121">Example</span></span>  
 <span data-ttu-id="8c027-122">В следующем примере показано, как сохранить текущую позицию в <xref:System.Windows.Forms.CurrencyManager> для дочерней таблицы и сбросить позицию после завершения изменения родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="8c027-122">The following example demonstrates how to save the current position on the <xref:System.Windows.Forms.CurrencyManager>.for a child table and reset the position after an edit is completed on the parent table.</span></span> <span data-ttu-id="8c027-123">Этот пример содержит два элемента управления <xref:System.Windows.Forms.DataGridView>, которые привязаны к двум таблицам в <xref:System.Data.DataSet> с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="8c027-123">This example contains two <xref:System.Windows.Forms.DataGridView> controls bound to two tables in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="8c027-124">Между двумя таблицами установлено отношение, добавлено отношение к <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8c027-124">A relation is established between the two tables and the relation is added to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="8c027-125">В демонстрационных целях позиция дочерней таблицы изначально установлена на третью строку.</span><span class="sxs-lookup"><span data-stu-id="8c027-125">The position in the child table is initially set to the third row for demonstration purposes.</span></span>  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 <span data-ttu-id="8c027-126">Чтобы проверить пример кода, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8c027-126">To test the code example, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="8c027-127">Запустите пример.</span><span class="sxs-lookup"><span data-stu-id="8c027-127">Run the example.</span></span>  
  
2.  <span data-ttu-id="8c027-128">Убедитесь, что установлен флажок **Кэшировать и сбрасывать позицию**.</span><span class="sxs-lookup"><span data-stu-id="8c027-128">Make sure the **Cache and reset position** check box is selected.</span></span>  
  
3.  <span data-ttu-id="8c027-129">Нажмите кнопку **Очистить родительское поле**, чтобы произвести изменение поля родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="8c027-129">Click the **Clear parent field** button to cause a change in a field of the parent table.</span></span> <span data-ttu-id="8c027-130">Обратите внимание, что выбранная строка в дочерней таблице не изменяется.</span><span class="sxs-lookup"><span data-stu-id="8c027-130">Notice that the selected row in the child table does not change.</span></span>  
  
4.  <span data-ttu-id="8c027-131">Закройте и снова запустите пример.</span><span class="sxs-lookup"><span data-stu-id="8c027-131">Close and run the example again.</span></span> <span data-ttu-id="8c027-132">Это необходимо сделать, поскольку сброс происходит только при первом изменении в родительской строке.</span><span class="sxs-lookup"><span data-stu-id="8c027-132">You need to do this because the reset behavior occurs only on the first change in the parent row.</span></span>  
  
5.  <span data-ttu-id="8c027-133">Сбросьте флажок **Кэшировать и сбрасывать позицию**.</span><span class="sxs-lookup"><span data-stu-id="8c027-133">Clear the **Cache and reset position** check box.</span></span>  
  
6.  <span data-ttu-id="8c027-134">Нажмите кнопку **Очистить родительское поле**.</span><span class="sxs-lookup"><span data-stu-id="8c027-134">Click the **Clear parent field** button.</span></span> <span data-ttu-id="8c027-135">Обратите внимание, что выбранная строка в дочерней таблице становится первой строкой.</span><span class="sxs-lookup"><span data-stu-id="8c027-135">Notice that the selected row in the child table changes to the first row.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c027-136">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8c027-136">Compiling the Code</span></span>  
 <span data-ttu-id="8c027-137">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="8c027-137">This example requires:</span></span>  
  
-   <span data-ttu-id="8c027-138">ссылки на сборки System, System.Data, System.Drawing, System.Windows.Forms и System.XML.</span><span class="sxs-lookup"><span data-stu-id="8c027-138">References to the System, System.Data, System.Drawing, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="8c027-139">Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8c027-139">For information about how to build this example from the command line for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8c027-140">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] , можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="8c027-140">You can also build this example in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="8c027-141">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="8c027-141">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c027-142">См. также</span><span class="sxs-lookup"><span data-stu-id="8c027-142">See Also</span></span>  
 [<span data-ttu-id="8c027-143">Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных</span><span class="sxs-lookup"><span data-stu-id="8c027-143">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 [<span data-ttu-id="8c027-144">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="8c027-144">BindingSource Component</span></span>](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="8c027-145">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c027-145">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
