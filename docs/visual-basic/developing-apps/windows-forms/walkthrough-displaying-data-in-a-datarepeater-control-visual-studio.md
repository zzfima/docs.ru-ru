---
title: Пошаговое руководство. Отображение данных в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
ms.openlocfilehash: 8e64a819e9670a29e97140a32c81f5ff9006f83e
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231518"
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a>Пошаговое руководство. Отображение данных в элементе управления DataRepeater (Visual Studio)
Это пошаговое руководство содержит базовый сценарий для отображения связанных данных в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> от начала и до конца.  
  
## <a name="prerequisite"></a>Предварительные требования  
 В данном пошаговом руководстве требуется доступ к учебной базе данных Northwind.  
  
 Если база данных не установлена на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка примеров баз данных](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
## <a name="overview"></a>Обзор  
 Данное пошаговое руководство состоит из четырех основных задач.  
  
-   Создание решения.  
  
-   Добавление элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
-   Добавление источника данных.  
  
-   Добавление элементов управления с привязкой к данным.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a>Создание решения DataRepeater  
 На первом шаге создаются проект и решение.  
  
#### <a name="to-create-a-datarepeater-solution"></a>Создание решения DataRepeater  
  
1.  В меню **Файл** Visual Studio выберите команду **Создать проект**.  
  
2.  В области **Типы проектов** диалогового окна **Создать проект** разверните узел **Visual Basic**, а затем щелкните **Windows**.  
  
3.  Выберите **Приложение Windows Forms** в области **Шаблоны**.  
  
4.  В поле **Имя файла** введите `DataRepeaterApp`.  
  
5.  Нажмите кнопку **ОК**.  
  
     Откроется конструктор Windows Forms.  
  
6.  Выберите форму в конструкторе Windows Forms. В окне **Свойства** присвойте свойству **Размер** значение `800, 700`.  
  
## <a name="adding-a-datarepeater-control"></a>Добавление элемента управления DataRepeater  
 На этом шаге в форму добавляется элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
#### <a name="to-add-a-datarepeater-control"></a>Добавление элемента управления DataRepeater  
  
1.  В меню **Вид** выберите пункт **Панель элементов**.  
  
     Откроется **Панель элементов** .  
  
2.  Перейдите на вкладку **Visual Basic PowerPacks** .  
  
3.  Перетащите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> в форму **Form1**.  
  
4.  В окне "Свойства" присвойте свойству **Расположение** значение `0, 25`.  
  
5.  Установите значение свойства **Размер** равным `460, 600`.  
  
## <a name="adding-a-data-source"></a>Добавление источника данных  
 На этом шаге добавляется источник данных для элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
#### <a name="to-add-a-data-source"></a>Добавление источника данных  
  
1.  В меню **Данные** выберите команду **Показать источники данных**.  
  
2.  В окне **Источники данных** выберите **Добавить новый источник данных**.  
  
3.  На странице **Выбор типа источника данных** выберите элемент **База данных** и нажмите **Далее**.  
  
4.  На странице **Выбор подключения к базе данных** выполните одно из следующих действий:  
  
    -   Если подключение к учебной базе данных "Борей" доступно в раскрывающемся списке, то выберите его.  
  
         - или -  
  
    -   Нажмите кнопку **Создать подключение** для создания подключения к данным. Дополнительные сведения см. в разделе [Добавление новых подключений](/visualstudio/data-tools/add-new-connections).  
  
5.  Если базе данных требуется пароль, выберите параметр для включения конфиденциальных данных и щелкните **Далее**.  
  
    > [!NOTE]
    >  Если появится диалоговое окно, нажмите кнопку **Да** , чтобы сохранить файл в проекте.  
  
6.  На странице **Сохранение подключения в файле конфигурации приложения** нажмите кнопку **Далее** .  
  
7.  Разверните узел **Таблицы** на странице **Выбор объектов базы данных** .  
  
8.  Установите флажки для таблиц **Клиенты** и **Заказы** , а затем нажмите кнопку **Готово**.  
  
     **NorthwindDataSet** добавляется в проект, и таблицы **Клиенты** и **Заказы** отображаются в окне **Источники данных** .  
  
## <a name="adding-data-bound-controls"></a>Добавление элементов управления с привязкой к данным  
 На этом шаге элементы управления с привязкой к данным добавляются в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
#### <a name="to-add-data-bound-controls"></a>Чтобы добавить элементы управления с привязкой к данным  
  
1.  В окне **Источники данных** выберите узел верхнего уровня для таблицы **Клиенты** .  
  
2.  Измените тип удаления таблицы на **Сведения** , выбрав **Сведения** в раскрывающемся списке в узле таблицы.  
  
3.  Выберите узел таблицы **Клиенты** и перетащите его в область шаблона (верхняя часть) элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
     Элемент управления <xref:System.Windows.Forms.BindingNavigator> добавляется в форму, а компоненты **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**и **CustomersBindingNavigator** добавляются в область компонентов.  
  
4.  Выберите все поля и их связанные подписи и разместите их у левого края области шаблона элемента.  
  
5.  Выберите последние пять полей (**Область**, **Почтовый индекс**, **Страна**, **Телефон**и **Факс**) и их связанные подписи и поместите их вверху справа от первых шести полей.  
  
6.  Выберите шаблон элемента (верхняя область элемента управления).  
  
7.  В окне "Свойства" присвойте свойству **Размер** значение `427, 170`.  
  
 Теперь у вас есть рабочее приложение, которое будет отображать повторяющийся список клиентов. Можно нажать клавишу F5, чтобы запустить приложение, изменить данные и добавить или удалить записи клиентов.  
  
 На следующих необязательных этапах вы узнаете, как настроить элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
## <a name="next-steps-optional"></a>Дальнейшие действия (необязательно)  
 Эта часть пошагового руководства состоит из четырех дополнительных задач.  
  
-   Изменение внешнего вида элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
-   Запрет добавления или удаления записей пользователями.  
  
-   Добавление функции поиска в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
-   Добавление основной таблицы и таблицы сведений в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a>Изменение внешнего вида элемента управления DataRepeater  
 На этом необязательном шаге выполняется изменение `BackColor` элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> во время разработки. Можно также добавить код для отображения столбцов с чередованием цвета и условного изменения `ForeColor` подписи.  
  
#### <a name="to-change-the-appearance-of-the-control"></a>Изменение внешнего вида элемента управления  
  
1.  В конструкторе Windows Forms выберите основную (нижнюю) область элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
2.  В окне "Свойства" задайте свойству `BackColor` значение "Белый".  
  
3.  Дважды щелкните <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> , чтобы открыть редактор кода.  
  
4.  В редакторе кода в раскрывающемся списке выберите **DrawItem**.  
  
5.  В обработчике событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> добавьте следующий код для изменения `BackColor`:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  В обработчике событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> добавьте следующий код для изменения `ForeColor` подписи в зависимости от условия:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  Нажмите клавишу F5, чтобы запустить приложение и просмотреть настройки.  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a>Запрет добавления или удаления записей пользователями  
 На этом необязательном шаге добавляется код, который запрещает пользователям добавлять или удалять записи в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a>Запрет добавления или удаления записей пользователями  
  
1.  В конструкторе Windows Forms дважды щелкните форму, чтобы открыть редактор кода.  
  
2.  Добавьте следующий код в событие `Form_Load` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  В раскрывающемся списке "Имя класса" выберите **BindingNavigatorDeleteItem**. В раскрывающемся списке "Имя метода" выберите **EnabledChanged**.  
  
4.  Добавьте следующий код в обработчик событий `BindingNavigatorDeleteItem_EnabledChanged` .  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  Этот шаг необходим, так как <xref:System.Windows.Forms.BindingSource> будет активировать кнопку **DeleteItem** при каждом изменении текущей записи.  
  
5.  Нажмите клавишу F5 для запуска приложения. Обратите внимание, что кнопка **DeleteItem** отключена и вы не можете удалять элементы с помощью клавиши DELETE.  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a>Добавление функции поиска в элемент управления DataRepeater  
 На этом необязательном шаге реализуется возможность поиска значения в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> . При нахождении искомой строки элемент управления выбирает элемент, содержащий значение, и прокручивает элемент в представлении.  
  
#### <a name="to-add-search-capability"></a>Добавление функции поиска  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TextBox> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
     Расположите его под элементом управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
2.  В окне "Свойства" измените значение свойства **Имя** на **SearchTextBox**.  
  
3.  Перетащите элемент управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> . Расположите его под элементом управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
4.  В окне "Свойства" измените значение свойства **Имя** на **SearchButton**. Задайте для свойства **Текст** значение **Поиск**.  
  
5.  Дважды щелкните элемент управления <xref:System.Windows.Forms.Button> , чтобы открыть редактор кода, и добавьте следующий код в обработчик событий `SearchButton_Click` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  Нажмите клавишу F5 для запуска приложения. Введите код клиента в **SearchTextBox** и нажмите кнопку **Поиск** .  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a>Добавление основной таблицы и таблицы сведений в элемент управления DataRepeater  
 На этом необязательном шаге добавляется второй элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> для отображения связанных заказов для каждого клиента.  
  
#### <a name="to-add-a-master-and-detail-table"></a>Добавление основной таблицы и таблицы сведений  
  
1.  Перетащите второй элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> с вкладки **Visual Basic PowerPacks** на **панели инструментов** в форму.  
  
2.  В окне "Свойства" присвойте свойству **Расположение** значение `465, 25`.  
  
3.  Установите значение свойства **Размер** равным `315, 600`.  
  
4.  В окне **Источники данных** разверните узел таблицы **Клиенты** и выберите узел сведений для таблицы **Заказы** .  
  
5.  Измените тип удаления таблицы **Заказы** на "Сведения", выбрав **Сведения** в раскрывающемся списке в узле таблицы.  
  
6.  Перетащите этот узел таблицы **Заказы** в область шаблона (верхняя часть) второго элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
     Компоненты **OrdersBindingSource** и **OrdersTableAdapter** добавляются в область компонентов.  
  
7.  Нажмите клавишу F5 для запуска приложения. При выборе каждого клиента в первом элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> заказы для этого клиента отображаются во втором элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Изменение структуры элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [Как: создать Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
