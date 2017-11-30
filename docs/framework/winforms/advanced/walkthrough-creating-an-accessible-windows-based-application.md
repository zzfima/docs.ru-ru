---
title: "Пошаговое руководство. Создание Windows-приложения с поддержкой специальных возможностей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5b52f9f06e2a4adf401367e337be81684f661e1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a>Пошаговое руководство. Создание Windows-приложения с поддержкой специальных возможностей
Создание приложений со специальными возможностями необходимо по деловым соображениям. Во многих странах для продаваемого программного обеспечения существуют правительственные требования в отношении специальных возможностей. Логотип "Сертифицировано для Windows" предполагает соответствие продукта требованиям в отношении специальных возможностей. По предварительным оценкам, только в США 30 миллионов пользователей нуждаются в программном обеспечении со специальными возможностями. Многие из них являются потенциальными клиентами.  
  
 В этом пошаговом руководстве рассматриваются пять требований в отношении специальных возможностей, выполнение которых необходимо для использования эмблемы "Сертифицировано для Windows". Согласно этим требованиям в приложении со специальными возможностями обеспечиваются:  
  
-   поддержка настройки размера, цвета, шрифта и параметров ввода с панели управления; изменение размеров строк меню, строк заголовков, границ и строки состояния при изменении соответствующих параметров на панели управления (дополнительные изменения элементов управления или кода в приложении не требуются);  
  
-   поддержка режима высокой контрастности;  
  
-   документированный доступ с клавиатуры ко всем возможностям;  
  
-   наглядное и программное представление фокуса клавиатуры;  
  
-   предоставление важной информации не только с помощью звукового сигнала.  
  
 Подробнее см. в разделе [Ресурсы для создания приложений со специальными возможностями](/visualstudio/ide/reference/resources-for-designing-accessible-applications).  
  
 Информацию о поддержке различных раскладок клавиатуры см. в разделе [Рекомендации по разработке международных приложений](../../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).  
  
## <a name="creating-the-project"></a>Создание проекта  
 В этом пошаговом руководстве создается пользовательский интерфейс для приложения, принимающего заказы на пиццу. Оно содержит поле (<xref:System.Windows.Forms.TextBox>) для имени заказчика, группу переключателей (<xref:System.Windows.Forms.RadioButton>) для выбора размера пиццы, флажки (<xref:System.Windows.Forms.CheckedListBox>) для выбора начинки, две кнопки с надписями "Заказать" и "Отмена", а также меню с командой "Выход".  
  
 Пользователь вводит имя заказчика, размер пиццы и выбранную начинку. Когда пользователь нажимает кнопку "Заказать", сводка заказа и его цена выводятся в окне сообщения, а элементы управления очищаются и становятся готовыми к приему следующего заказа. Когда пользователь нажимает кнопку "Отмена", элементы управления очищаются и становятся готовыми к приему следующего заказа. Когда пользователь выбирает в меню команду "Выход", программа закрывается.  
  
 Основное внимание в этом пошаговом руководстве уделяется не коду для системы розничной продажи, а специальным возможностям пользовательского интерфейса. В примере демонстрируются специальные возможности для некоторых часто используемых элементов управления, таких как кнопки, переключатели, поля и метки.  
  
#### <a name="to-begin-making-the-application"></a>Начало разработки приложения  
  
-   Создайте приложение Windows в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]. Назовите проект **PizzaOrder**. (Подробнее см. в разделе [Создание решений и проектов](/visualstudio/ide/creating-solutions-and-projects).)  
  
## <a name="adding-the-controls-to-the-form"></a>Добавление элементов управления в форму  
 При добавлении элементов управления в форму придерживайтесь приведенных ниже правил для того, чтобы приложение было доступным для пользователей с физическими ограничениями.  
  
-   Задайте свойства <xref:System.Windows.Forms.Control.AccessibleDescription%2A> и <xref:System.Windows.Forms.Control.AccessibleName%2A>. В этом примере для свойства <xref:System.Windows.Forms.Control.AccessibleRole%2A> достаточным является значение Default. Подробнее о свойствах специальных возможностей см. в разделе [Определение сведений, связанных со специальными возможностями, для элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form.md).  
  
-   Задайте размер шрифта 10 пунктов или выше.  
  
    > [!NOTE]
    >  Если задать для формы размер шрифта 10 в начале работы, то все элементы управления, добавляемые в форму после этого, также будут иметь размер шрифта 10.  
  
-   Убедитесь в том, что любой элемент управления Label, относящийся к элементу TextBox, непосредственно предшествует элементу TextBox в последовательности табуляции.  
  
-   С помощью символа & добавьте клавишу доступа в значение свойства <xref:System.Windows.Forms.Control.Text%2A> любого элемента управления, к которому пользователю может потребоваться перейти.  
  
