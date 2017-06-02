---
title: "Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "данные [Windows Forms], управление большими наборами данных"
  - "DataGridView - элемент управления [Windows Forms], большие наборы данных"
  - "DataGridView - элемент управления [Windows Forms], виртуальный режим"
  - "виртуальный режим, пошаговые руководства"
  - "пошаговые руководства [Windows Forms], DataGridView - элемент управления"
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
Если в элементе управления <xref:System.Windows.Forms.DataGridView> требуется отобразить большой объем табличных данных, можно задать для свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение `true` и явным образом управлять взаимодействием элемента управления с хранилищем данных.  Это позволяет управлять производительностью элемента управления в такой ситуации.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет несколько событий, которые могут обрабатываться для взаимодействия с пользовательским хранилищем данных.  Процесс реализации таких обработчиков событий описан в данном пошаговом руководстве.  В примере кода в этом разделе для наглядности используется очень простой источник данных.  На практике обычно загружаются только строки, необходимые для отображения в кэше, а события <xref:System.Windows.Forms.DataGridView> обрабатываются для взаимодействия с кэшем и его обновления.  Дополнительные сведения содержатся в разделе [Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
 Чтобы скопировать весь текст кода из этой темы, см. ссылку [Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## Создание формы  
  
#### Чтобы реализовать виртуальный режим  
  
1.  Создайте производный от <xref:System.Windows.Forms.Form> класс, который содержит элемент управления <xref:System.Windows.Forms.DataGridView>.  
  
     В следующем коде реализована начальная стадия инициализации.  Объявлены некоторые переменные, которые будут использоваться позднее, предоставлен метод `Main` и предоставлен простой макет формы в конструкторе класса.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, который инициализирует элемент управления <xref:System.Windows.Forms.DataGridView> и заполняет хранилище данных образцами значений.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellValueNeeded>, который извлекает запрошенное значение ячейки из хранилища данных или объекта `Customer`, находящегося в режиме редактирования.  
  
     Это событие происходит каждый раз, когда элементу управления <xref:System.Windows.Forms.DataGridView> требуется прорисовать ячейку.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellValuePushed>, который сохраняет измененное значение ячейки в объекте `Customer`, представляющем отредактированную строку.  Это событие происходит каждый раз, когда пользователь подтверждает изменение значения ячейки.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.NewRowNeeded>, который создает новый объект `Customer`, представляющий созданную строку.  
  
     Это событие происходит каждый раз, когда пользователь входит в строку для добавления новых записей.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.RowValidated>, который сохраняет новые или измененные строки в хранилище данных.  
  
     Это событие происходит каждый раз, когда пользователь изменяет текущую строку.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>, который указывает, будет ли происходить событие <xref:System.Windows.Forms.DataGridView.CancelRowEdit> в случае, если пользователь восстанавливает строку, нажав ESC два раза в режиме редактирования или один раз в другом режиме.  
  
     По умолчанию <xref:System.Windows.Forms.DataGridView.CancelRowEdit> происходит при восстановлении строки, если любые ячейки в текущей строке были изменены, за исключением случая, когда для свойства <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName> задано значение `true` в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.  Это событие наиболее эффективно, если область фиксации определяется во время выполнения.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CancelRowEdit>, который отменяет значения объекта `Customer`, представляющего текущую строку.  
  
     Это событие происходит, если пользователь восстанавливает строку, нажав ESC два раза в режиме редактирования или один раз в другом режиме.  Это событие не происходит, если ячейки в текущей строке не были изменены или для свойства <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName> было задано значение `false` в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.UserDeletingRow>, который удаляет существующий объект `Customer` из хранилища данных или отменяет несохраненный объект `Customer`, представляющий созданную строку.  
  
     Это событие происходит каждый раз, когда пользователь удаляет строку, щелкнув по заголовку строки и нажав клавишу DELETE.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Реализуйте простой класс `Customers` для представления элементов данных, используемых в этом примере кода.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она работает так, как ожидалось.  
  
#### Чтобы проверить форму, выполните следующие действия:  
  
-   Скомпилируйте и запустите приложение.  
  
     Появится элемент управления <xref:System.Windows.Forms.DataGridView> с тремя записями клиентов.  Чтобы вернуть исходные значения во всей строке после изменения значений нескольких ячеек этой строки, можно нажать клавишу ESC два раза в режиме редактирования или один раз в другом режиме.  При изменении, добавлении или удалении строк в элементе управления, также изменяются, добавляются или удаляются объекты `Customer` в хранилище данных.  
  
## Следующие действия  
 Это приложение позволяет в общем понять, какие события необходимо обработать для реализации виртуального режима в элементе управления <xref:System.Windows.Forms.DataGridView>.  Это основное приложение можно улучшить несколькими способами.  
  
-   Реализуйте хранилище данных, кэширующее значения из внешней базы данных.  Кэш извлекает и отменяет значения по мере необходимости таким образом, что в нем содержатся только необходимые для отображения данные — при этом сокращается потребление ресурсов памяти на клиентском компьютере.  
  
-   Выполните точную настройку производительности хранилища данных в зависимости от конкретных требований.  Например, может потребоваться компенсировать медленное сетевое соединение, а не ограничения оперативной памяти компьютера клиента. В таком случае можно использовать кэш с увеличенным размером, чтобы свести к минимуму количество запросов к базе данных.  
  
 Дополнительные сведения о кэшировании значений из внешней базы данных содержатся по ссылке [Практическое руководство. Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## См. также  
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
 [Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)   
 [Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)