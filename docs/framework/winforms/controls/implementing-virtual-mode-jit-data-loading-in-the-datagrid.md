---
title: Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms
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
ms.openlocfilehash: ad3ec7fb2e0012459bcf597ac9abee76c20b767e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540921"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms
Реализация виртуального режима в одной из причин <xref:System.Windows.Forms.DataGridView> управления является получение данных только по мере необходимости. Это называется *загрузка данных в момент*.  
  
 При работе с очень большими таблицами в удаленной базе данных, например, может потребоваться исключить задержки при запуске, извлекая только данные, необходимые для отображения и извлекая дополнительные данные только в том случае, когда пользователь прокручивает новых строк в представлении. Если клиентские компьютеры под управлением приложения имеют ограниченный объем памяти для хранения данных, может также потребоваться удаления неиспользуемых данных при извлечении новых значений из базы данных.  
  
 В следующих разделах описаны способы использования <xref:System.Windows.Forms.DataGridView> управления с кэшем на времени.  
  
 Скопируйте код из этой темы, в разделе [как: реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>Формы  
 В следующем примере кода определяется форму, содержащую только для чтения <xref:System.Windows.Forms.DataGridView> управления, который взаимодействует с `Cache` посредством <xref:System.Windows.Forms.DataGridView.CellValueNeeded> обработчика событий. `Cache` Управляет значениями, хранящимися локально и использует `DataRetriever` объекта для извлечения значения из таблицы Orders учебной базы данных "Борей". `DataRetriever` Объект, который реализует `IDataPageRetriever` интерфейс, необходимый `Cache` класса, также используется для инициализации <xref:System.Windows.Forms.DataGridView> управления строками и столбцами.  
  
 `IDataPageRetriever`, `DataRetriever`, И `Cache` типы описаны далее в этом разделе.  
  
> [!NOTE]
>  Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>Интерфейс IDataPageRetriever  
 В следующем примере кода определяется `IDataPageRetriever` интерфейс, который реализуется `DataRetriever` класса. Является единственным методом, объявленным в этом интерфейсе `SupplyPageOfData` метод, который требуется начальный индекс строки и число строк на одной странице данных. Эти значения используются средством реализации для извлечения подмножества данных из источника данных.  
  
 Объект `Cache` объект использует реализацию этого интерфейса во время построения для загрузки двух начальных страниц данных. Каждый раз, когда требуется некэшированные значение, кэш очищает одну из этих страниц и запрашивает новую страницу с значением из `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>Класс DataRetriever  
 В следующем примере кода определяется `DataRetriever` класса, который реализует `IDataPageRetriever` интерфейс для извлечения страниц данных с сервера. `DataRetriever` Класс также предоставляет `Columns` и `RowCount` свойства, который <xref:System.Windows.Forms.DataGridView> управления используется для создания необходимых столбцов и добавления соответствующего числа пустых строк для <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции. Добавление пустых строк необходим, чтобы элемент управления будет действует так, будто он содержит все данные в таблице. Это означает, что ползунка полосы прокрутки будет иметь соответствующий размер, что пользователь будет иметь доступ к любой строки в таблице. Строки заполняются <xref:System.Windows.Forms.DataGridView.CellValueNeeded> обработчик событий только в том случае, если они находятся в результате прокрутки.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Класс Cache  
 В следующем примере кода определяется `Cache` класс, который управляет двумя страницами данных заполняется через `IDataPageRetriever` реализации. `Cache` Класс определяет внутреннюю `DataPage` структуру, которая содержит <xref:System.Data.DataTable> для хранения значений в одном кэше страницы и которая вычисляет индексы строк, представляющие верхнюю и нижнюю границы страницы.  
  
 `Cache` Класс загружает две страницы данных во время построения. Каждый раз, когда <xref:System.Windows.Forms.DataGridView.CellValueNeeded> событий запрашивает значение, `Cache` определяет объект, если значение доступно в одной из двух его страницы, а также, если это так, то возвращает его. Если значение локально не доступно, `Cache` определяет, какая из двух страниц дальше всего от текущих отображаемых строк и заменяет страницу новой с запрошенным значением, которое затем возвращается.  
  
 Предположим, что количество строк на странице данных является таким же, как количество строк, которые отображаются на экране одновременно, эта модель позволяет пользователям постраничного просмотра в таблице эффективно вернуться на страницу Недавно просмотренные.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Дополнительные сведения  
 В предыдущих примерах кода предоставляются в качестве демонстрации загрузка данных в момент. Необходимо изменить код для своих потребностей для достижения максимальной эффективности. Как минимум необходимо выбрать соответствующее значение для числа строк на странице данных в кэше. Это значение передается в `Cache` конструктора. Количество строк на странице должно быть не меньше, чем количество строк, которые могут одновременно отображаться в вашей <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
 Для получения наилучших результатов необходимо провести тестирование производительности для определения требований системы и пользователей. Несколько факторов, которые необходимо принимать во внимание включают объем памяти в клиентских компьютеров, выполняющих приложение, доступная пропускная способность сетевого подключения и задержки сервера, используемого. Полосы пропускания и задержки должно определяться во время активного использования.  
  
 Для повышения быстродействия приложения, можно увеличить объем данных, хранящихся локально. Чтобы сократить время запуска, однако следует загружать слишком много данных изначально. Может потребоваться изменить `Cache` класса, чтобы увеличить число страниц данных, он позволяет хранить. С помощью нескольких страниц данных может повысить эффективность прокрутки, но вам потребуется определить оптимальное количество строк на странице данных, в зависимости от доступной пропускной способности и задержке сервера. При меньших страницах сервер будет осуществляться чаще, но будет занимать меньше времени, чтобы вернуть запрошенные данные. Если задержка больше, чем пропускной способности на проблему, можно использовать страниц данных большего размера.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Практическое руководство. Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
