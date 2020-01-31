---
title: Реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
ms.openlocfilehash: 85c6877a9fc6a92752eb039da9d36e34811f8b77
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745067"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms
Одной из причин реализации виртуального режима в элементе управления <xref:System.Windows.Forms.DataGridView> является получение данных только по мере необходимости. Это называется *JIT-загрузкой данных*.  
  
 При работе с очень большой таблицей в удаленной базе данных, например, может возникнуть необходимость избежать задержек запуска, извлекая только те данные, которые необходимы для отображения и извлечения дополнительных данных, только когда пользователь прокручивает новые строки в представлении. Если на клиентских компьютерах, на которых выполняется приложение, имеется ограниченный объем памяти для хранения данных, может также потребоваться отменить неиспользуемые данные при извлечении новых значений из базы данных.  
  
 В следующих разделах описано, как использовать элемент управления <xref:System.Windows.Forms.DataGridView> с кэшем JIT.  
  
 Чтобы скопировать код из этого раздела в виде отдельного перечня, см. раздел [как реализовать виртуальный режим с JIT-загрузкой данных в элементе управления Windows Forms DataGridView](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>Форма  
 В следующем примере кода определяется форма, содержащая элемент управления <xref:System.Windows.Forms.DataGridView> только для чтения, который взаимодействует с `Cache` объектом через обработчик событий <xref:System.Windows.Forms.DataGridView.CellValueNeeded>. Объект `Cache` управляет локально хранимыми значениями и использует объект `DataRetriever` для получения значений из таблицы Orders образца базы данных Northwind. Объект `DataRetriever`, который реализует интерфейс `IDataPageRetriever`, необходимый для класса `Cache`, также используется для инициализации строк и столбцов элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 Типы `IDataPageRetriever`, `DataRetriever`и `Cache` описаны далее в этом разделе.  
  
> [!NOTE]
> Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>Интерфейс Идатапажеретриевер  
 В следующем примере кода определяется интерфейс `IDataPageRetriever`, который реализуется классом `DataRetriever`. Единственным методом, объявленным в этом интерфейсе, является метод `SupplyPageOfData`, для которого требуется начальный индекс строки и количество строк на одной странице данных. Эти значения используются средством реализации для получения подмножества данных из источника данных.  
  
 Объект `Cache` использует реализацию этого интерфейса во время создания для загрузки двух начальных страниц данных. Всякий раз, когда требуется некэшированное значение, кэш отбрасывает одну из этих страниц и запрашивает новую страницу, содержащую значение из `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>Класс "извлечение"  
 В следующем примере кода определяется класс `DataRetriever`, который реализует интерфейс `IDataPageRetriever` для получения страниц данных с сервера. Класс `DataRetriever` также предоставляет свойства `Columns` и `RowCount`, которые элемент управления <xref:System.Windows.Forms.DataGridView> использует для создания необходимых столбцов и для добавления соответствующего количества пустых строк в коллекцию <xref:System.Windows.Forms.DataGridView.Rows%2A>. Добавление пустых строк необходимо, чтобы элемент управления навести себя так, как будто содержит все данные в таблице. Это означает, что поле прокрутки на полосе прокрутки будет иметь соответствующий размер, и пользователь сможет получить доступ к любой строке в таблице. Строки заполняются обработчиком событий <xref:System.Windows.Forms.DataGridView.CellValueNeeded>, только если они прокручивается в представление.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Класс кэша  
 В следующем примере кода определяется класс `Cache`, который управляет двумя страницами данных, заполненных с помощью реализации `IDataPageRetriever`. Класс `Cache` определяет внутреннюю структуру `DataPage`, которая содержит <xref:System.Data.DataTable> для хранения значений на одной странице кэша и вычисляет индексы строк, представляющие верхние и нижние границы страницы.  
  
 Класс `Cache` загружает две страницы данных во время создания. Каждый раз, когда событие <xref:System.Windows.Forms.DataGridView.CellValueNeeded> запрашивает значение, объект `Cache` определяет, доступно ли значение на одной из двух страниц, и, если да, возвращает его. Если значение недоступно локально, то объект `Cache` определяет, какая из двух страниц наиболее востребована к отображаемым строкам, и заменяет эту страницу новой, содержащей запрошенное значение, которое затем возвращается.  
  
 При условии, что количество строк на странице данных совпадает с количеством строк, которые могут отображаться на экране одновременно, эта модель позволяет пользователям переноситься по таблице для эффективного возврата к последней просмотренной странице.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Дополнительные сведения  
 Приведенные выше примеры кода предоставляются как демонстрация JIT-загрузки данных. Вам потребуется изменить код для собственных нужд, чтобы добиться максимальной эффективности. Как минимум необходимо выбрать подходящее значение для количества строк на страницу данных в кэше. Это значение передается в конструктор `Cache`. Количество строк на странице не должно быть меньше числа строк, которые могут одновременно отображаться в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
 Для получения наилучших результатов необходимо провести тестирование производительности и тестирование на удобство использования, чтобы определить требования вашей системы и пользователей. Необходимо учитывать несколько факторов, включая объем памяти на клиентских компьютерах, на которых выполняется приложение, доступную пропускную способность сетевого подключения и задержку используемого сервера. Пропускную способность и задержку следует определять в периоды пикового использования.  
  
 Чтобы повысить производительность прокрутки приложения, можно увеличить объем данных, хранящихся локально. Однако для улучшения времени запуска следует избегать первоначальной загрузки слишком большого объема данных. Может потребоваться изменить класс `Cache`, чтобы увеличить количество страниц данных, которые он может хранить. Использование большего количества страниц данных может повысить эффективность прокрутки, но необходимо определить оптимальное количество строк на странице данных в зависимости от доступной пропускной способности и задержки сервера. При использовании небольших страниц доступ к серверу будет осуществляться чаще, но для возврата запрошенных данных потребуется меньше времени. Если задержка является более проблемой, чем пропускная способность, может потребоваться использовать большие страницы данных.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Виртуальный режим элемента управления DataGridView в Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Практическое руководство. Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
