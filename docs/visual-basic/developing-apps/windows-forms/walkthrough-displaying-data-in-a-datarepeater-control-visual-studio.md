---
title: "Пошаговое руководство: Отображение данных в элементе управления DataRepeater (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 09f15c94c3d5a3387935c8d3f4758c0ecfd7cfcd
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a>Пошаговое руководство. Отображение данных в элементе управления DataRepeater (Visual Studio)
Это пошаговое руководство содержит базовый сценарий начало окончание для отображения связанных данных в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="prerequisite"></a>Предварительные требования  
 В данном пошаговом руководстве требуется доступ к учебной базе данных Northwind.  
  
 Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла [Центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088). Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).  
  
## <a name="overview"></a>Обзор  
 Данное пошаговое руководство состоит из четырех основных задач.  
  
-   Создание решения.  
  
-   Добавление <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Добавление источника данных.  
  
-   Добавление элементов управления с привязкой к данным.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
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
 На этом этапе можно добавить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>в форму элемент управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-datarepeater-control"></a>Добавление элемента управления DataRepeater  
  
1.  В меню **Вид** выберите пункт **Панель элементов**.  
  
     Откроется **Панель элементов** .  
  
2.  Перейдите на вкладку **Visual Basic PowerPacks** .  
  
3.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления **Form1**.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  В окне "Свойства" присвойте свойству **Расположение** значение `0, 25`.  
  
5.  Установите значение свойства **Размер** равным `460, 600`.  
  
## <a name="adding-a-data-source"></a>Добавление источника данных  
 На этом шаге добавьте источник данных для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-data-source"></a>Добавление источника данных  
  
1.  В меню **Данные** выберите команду **Показать источники данных**.  
  
2.  В окне **Источники данных** выберите **Добавить новый источник данных**.  
  
3.  На странице **Выбор типа источника данных** выберите элемент **База данных** и нажмите **Далее**.  
  
4.  На странице **Выбор подключения к базе данных** выполните одно из следующих действий:  
  
    -   Если подключение к учебной базе данных "Борей" доступно в раскрывающемся списке, то выберите его.  
  
         -или-  
  
    -   Нажмите кнопку **Создать подключение** для создания подключения к данным. Дополнительные сведения см. в разделе [Практическое руководство: создание подключений к базам данных SQL Server](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).  
  
5.  Если базе данных требуется пароль, выберите параметр для включения конфиденциальных данных и щелкните **Далее**.  
  
    > [!NOTE]
    >  Если появится диалоговое окно, нажмите кнопку **Да** , чтобы сохранить файл в проекте.  
  
6.  На странице **Сохранение подключения в файле конфигурации приложения** нажмите кнопку **Далее** .  
  
7.  Разверните узел **Таблицы** на странице **Выбор объектов базы данных** .  
  
8.  Установите флажки для таблиц **Клиенты** и **Заказы** , а затем нажмите кнопку **Готово**.  
  
     **NorthwindDataSet** добавляется в проект, и таблицы **Клиенты** и **Заказы** отображаются в окне **Источники данных** .  
  
## <a name="adding-data-bound-controls"></a>Добавление элементов управления с привязкой к данным  
 На этом шаге добавляются элементы управления с привязкой к данным <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-data-bound-controls"></a>Чтобы добавить элементы управления с привязкой к данным  
  
1.  В окне **Источники данных** выберите узел верхнего уровня для таблицы **Клиенты** .  
  
2.  Измените тип удаления таблицы на **Сведения** , выбрав **Сведения** в раскрывающемся списке в узле таблицы.  
  
3.  Выберите **клиентов** узел таблицы и перетащите его в область шаблона элемента (верхняя область) элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     A <xref:System.Windows.Forms.BindingNavigator>элемент управления добавляется на форму и **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, и **CustomersBindingNavigator** компоненты добавляются в область компонентов.</xref:System.Windows.Forms.BindingNavigator>  
  
4.  Выберите все поля и их связанные подписи и разместите их у левого края области шаблона элемента.  
  
5.  Выберите последние пять полей (**Область**, **Почтовый индекс**, **Страна**, **Телефон**и **Факс**) и их связанные подписи и поместите их вверху справа от первых шести полей.  
  
6.  Выберите шаблон элемента (верхняя область элемента управления).  
  
7.  В окне "Свойства" присвойте свойству **Размер** значение `427, 170`.  
  
 Теперь у вас есть рабочее приложение, которое будет отображать повторяющийся список клиентов. Можно нажать клавишу F5, чтобы запустить приложение, изменить данные и добавить или удалить записи клиентов.  
  
 Следующим необязательным этапом, вы узнаете, как настроить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="next-steps-optional"></a>Дальнейшие действия (необязательно)  
 Эта часть пошагового руководства состоит из четырех дополнительных задач.  
  
