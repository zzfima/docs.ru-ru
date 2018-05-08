---
title: Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
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
ms.openlocfilehash: 52e93ebe0b2903fdf2fe97f4ce812331e740f8b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
Если вы хотите отобразить очень большому количеству табличные данные в <xref:System.Windows.Forms.DataGridView> управления, можно задать <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойства `true` и явным образом управлять взаимодействием элемента управления с хранилищем данных. Это позволяет оптимизировать производительность элемента управления в этой ситуации.  
  
 <xref:System.Windows.Forms.DataGridView> Управления предоставляет несколько событий, которые могут обрабатываться для взаимодействия с пользовательским хранилищем данных. В этом пошаговом руководстве помогает выполнить процесс реализации эти обработчики событий. В примере кода в этом разделе использует очень простого источника данных для наглядности. В производственной среде, обычно загружаются только строки, необходимые для отображения в кэше и обработки <xref:System.Windows.Forms.DataGridView> событий для взаимодействия с кэшем и его обновления. Дополнительные сведения см. в разделе [реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Скопируйте код из этой темы, в разделе [как: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Создание формы  
  
#### <a name="to-implement-virtual-mode"></a>Чтобы реализовать виртуальный режим  
  
1.  Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержит <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
     В следующем коде содержатся некоторые основные инициализации. Он объявляется несколько переменных, которые будут использоваться на последующих этапах, предоставляет `Main` метода и предоставляет простой макет формы в конструкторе класса.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  Реализуйте обработчик для формы <xref:System.Windows.Forms.Form.Load> событие, которое инициализирует <xref:System.Windows.Forms.DataGridView> управления и заполняет значениями образец хранилища данных.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  Реализуйте обработчик для <xref:System.Windows.Forms.DataGridView.CellValueNeeded> событие, которое извлекает запрошенное значение ячейки из хранилища данных или `Customer` объекта, находящегося в режиме редактирования.  
  
     Это событие возникает при изменении <xref:System.Windows.Forms.DataGridView> элемента управления необходим для рисования ячейки.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  Реализуйте обработчик для <xref:System.Windows.Forms.DataGridView.CellValuePushed> событие, которое сохраняет измененное значение ячейки в `Customer` объект, представляющий редактируемой строки. Это событие возникает каждый раз, когда пользователь подтверждает изменение значения ячейки.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  Реализуйте обработчик для <xref:System.Windows.Forms.DataGridView.NewRowNeeded> событие, которое создает новый `Customer` объект, представляющий только что созданной строки.  
  
     Это событие возникает каждый раз, когда пользователь вводит строку для новых записей.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  Реализуйте обработчик для <xref:System.Windows.Forms.DataGridView.RowValidated> событие, которое сохраняет новых или измененных строк в хранилище данных.  
  
     Это событие возникает каждый раз, когда пользователь изменяет текущую строку.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  Реализовать обработчик для <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> событие, указывающее, является ли <xref:System.Windows.Forms.DataGridView.CancelRowEdit> события возникают в том случае, если пользователь восстанавливает строку, нажав клавишу ESC два раза в режиме редактирования или один раз в другом режиме.  
  
     По умолчанию <xref:System.Windows.Forms.DataGridView.CancelRowEdit> происходит при восстановлении строки, если все ячейки в текущей строке были изменены, пока не <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> свойству `true` в <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> обработчика событий. Это событие полезно в тех случаях, когда область фиксации определяется во время выполнения.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  Реализуйте обработчик для <xref:System.Windows.Forms.DataGridView.CancelRowEdit> событий, который удаляет значения `Customer` объект, представляющий текущую строку.  
  
     Это событие возникает, если пользователь восстанавливает строку, нажав клавишу ESC два раза в режиме редактирования или один раз в другом режиме. Это событие не происходит, если ячейки отсутствуют в текущей строке были изменены или если значение <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> свойства `false` в <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> обработчика событий.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Реализуйте обработчик для <xref:System.Windows.Forms.DataGridView.UserDeletingRow> событий, который удаляет существующий `Customer` объекта из хранилища данных или отменяет несохраненный `Customer` объект, представляющий только что созданной строки.  
  
     Это событие возникает каждый раз, когда пользователь удаляет строку, щелкнув заголовок строки и нажав клавишу DELETE.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Реализовать простой `Customers` класс для представления элементов данных, используемых в этом примере кода.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться в том, что оно правильно работает.  
  
#### <a name="to-test-the-form"></a>Чтобы проверить форму  
  
-   Скомпилируйте и запустите приложение.  
  
     Вы увидите <xref:System.Windows.Forms.DataGridView> управления заполняются три записи клиента. Можно изменять значения нескольких ячеек в строке и нажмите клавишу ESC два раза в режиме редактирования и один раз за пределами режим редактирования, чтобы восстановить исходные значения во всей строке. Если изменения, добавления или удаления строк в элементе управления `Customer` изменен, добавлен или также удалены объекты в хранилище данных.  
  
## <a name="next-steps"></a>Следующие шаги  
 Это приложение позволяет основные события, необходимо обработать для реализации виртуального режима в <xref:System.Windows.Forms.DataGridView> элемента управления. Можно улучшить это основное приложение несколькими способами:  
  
-   Реализация хранилища данных, который кэширует значения из внешней базы данных. Кэш извлекает и отменяет значения по мере необходимости, чтобы он содержал только необходимые для отображения при использовании небольшой объем памяти на клиентском компьютере.  
  
-   Оптимизировать производительность хранилища данных в зависимости от требований. Например может потребоваться компенсировать медленное сетевое соединение, а не ограничения оперативной памяти на клиентском компьютере, используя размер кэш-памяти и уменьшает количество запросов к базе данных.  
  
 Дополнительные сведения о кэшировании значений из внешней базы данных см. в разделе [как: реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
