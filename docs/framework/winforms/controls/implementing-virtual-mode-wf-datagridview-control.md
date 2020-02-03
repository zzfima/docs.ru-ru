---
title: Пошаговое руководство. Реализация виртуального режима в элементе управления DataGridView
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
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746519"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1a780-102">Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a780-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1a780-103">Если требуется отображать в элементе управления <xref:System.Windows.Forms.DataGridView> очень большие объемы табличных данных, можно задать для свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение `true` и явно управлять взаимодействием элемента управления с его хранилищем данных.</span><span class="sxs-lookup"><span data-stu-id="1a780-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="1a780-104">Это позволяет точно настроить производительность элемента управления в этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="1a780-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="1a780-105">Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет несколько событий, которые можно использовать для взаимодействия с пользовательским хранилищем данных.</span><span class="sxs-lookup"><span data-stu-id="1a780-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="1a780-106">В этом пошаговом руководстве описывается процесс реализации этих обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="1a780-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="1a780-107">В примере кода в этом разделе используется очень простой источник данных для иллюстрации целей.</span><span class="sxs-lookup"><span data-stu-id="1a780-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="1a780-108">В рабочем параметре обычно загружаются только строки, которые необходимо отобразить в кэш, а также обрабатывает события <xref:System.Windows.Forms.DataGridView> для взаимодействия с кэшем и его обновления.</span><span class="sxs-lookup"><span data-stu-id="1a780-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="1a780-109">Дополнительные сведения см. [в статье реализация виртуального режима с JIT-загрузкой данных в элементе управления Windows Forms DataGridView](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md) .</span><span class="sxs-lookup"><span data-stu-id="1a780-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="1a780-110">Чтобы скопировать код из этого раздела в виде отдельного списка, см. раздел [как реализовать виртуальный режим в элементе управления Windows Forms DataGridView](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="1a780-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="1a780-111">Создание формы</span><span class="sxs-lookup"><span data-stu-id="1a780-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="1a780-112">Реализация виртуального режима</span><span class="sxs-lookup"><span data-stu-id="1a780-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="1a780-113">Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="1a780-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="1a780-114">Следующий код содержит некоторую базовую инициализацию.</span><span class="sxs-lookup"><span data-stu-id="1a780-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="1a780-115">Он объявляет некоторые переменные, которые будут использоваться на последующих этапах, предоставляет метод `Main` и предоставляет простую структуру формы в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="1a780-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="1a780-116">Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, которое инициализирует элемент управления <xref:System.Windows.Forms.DataGridView> и заполняет хранилище данными образцами значений.</span><span class="sxs-lookup"><span data-stu-id="1a780-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="1a780-117">Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellValueNeeded>, которое извлекает запрошенное значение ячейки из хранилища данных, или объект `Customer`, который в данный момент находится в редактировании.</span><span class="sxs-lookup"><span data-stu-id="1a780-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="1a780-118">Это событие возникает каждый раз, когда элементу управления <xref:System.Windows.Forms.DataGridView> требуется закрасить ячейку.</span><span class="sxs-lookup"><span data-stu-id="1a780-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="1a780-119">Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellValuePushed>, которое хранит значение измененной ячейки в объекте `Customer`, представляющем редактируемую строку.</span><span class="sxs-lookup"><span data-stu-id="1a780-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="1a780-120">Это событие возникает каждый раз, когда пользователь фиксирует изменение значения ячейки.</span><span class="sxs-lookup"><span data-stu-id="1a780-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="1a780-121">Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.NewRowNeeded>, которое создает новый объект `Customer`, представляющий вновь созданную строку.</span><span class="sxs-lookup"><span data-stu-id="1a780-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="1a780-122">Это событие возникает каждый раз, когда пользователь вводит строку для новых записей.</span><span class="sxs-lookup"><span data-stu-id="1a780-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="1a780-123">Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.RowValidated>, которое сохраняет новые или измененные строки в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="1a780-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="1a780-124">Это событие возникает каждый раз, когда пользователь изменяет текущую строку.</span><span class="sxs-lookup"><span data-stu-id="1a780-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="1a780-125">Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>, которое указывает, произойдет ли событие <xref:System.Windows.Forms.DataGridView.CancelRowEdit>, когда пользователь получит сигнал о повторной версии строки, нажав клавишу ESC дважды в режиме редактирования или один раз за пределами режима редактирования.</span><span class="sxs-lookup"><span data-stu-id="1a780-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="1a780-126">По умолчанию <xref:System.Windows.Forms.DataGridView.CancelRowEdit> происходит при изменении версии строки, если какие-либо ячейки в текущей строке были изменены, если только свойство <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> не имеет значение `true` в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.</span><span class="sxs-lookup"><span data-stu-id="1a780-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="1a780-127">Это событие полезно, когда область фиксации определяется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a780-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="1a780-128">Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CancelRowEdit>, которое отменяет значения объекта `Customer`, представляющего текущую строку.</span><span class="sxs-lookup"><span data-stu-id="1a780-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="1a780-129">Это событие возникает, когда пользователь сигнализирует о повторной версии строки, нажав клавишу ESC дважды в режиме редактирования или один раз за пределами режима редактирования.</span><span class="sxs-lookup"><span data-stu-id="1a780-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="1a780-130">Это событие не происходит, если ни одна ячейка в текущей строке не была изменена или значение свойства <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> было задано как `false` в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.</span><span class="sxs-lookup"><span data-stu-id="1a780-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="1a780-131">Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.UserDeletingRow>, которое удаляет существующий объект `Customer` из хранилища данных или отменяет несохраненный объект `Customer`, представляющий вновь созданную строку.</span><span class="sxs-lookup"><span data-stu-id="1a780-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="1a780-132">Это событие возникает каждый раз, когда пользователь удаляет строку, щелкая заголовок строки и нажимая клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="1a780-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="1a780-133">Реализуйте простой `Customers` класс для представления элементов данных, используемых в этом примере кода.</span><span class="sxs-lookup"><span data-stu-id="1a780-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="1a780-134">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="1a780-134">Testing the Application</span></span>  
 <span data-ttu-id="1a780-135">Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="1a780-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="1a780-136">Тестирование формы</span><span class="sxs-lookup"><span data-stu-id="1a780-136">To test the form</span></span>  
  
- <span data-ttu-id="1a780-137">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="1a780-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="1a780-138">Вы увидите элемент управления <xref:System.Windows.Forms.DataGridView>, заполненный тремя записями клиентов.</span><span class="sxs-lookup"><span data-stu-id="1a780-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="1a780-139">Можно изменить значения нескольких ячеек в строке и дважды нажать клавишу ESC в режиме редактирования и один раз за пределами режима редактирования, чтобы восстановить исходные значения всей строки.</span><span class="sxs-lookup"><span data-stu-id="1a780-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="1a780-140">При изменении, добавлении или удалении строк в элементе управления `Customer` объекты в хранилище данных также изменяются, добавляются или удаляются.</span><span class="sxs-lookup"><span data-stu-id="1a780-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1a780-141">Next Steps</span><span class="sxs-lookup"><span data-stu-id="1a780-141">Next Steps</span></span>  
 <span data-ttu-id="1a780-142">Это приложение предоставляет базовое представление о событиях, которые необходимо решить для реализации виртуального режима в элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="1a780-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1a780-143">Вы можете улучшить это базовое приложение несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="1a780-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="1a780-144">Реализуйте хранилище данных, которое кэширует значения из внешней базы данных.</span><span class="sxs-lookup"><span data-stu-id="1a780-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="1a780-145">Кэш должен извлекать и удалять значения по мере необходимости, чтобы он содержал только то, что необходимо для вывода, при использовании небольшого объема памяти на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a780-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="1a780-146">Точная настройка производительности хранилища данных в зависимости от требований.</span><span class="sxs-lookup"><span data-stu-id="1a780-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="1a780-147">Например, может потребоваться компенсировать медленные сетевые подключения, а не ограничения памяти клиентского компьютера, используя больший размер кэша и свести к минимуму количество запросов к базе данных.</span><span class="sxs-lookup"><span data-stu-id="1a780-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="1a780-148">Дополнительные сведения о кэшировании значений из внешней базы данных см. в разделе [инструкции. Реализация виртуального режима с JIT-загрузкой данных в элементе управления Windows Forms DataGridView](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="1a780-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a780-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1a780-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="1a780-150">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a780-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1a780-151">Масштабирование элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a780-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1a780-152">Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a780-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="1a780-153">Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a780-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