-   С помощью символа & добавьте клавишу доступа в значение свойства <xref:System.Windows.Forms.Control.Text%2A> метки, находящейся перед элементом управления, к которому пользователю может потребоваться перейти. Задайте для свойства <xref:System.Windows.Forms.Label.UseMnemonic%2A> метки значение `true`, чтобы при нажатии клавиши доступа фокус переводился на следующий элемент управления в последовательности табуляции.  
  
-   Добавьте клавиши доступа для всех элементов меню.  
  
#### <a name="to-make-your-windows-application-accessible"></a>Обеспечение специальных возможностей приложения Windows  
  
-   Добавьте в форму элементы управления и задайте их свойства, как описано ниже. Модель размещения элементов управления в форме см. на рисунке после таблицы.  
  
    |Объект|Свойство.|Значение|  
    |------------|--------------|-----------|  
    |Form1|AccessibleDescription|Форма заказа|  
    ||AccessibleName|Форма заказа|  
    ||Размер шрифта|10|  
    ||Text|Форма заказа пиццы|  
    |PictureBox|Имя|logo|  
    ||AccessibleDescription|Порция пиццы|  
    ||AccessibleName|Логотип компании|  
    ||Изображение|Любой значок или растровое изображение|  
    |Метка|Имя|companyLabel|  
    ||Text|Вкусная пицца|  
    ||TabIndex|1|  
    ||AccessibleDescription|Название компании|  
    ||AccessibleName|Название компании|  
    ||Backcolor|Синий|  
    ||Forecolor|Желтый|  
    ||Font size|18|  
    |Метка|Имя|customerLabel|  
    ||Text|&Имя|  
    ||TabIndex|2|  
    ||AccessibleDescription|Подпись имени заказчика|  
    ||AccessibleName|Подпись имени заказчика|  
    ||UseMnemonic|True|  
    |TextBox|Имя|customerName|  
    ||Text|(нет)|  
    ||TabIndex|3|  
    ||AccessibleDescription|Имя заказчика|  
    ||AccessibleName|Имя заказчика|  
    |GroupBox|Имя|sizeOptions|  
    ||AccessibleDescription|Размеры порции пиццы|  
    ||AccessibleName|Размеры порции пиццы|  
    ||Text|Размер пиццы|  
    ||TabIndex|4|  
    |RadioButton|Имя|smallPizza|  
    ||Text|&Маленькая 300 р.|  
    ||Установлен|True|  
    ||TabIndex|0|  
    ||AccessibleDescription|Маленькая пицца|  
    ||AccessibleName|Маленькая пицца|  
    |RadioButton|Имя|largePizza|  
    ||Text|&Большая 500 р.|  
    ||TabIndex|1|  
    ||AccessibleDescription|Большая пицца|  
    ||AccessibleName|Большая пицца|  
    |Метка|Имя|toppingsLabel|  
    ||Text|&Начинки (40 р. за каждую)|  
    ||TabIndex|5|  
    ||AccessibleDescription|Метка начинки|  
    ||AccessibleName|Метка начинки|  
    ||UseMnemonic|True|  
    |CheckedListBox|Имя|toppings|  
    ||TabIndex|6|  
    ||AccessibleDescription|Выбор начинок|  
    ||AccessibleName|Выбор начинок|  
    ||Элементы|Пепперони, колбаса, грибы|  
    |Кнопка|Имя|порядок|  
    ||Text|&Порядок|  
    ||TabIndex|7|  
    ||AccessibleDescription|Сумма заказа|  
    ||AccessibleName|Сумма заказа|  
    |Кнопка|Имя|cancel|  
    ||Text|О&тмена|  
    ||TabIndex|8|  
    ||AccessibleDescription|Отмена заказа|  
    ||AccessibleName|Отмена заказа|  
    |MainMenu|Имя|theMainMenu|  
    |MenuItem|Имя|fileCommands|  
    ||Text|&Файл|  
    |MenuItem|Имя|exitApp|  
    ||Text|Вы&ход|  
  
     ![Форма заказа пиццы](../../../../docs/framework/winforms/advanced/media/vbpizzaorderform.gif "vbPizzaOrderForm")  
Форма будет иметь вид, аналогичный представленному ниже.  
  
## <a name="supporting-high-contrast-mode"></a>Поддержка режима высокой контрастности  
 Режим высокой контрастности представляет собой тип системной настройки Windows, при которой удобство чтения текста повышается за счет более контрастных цветов и размеров шрифта, подходящих для пользователей с нарушениями зрения. <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> Свойство позволяет определить, установлен ли режим высокой контрастности.  
  
 Если свойство SystemInformation.HighContrast имеет значение `true`, то в приложении происходит следующее:  
  
-   Все элементы пользовательского интерфейса отображаются с использованием системной цветовой схемы.  
  
-   Любая информация, передающаяся цветом, также передается с помощью визуальных или звуковых сигналов. Например, если определенный элемент списка выделен красным шрифтом, можно также отобразить его полужирным шрифтом, чтобы пользователь, не различающий цвета, видел, что элемент выделен.  
  
