---
title: "Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "примеры [Windows Forms], JIT-загрузка данных"
  - "JIT-загрузка данных"
  - "виртуальный режим, JIT-загрузка данных"
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms
Одной из причин реализации виртуального режима в элементе управления <xref:System.Windows.Forms.DataGridView> является получение данных только по мере необходимости в них.  Это называется *JIT\-загрузкой данных*.  
  
 Например, при работе с очень большой таблицей в удаленной базе данных требуется исключить задержки при запуске, получая только необходимые данные для отображения и извлекая дополнительные данные только тогда, когда пользователь прокручивает на экране новые строки.  Если на клиентском компьютере, где выполняется приложение, объем памяти для хранения данных ограничен, может возникнуть необходимость удаления неиспользуемых данных при извлечении новых значений из базы данных.  
  
 В следующем разделе описано, как использовать элемент управления <xref:System.Windows.Forms.DataGridView> с кэшем JIT.  
  
 Чтобы скопировать весь текст кода из этой темы, см. раздел [Практическое руководство. Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## Форма  
 В следующем примере кода определена форма, содержащая элемент управления <xref:System.Windows.Forms.DataGridView> только для чтения, который взаимодействует с объектом `Cache` при помощи обработчика событий <xref:System.Windows.Forms.DataGridView.CellValueNeeded>.  Объект `Cache` управляет значениями, хранящимися локально, и использует объект `DataRetriever` для извлечения значений из таблицы "Orders" примера базы данных "Northwind".  Объект `DataRetriever`, реализующий интерфейс `IDataPageRetriever`, который необходим для класса `Cache`, также используется для инициализации строк и столбцов элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 Типы `IDataPageRetriever`, `DataRetriever` и `Cache` описаны в далее в этом разделе.  
  
> [!NOTE]
>  Хранение в строке подключения конфиденциальных сведений, таких как пароль, может привести к снижению уровня защиты приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Дополнительные сведения см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## Интерфейс IDataPageRetriever  
 Следующий пример кода определяет интерфейс `IDataPageRetriever`, реализуемый классом `DataRetriever`.  Единственным методом, объявленным в этом интерфейсе, является метод `SupplyPageOfData`, для которого требуется начальный индекс строки и число строк на одной странице данных.  Эти значения используются средством реализации для извлечения подмножества данных из источника данных.  
  
 Объект `Cache` использует реализацию этого интерфейса во время построения для загрузки двух начальных страниц данных.  Каждый раз, когда требуется некэшированное значение, кэш очищает одну из этих страниц и запрашивает новую страницу с значением из `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## Класс DataRetriever  
 Следующий пример кода определяет класс `DataRetriever`, который реализует интерфейс `IDataPageRetriever` для извлечения страниц данных с сервера.  Класс `DataRetriever` также предоставляет свойства `Columns` и `RowCount`, которые элемент управления <xref:System.Windows.Forms.DataGridView> использует для создания необходимых столбцов и добавления соответствующего числа пустых строк в коллекцию <xref:System.Windows.Forms.DataGridView.Rows%2A>.  Добавление пустых строк необходимо для того, чтобы поведение элемента управления было таким, как если бы в нем содержались все данные в таблице.  Это означает, что ползунок полосы прокрутки будет иметь соответствующий размер, а пользователь сможет получить доступ к любой строке в таблице.  Строки заполняются обработчиком событий <xref:System.Windows.Forms.DataGridView.CellValueNeeded> в момент прокрутки на экране.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## Класс Cache  
 Следующий пример кода определяет класс `Cache`, который управляет двумя страницами данных, заполняемыми через реализацию `IDataPageRetriever`.  Класс `Cache` определяет внутреннюю структуру `DataPage`, которая содержит <xref:System.Data.DataTable> для хранения значений на одной странице кэша и которая вычисляет индексы строк, представляющие верхнюю и нижнюю границы страницы.  
  
 Класс `Cache` загружает две страницы данных во время построения.  Каждый раз, когда событие <xref:System.Windows.Forms.DataGridView.CellValueNeeded> запрашивает значение, объект `Cache` определяет, доступно ли значение на одной из двух его страниц, и если это так, то возвращает его.  Если значение локально не доступно, объект `Cache` определяет, какая из двух страниц дальше всего от отображаемых в данный момент строк и заменяет страницу новой с запрошенным значением, которое затем возвращается.  
  
 Допуская, что число строк на странице данных соответствует числу строк, которые могут быть отображены на экране одновременно, эта модель позволяет пользователям переходить по страницам таблицы, чтобы можно было быстрее вернуться на последнюю просмотренную страницу.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## Дополнительные сведения  
 Приведенные выше примеры кода предоставляются в качестве демонстрации JIT\-загрузки данных.  Для достижения максимальной эффективности код потребуется изменить в зависимости от необходимости.  По меньшей мере, потребуется выбрать соответствующее значение для числа строк на странице данных в кэше.  Это значение подставляется в конструктор `Cache`.  Число строк на странице не должно быть меньше числа строк, которые могут одновременно отображаться в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
 Для достижения наилучших результатов потребуется провести тестирование производительности для определения требований системы и пользователей.  Необходимо принять во внимание ряд факторов, в числе которых объем памяти на клиентском компьютере, где выполняется приложение, доступная пропускная способность используемого сетевого подключения и задержки сервера.  Пропускную способность и задержки следует определять в часы максимальной нагрузки.  
  
 Для повышения производительности приложения во время прокрутки можно увеличить объем локально хранящихся данных.  Однако, чтобы добиться лучшего времени запуска, изначально не следует загружать слишком много данных.  Можно попробовать изменить класс `Cache`, чтобы увеличить число страниц данных, которые могут храниться в нем.  Использование большего числа страниц данных делает прокрутку более эффективной, но идеальное число строк на странице данных можно определить исходя из доступной пропускной способности и задержек сервера.  При меньших страницах обращения к серверу будут выполняться чаще, но для возврата запрашиваемых данных потребуется меньше времени.  Если задержки более критичны, чем пропускная способность, можно подумать об использовании страниц данных большего размера.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Практическое руководство. Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)