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
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
Если требуется отображать в элементе управления <xref:System.Windows.Forms.DataGridView> очень большие объемы табличных данных, можно задать для свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение `true` и явно управлять взаимодействием элемента управления с его хранилищем данных. Это позволяет точно настроить производительность элемента управления в этой ситуации.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет несколько событий, которые можно использовать для взаимодействия с пользовательским хранилищем данных. В этом пошаговом руководстве описывается процесс реализации этих обработчиков событий. В примере кода в этом разделе используется очень простой источник данных для иллюстрации целей. В рабочем параметре обычно загружаются только строки, которые необходимо отобразить в кэш, а также обрабатывает события <xref:System.Windows.Forms.DataGridView> для взаимодействия с кэшем и его обновления. Дополнительные сведения см. [в статье реализация виртуального режима с JIT-загрузкой данных в элементе управления Windows Forms DataGridView](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md) .  
  
 Чтобы скопировать код из этого раздела в виде отдельного списка, см. раздел [как реализовать виртуальный режим в элементе управления Windows Forms DataGridView](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Создание формы  
  
#### <a name="to-implement-virtual-mode"></a>Реализация виртуального режима  
  
1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий элемент управления <xref:System.Windows.Forms.DataGridView>.  
  
     Следующий код содержит некоторую базовую инициализацию. Он объявляет некоторые переменные, которые будут использоваться на последующих этапах, предоставляет метод `Main` и предоставляет простую структуру формы в конструкторе класса.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, которое инициализирует элемент управления <xref:System.Windows.Forms.DataGridView> и заполняет хранилище данными образцами значений.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellValueNeeded>, которое извлекает запрошенное значение ячейки из хранилища данных, или объект `Customer`, который в данный момент находится в редактировании.  
  
     Это событие возникает каждый раз, когда элементу управления <xref:System.Windows.Forms.DataGridView> требуется закрасить ячейку.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellValuePushed>, которое хранит значение измененной ячейки в объекте `Customer`, представляющем редактируемую строку. Это событие возникает каждый раз, когда пользователь фиксирует изменение значения ячейки.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.NewRowNeeded>, которое создает новый объект `Customer`, представляющий вновь созданную строку.  
  
     Это событие возникает каждый раз, когда пользователь вводит строку для новых записей.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.RowValidated>, которое сохраняет новые или измененные строки в хранилище данных.  
  
     Это событие возникает каждый раз, когда пользователь изменяет текущую строку.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>, которое указывает, произойдет ли событие <xref:System.Windows.Forms.DataGridView.CancelRowEdit>, когда пользователь получит сигнал о повторной версии строки, нажав клавишу ESC дважды в режиме редактирования или один раз за пределами режима редактирования.  
  
     По умолчанию <xref:System.Windows.Forms.DataGridView.CancelRowEdit> происходит при изменении версии строки, если какие-либо ячейки в текущей строке были изменены, если только свойство <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> не имеет значение `true` в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>. Это событие полезно, когда область фиксации определяется во время выполнения.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CancelRowEdit>, которое отменяет значения объекта `Customer`, представляющего текущую строку.  
  
     Это событие возникает, когда пользователь сигнализирует о повторной версии строки, нажав клавишу ESC дважды в режиме редактирования или один раз за пределами режима редактирования. Это событие не происходит, если ни одна ячейка в текущей строке не была изменена или значение свойства <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> было задано как `false` в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.UserDeletingRow>, которое удаляет существующий объект `Customer` из хранилища данных или отменяет несохраненный объект `Customer`, представляющий вновь созданную строку.  
  
     Это событие возникает каждый раз, когда пользователь удаляет строку, щелкая заголовок строки и нажимая клавишу DELETE.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Реализуйте простой `Customers` класс для представления элементов данных, используемых в этом примере кода.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.  
  
#### <a name="to-test-the-form"></a>Тестирование формы  
  
- Скомпилируйте и запустите приложение.  
  
     Вы увидите элемент управления <xref:System.Windows.Forms.DataGridView>, заполненный тремя записями клиентов. Можно изменить значения нескольких ячеек в строке и дважды нажать клавишу ESC в режиме редактирования и один раз за пределами режима редактирования, чтобы восстановить исходные значения всей строки. При изменении, добавлении или удалении строк в элементе управления `Customer` объекты в хранилище данных также изменяются, добавляются или удаляются.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Это приложение предоставляет базовое представление о событиях, которые необходимо решить для реализации виртуального режима в элементе управления <xref:System.Windows.Forms.DataGridView>. Вы можете улучшить это базовое приложение несколькими способами:  
  
- Реализуйте хранилище данных, которое кэширует значения из внешней базы данных. Кэш должен извлекать и удалять значения по мере необходимости, чтобы он содержал только то, что необходимо для вывода, при использовании небольшого объема памяти на клиентском компьютере.  
  
- Точная настройка производительности хранилища данных в зависимости от требований. Например, может потребоваться компенсировать медленные сетевые подключения, а не ограничения памяти клиентского компьютера, используя больший размер кэша и свести к минимуму количество запросов к базе данных.  
  
 Дополнительные сведения о кэшировании значений из внешней базы данных см. в разделе [инструкции. Реализация виртуального режима с JIT-загрузкой данных в элементе управления Windows Forms DataGridView](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