-   Опускаются все рисунки или узоры за текстом.  
  
 Приложение должно проверять значение свойства <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> при запуске и отвечать на системное событие <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>. При изменении значения свойства <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> происходит событие <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.  
  
 В этом примере единственным элементом, не использующим системные параметры цвета, является `lblCompanyName`. <xref:System.Drawing.SystemColors> Класс используется для замены параметров цвета метки на выбранные пользователем системные цвета.  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a>Эффективный способ обеспечения высокой контрастности  
  
1.  Создайте метод, задающий для метки системные цвета.  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2.  Вызовите процедуру `SetColorScheme` в конструкторе форм (`Public Sub New()` в Visual Basic; `public class Form1` в Visual C#). Чтобы получить доступ к конструктору в Visual Basic, необходимо развернуть область с меткой **Код, автоматически созданный конструктором форм Windows**.  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3.  Создайте процедуру обработки события с соответствующей подписью для реагирования на событие <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4.  Добавьте код в конструктор форм после вызова метода `InitializeComponents`, чтобы подключить процедуру обработки событий к системному событию. Этот метод вызывает процедуру `SetColorScheme`.  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5.  Добавьте код в метод <xref:System.Windows.Forms.Control.Dispose%2A> формы перед вызовом метода <xref:System.Windows.Forms.Control.Dispose%2A> базового класса, чтобы освободить событие при закрытии приложения. Чтобы получить доступ к методу <xref:System.Windows.Forms.Control.Dispose%2A> в Visual Basic, необходимо развернуть область "Код, автоматически созданный конструктором форм Windows".  
  
    > [!NOTE]
    >  Код системного события выполняется в потоке, отдельном от основного приложения. Если не освободить событие, то код, связанный с событием, будет выполняться даже после закрытия программы.  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6.  Нажмите клавишу F5 для запуска приложения.  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a>Передача важной информации способами помимо звукового сигнала  
 В этом приложении никакая информация не предоставляется только с помощью звукового сигнала. Если вы используете звук в своем приложении, следует также предусмотреть альтернативные способы передачи информации.  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a>Обеспечение передачи важной информации способами помимо звукового сигнала  
  
1.  Сделайте строку заголовка мигающей с помощью функции FlashWindow интерфейса Windows API. Пример вызова функций Windows API см. в разделе [Пошаговое руководство. Вызов API Windows](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
    > [!NOTE]
    >  У пользователя может быть включена служба визуального оповещения Windows, что также приведет к миганию окна при подаче системных звуковых сигналов через встроенные динамики компьютера.  
  
2.  Выводите важную информацию в немодальном окне, чтобы пользователь мог реагировать на нее.  
  
3.  При выводе окна сообщения передавайте ему фокус клавиатуры. Этот способ не следует применять в момент, когда пользователь может осуществлять ввод с клавиатуры.  
  
4.  Выводите индикатор состояния в области уведомлений о состоянии панели задач. Подробнее см. в разделе [Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Перед развертыванием приложения необходимо протестировать реализованные специальные возможности.  
  
#### <a name="to-test-accessibility-features"></a>Тестирование специальных возможностей  
  
1.  Для проверки доступа с клавиатуры отключите мышь и перейдите к каждому элемента пользовательского интерфейса, используя только клавиатуру. Убедитесь в том, что все задачи можно выполнить с помощью клавиатуры.  
  
2.  Для проверки режима высокой контрастности используйте компонент "Специальные возможности" на панели управления. Выберите вкладку "Экран" и установите флажок "Высокая контрастность". Перейдите по всем элементам управления и убедитесь в том, что отражаются изменения цвета и шрифта. Кроме того, убедитесь в том, что отсутствуют рисунки или узоры под текстом.  
  
    > [!NOTE]
    >  В Windows NT 4 значок "Специальные возможности" на панели управления отсутствует. Поэтому этот способ изменения значения свойства SystemInformation.HighContrast не работает в Windows NT 4.  
  
3.  Доступны также другие средства тестирования специальных возможностей приложения.  
  
4.  Для тестирования демонстрации фокуса клавиатуры запустите экранную лупу. (Для этого нажмите кнопку **Пуск**, выберите **Программы**, **Стандартные**, **Специальные возможности**, а затем щелкните **Экранная лупа**.) Выполните переходы по интерфейсу пользователя, используя клавишу TAB и мышь. Убедитесь в том, что все переходы правильно отображаются **экранной лупой**.  
  
5.  Для проверки отображения элементов экрана запустите программу Inspect и перейдите к каждому элементу с помощью мыши и клавиши TAB. Убедитесь в том, что сведения, выводящиеся в полях "Name", "State", "Role", "Location" и "Value" окна программы Inspect для каждого объекта в интерфейсе являются полезными для пользователя.