-   Изменение внешнего вида <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Запрет добавления или удаления записей пользователями.  
  
-   Добавление возможностей поиска в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Добавление таблицы основные и подробные <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a>Изменение внешнего вида элемента управления DataRepeater  
 На этом этапе необязательно изменять `BackColor` из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>элемента управления во время разработки.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Можно также добавить код для отображения столбцов с чередованием цвета и условного изменения `ForeColor` подписи.  
  
#### <a name="to-change-the-appearance-of-the-control"></a>Изменение внешнего вида элемента управления  
  
1.  В конструкторе Windows Forms выберите основной регион (внизу) <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  В окне "Свойства" задайте свойству `BackColor` значение "Белый".  
  
3.  Дважды щелкните файл <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, чтобы открыть редактор кода.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  В редакторе кода в раскрывающемся списке выберите **DrawItem**.  
  
5.  В <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>обработчик события добавьте следующий код для альтернативного `BackColor`:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
  
     [!code-cs[#1 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  В <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>обработчик события добавьте следующий код, чтобы изменить `ForeColor` метки в зависимости от условия:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  Нажмите клавишу F5, чтобы запустить приложение и просмотреть настройки.  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a>Запрет добавления или удаления записей пользователями  
 В это необязательный шаг, добавьте код, который запрещает пользователям добавлять или удалять записи в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a>Запрет добавления или удаления записей пользователями  
  
1.  В конструкторе Windows Forms дважды щелкните форму, чтобы открыть редактор кода.  
  
2.  Добавьте следующий код в событие `Form_Load` :  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  В раскрывающемся списке "Имя класса" выберите **BindingNavigatorDeleteItem**. В раскрывающемся списке "Имя метода" выберите **EnabledChanged**.  
  
4.  Добавьте следующий код в обработчик событий `BindingNavigatorDeleteItem_EnabledChanged` .  
  
     [!code-cs[#4 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  Этот шаг необходим, так как <xref:System.Windows.Forms.BindingSource>позволит **DeleteItem** кнопку при каждом изменении текущей записи.</xref:System.Windows.Forms.BindingSource>  
  
5.  Нажмите клавишу F5 для запуска приложения. Обратите внимание, что кнопка **DeleteItem** отключена и вы не можете удалять элементы с помощью клавиши DELETE.  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a>Добавление функции поиска в элемент управления DataRepeater  
 На этом этапе необязательно реализовать возможность поиска для значения в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> При нахождении искомой строки элемент управления выбирает элемент, содержащий значение, и прокручивает элемент в представлении.  
  
#### <a name="to-add-search-capability"></a>Добавление функции поиска  
  
1.  Перетащите <xref:System.Windows.Forms.TextBox>управления из **элементов** в форму, которая содержит <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.TextBox>  
  
     Расположите его под <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  В окне "Свойства" измените значение свойства **Имя** на **SearchTextBox**.  
  
3.  Перетащите <xref:System.Windows.Forms.Button>управления из **элементов** в форму, которая содержит <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.Button> Расположите его под <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  В окне "Свойства" измените значение свойства **Имя** на **SearchButton**. Задайте для свойства **Текст** значение **Поиск**.  
  
5.  Дважды щелкните <xref:System.Windows.Forms.Button>управления, чтобы открыть редактор кода и добавьте следующий код в `SearchButton_Click` обработчик события.</xref:System.Windows.Forms.Button>  
  
     [!code-cs[#5 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  Нажмите клавишу F5 для запуска приложения. Введите код клиента в **SearchTextBox** и нажмите кнопку **Поиск** .  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a>Добавление основной таблицы и таблицы сведений в элемент управления DataRepeater  
 На данном необязательном этапе добавляется второй <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>элемента управления для отображения связанных заказов для каждого клиента.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-master-and-detail-table"></a>Добавление основной таблицы и таблицы сведений  
  
1.  Перетащите второй <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления из **Visual Basic PowerPacks** вкладке **элементов** в форму.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  В окне "Свойства" присвойте свойству **Расположение** значение `465, 25`.  
  
3.  Установите значение свойства **Размер** равным `315, 600`.  
  
4.  В окне **Источники данных** разверните узел таблицы **Клиенты** и выберите узел сведений для таблицы **Заказы** .  
  
5.  Измените тип удаления таблицы **Заказы** на "Сведения", выбрав **Сведения** в раскрывающемся списке в узле таблицы.  
  
6.  Перетащите это **заказов** узел таблицы область шаблона элемента (верхняя область) второго <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Компоненты **OrdersBindingSource** и **OrdersTableAdapter** добавляются в область компонентов.  
  
7.  Нажмите клавишу F5 для запуска приложения. При выборе каждого клиента в первом <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления, заказы для этого клиента отображаются во втором <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Практическое руководство: отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: изменение макета элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: создание Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: отключение добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
