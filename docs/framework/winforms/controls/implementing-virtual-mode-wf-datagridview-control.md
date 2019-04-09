---
title: Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 7509e2f5035cb05c20af379f9f6a141177d540d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127053"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1133c-102">Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1133c-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1133c-103">Если вы хотите отобразить очень большому количеству табличные данные в <xref:System.Windows.Forms.DataGridView> элемента управления, можно задать <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойства `true` и явно управлять взаимодействием элемента управления с хранилищем данных.</span><span class="sxs-lookup"><span data-stu-id="1133c-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="1133c-104">Это позволяет оптимизировать производительность элемента управления в этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="1133c-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="1133c-105"><xref:System.Windows.Forms.DataGridView> Управления предусмотрено несколько событий, которые можно обрабатывать для взаимодействия с хранилищем пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="1133c-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="1133c-106">В этом пошаговом руководстве поможет выполнить процесс реализации этих обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="1133c-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="1133c-107">В примере кода в этом разделе используется очень простой источник данных для иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="1133c-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="1133c-108">На практике, обычно загружаются только те строки, необходимые для отображения в кэше и обрабатывать <xref:System.Windows.Forms.DataGridView> события для взаимодействия с кэшем и его обновления.</span><span class="sxs-lookup"><span data-stu-id="1133c-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="1133c-109">Дополнительные сведения см. в разделе [реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="1133c-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="1133c-110">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Реализация виртуального режима в Windows Forms элемента управления DataGridView](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="1133c-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="1133c-111">Создание формы</span><span class="sxs-lookup"><span data-stu-id="1133c-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="1133c-112">Реализация виртуального режима</span><span class="sxs-lookup"><span data-stu-id="1133c-112">To implement virtual mode</span></span>  
  
1.  <span data-ttu-id="1133c-113">Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержит <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1133c-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="1133c-114">Следующий код содержит некоторые основные инициализации.</span><span class="sxs-lookup"><span data-stu-id="1133c-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="1133c-115">Он объявляется несколько переменных, которые будут использоваться на последующих этапах, предоставляет `Main` метод и предоставляет простой макет формы в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="1133c-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  <span data-ttu-id="1133c-116">Реализовать обработчик для формы <xref:System.Windows.Forms.Form.Load> событие, которое инициализирует <xref:System.Windows.Forms.DataGridView> управления и заполняет хранилище данных с помощью образцов значений.</span><span class="sxs-lookup"><span data-stu-id="1133c-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  <span data-ttu-id="1133c-117">Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.CellValueNeeded> событие, которое извлекает запрошенное значение ячейки из хранилища данных или `Customer` объекта, находящегося в режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="1133c-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="1133c-118">Это событие возникает каждый раз, когда <xref:System.Windows.Forms.DataGridView> элемента управления требуется прорисовать ячейку.</span><span class="sxs-lookup"><span data-stu-id="1133c-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  <span data-ttu-id="1133c-119">Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.CellValuePushed> события, которое сохраняет измененное значение ячейки в `Customer` объект, представляющий редактируемой строки.</span><span class="sxs-lookup"><span data-stu-id="1133c-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="1133c-120">Это событие возникает каждый раз, когда пользователь фиксирует изменение значения ячейки.</span><span class="sxs-lookup"><span data-stu-id="1133c-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  <span data-ttu-id="1133c-121">Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.NewRowNeeded> событие, которое создает новый `Customer` объект, представляющий только что созданной строки.</span><span class="sxs-lookup"><span data-stu-id="1133c-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="1133c-122">Это событие возникает каждый раз, когда пользователь вводит строку для новых записей.</span><span class="sxs-lookup"><span data-stu-id="1133c-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  <span data-ttu-id="1133c-123">Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.RowValidated> событие, которое сохраняет новые или измененные строки в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="1133c-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="1133c-124">Это событие возникает каждый раз, когда пользователь изменяет текущую строку.</span><span class="sxs-lookup"><span data-stu-id="1133c-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  <span data-ttu-id="1133c-125">Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> событие, указывающее, является ли <xref:System.Windows.Forms.DataGridView.CancelRowEdit> событие произойдет в том случае, если пользователь восстанавливает строку, нажав клавишу ESC, дважды в режиме редактирования или один раз в другом режиме.</span><span class="sxs-lookup"><span data-stu-id="1133c-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="1133c-126">По умолчанию <xref:System.Windows.Forms.DataGridView.CancelRowEdit> происходит при восстановлении строки, если ни одной из ячеек в текущей строке были изменены, если не <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> свойству `true` в <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1133c-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="1133c-127">Это событие полезно в тех случаях, когда область фиксации определяется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1133c-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  <span data-ttu-id="1133c-128">Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.CancelRowEdit> событий, который удаляет значения `Customer` объект, представляющий текущую строку.</span><span class="sxs-lookup"><span data-stu-id="1133c-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="1133c-129">Это событие происходит, если пользователь восстанавливает строку, нажав клавишу ESC, дважды в режиме редактирования или один раз в другом режиме.</span><span class="sxs-lookup"><span data-stu-id="1133c-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="1133c-130">Это событие не происходит, если ячейки отсутствуют в текущей строке были изменены или если значение <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> было присвоено свойство `false` в <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1133c-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="1133c-131">Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.UserDeletingRow> событие, которое удаляет существующий `Customer` объекта из хранилища данных или отменяет несохраненный `Customer` объект, представляющий только что созданной строки.</span><span class="sxs-lookup"><span data-stu-id="1133c-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="1133c-132">Это событие возникает каждый раз, когда пользователь удаляет строку, при щелчке заголовка строки и нажав клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="1133c-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="1133c-133">Реализовать простой `Customers` класс для представления элементов данных, используемых в этом примере кода.</span><span class="sxs-lookup"><span data-stu-id="1133c-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="1133c-134">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="1133c-134">Testing the Application</span></span>  
 <span data-ttu-id="1133c-135">Теперь можно проверить форму, чтобы убедиться, что она правильно работает.</span><span class="sxs-lookup"><span data-stu-id="1133c-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="1133c-136">Чтобы проверить форму</span><span class="sxs-lookup"><span data-stu-id="1133c-136">To test the form</span></span>  
  
-   <span data-ttu-id="1133c-137">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="1133c-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="1133c-138">Вы увидите <xref:System.Windows.Forms.DataGridView> управления с тремя записями клиентов.</span><span class="sxs-lookup"><span data-stu-id="1133c-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="1133c-139">Можно изменить значения нескольких ячеек в строке и нажмите клавишу ESC, дважды в режиме редактирования и один раз за пределами режим редактирования, чтобы вернуть всю строку к исходным значениям.</span><span class="sxs-lookup"><span data-stu-id="1133c-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="1133c-140">Когда изменения, добавления или удаления строк в элементе управления `Customer` объектов в хранилище данных будут изменены, добавлены или удалены.</span><span class="sxs-lookup"><span data-stu-id="1133c-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1133c-141">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="1133c-141">Next Steps</span></span>  
 <span data-ttu-id="1133c-142">Это приложение позволяет основные события, необходимо обработать для реализации виртуального режима в <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1133c-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1133c-143">Вы можете улучшить это основное приложение несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="1133c-143">You can improve this basic application in a number of ways:</span></span>  
  
-   <span data-ttu-id="1133c-144">Реализуйте хранилище данных, которое кэширует значения из внешней базы данных.</span><span class="sxs-lookup"><span data-stu-id="1133c-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="1133c-145">Кэш извлекает и отменяет по необходимости, чтобы он содержал только необходимые для отображения при использовании небольшой объем памяти на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="1133c-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
-   <span data-ttu-id="1133c-146">Оптимизировать производительность хранилища данных в зависимости от требований.</span><span class="sxs-lookup"><span data-stu-id="1133c-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="1133c-147">Например можно компенсировать медленные сетевые подключения, а не ограничения памяти клиентского компьютера с помощью большего размера кэша, сводя к минимуму число запросов к базе данных.</span><span class="sxs-lookup"><span data-stu-id="1133c-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="1133c-148">Дополнительные сведения о кэшировании значений из внешней базы данных, см. в разделе [как: Реализация виртуального режима с JIT в загрузкой данных в Windows Forms элемента управления DataGridView](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="1133c-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1133c-149">См. также</span><span class="sxs-lookup"><span data-stu-id="1133c-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="1133c-150">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1133c-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1133c-151">Масштабирование элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1133c-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1133c-152">Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1133c-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="1133c-153">Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1133c-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
