---
title: "Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute | Microsoft Docs"
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
  - "коллекции, сериализация"
  - "коллекции, стандартные типы"
  - "DesiginerSerializationVisibilityAttribute - класс"
  - "сериализация, коллекции"
  - "стандартные типы, коллекции"
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute
Иногда пользовательские элементы управления используют в качестве свойства коллекцию.  Данное пошаговое руководство демонстрирует использование класса <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> для управления сериализацией коллекции во время проектирования.  Применение значения <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> к свойству коллекции обеспечит его сериализацию.  
  
 Чтобы скопировать весь текст кода из этой темы, см. ссылку [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена Visual Studio.  
  
## Создание элемента управления с сериализуемой коллекцией  
 Сначала нужно создать элемент управления с с сериализуемой коллекцией в качестве свойства.  Изменить содержимое этой коллекции можно с помощью **редактора коллекций**, который доступен в окне **Свойства**.  
  
#### Для создания элемента управления с сериализуемой коллекцией выполните следующие действия.  
  
1.  Создайте новый проект "Библиотека элементов управления Windows" под названием `SerializationDemoControlLib`.  Дополнительные сведения см. в разделе [Windows Control Library Template](http://msdn.microsoft.com/ru-ru/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Переименуйте `UserControl1` в `SerializationDemoControl`.  Дополнительные сведения см. в разделе [How to: Rename Identifiers](http://msdn.microsoft.com/ru-ru/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.Padding.All%2A?displayProperty=fullName> значение `10`.  
  
4.  Поместите элемент управления <xref:System.Windows.Forms.TextBox> в `SerializationDemoControl`.  
  
5.  Выберите элемент управления <xref:System.Windows.Forms.TextBox>.  В окне **Свойства** задайте следующие значения свойств.  
  
    |Свойство.|Значение|  
    |---------------|--------------|  
    |**Multiline**|`true`|  
    |**Dock**|<xref:System.Windows.Forms.DockStyle>|  
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars>|  
    |**ReadOnly**|`true`|  
  
6.  В **редакторе кода** объявите поле строкового массива с именем `stringsValue` в `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Определите свойство `Strings` в `SerializationDemoControl`.  
  
> [!NOTE]
>  Значение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> используется для включения сериализации коллекции.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Нажмите клавишу F5 для построения проекта и запустите элемент управления в **Тестовом контейнере пользовательских элементов управления**.  
  
2.  Найдите свойство `Strings` в объекте <xref:System.Windows.Forms.PropertyGrid> **тестового контейнера элементов управления**.  Щелкните свойство `Strings`, затем нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), чтобы открыть **редактор коллекции строк**.  
  
3.  Введите несколько строк в **редакторе набора строк**.  Для разделения строк нажмите клавишу ВВОД в конце каждой строки.  По завершении нажмите кнопку **ОК**.  
  
> [!NOTE]
>  Введенные строки отображаются в поле <xref:System.Windows.Forms.TextBox> элемента управления `SerializationDemoControl`.  
  
## Сериализация свойства коллекции  
 Для проверки сериализации элемента управления его можно поместить в форму и изменить содержимое коллекции с помощью **редактора коллекций**.  Для проверки состояния сериализации служит файл конструктора, в который **Конструктор Windows Forms Designer** выдает код.  
  
#### Для сериализации коллекции выполните следующие действия.  
  
1.  В решение добавьте новый проект приложения Windows.  Назовите проект `SerializationDemoControlTest`.  
  
2.  В **панели элементов** перейдите на новую вкладку под названием **SerializationDemoControlLib Components**.  На этой вкладке будет находиться `SerializationDemoControl`.  Дополнительные сведения см. в разделе [Пример. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Поместите `SerializationDemoControl` в форму.  
  
4.  Найдите свойство `Strings` в окне **Свойства**.  Щелкните свойство `Strings`, затем нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), чтобы открыть **редактор коллекции строк**.  
  
5.  Введите несколько строк в **редакторе коллекции строк**.  Для разделения строк нажмите клавишу ВВОД в конце каждой строки.  По завершении нажмите кнопку **ОК**.  
  
> [!NOTE]
>  Введенные строки отображаются в поле <xref:System.Windows.Forms.TextBox> элемента управления `SerializationDemoControl`.  
  
1.  В **обозревателе решений** нажмите кнопку **Показать все файлы**.  
  
2.  Откройте узел **Form1**.  Под ним находится файл **Form1.Designer.cs** или **Form1.Designer.vb**.  Это файл, в который **Конструктор Windows Forms** выдает код, представляющий состояние вашей формы и ее элементов управления на этапе разработки.  Откройте этот файл в **Редакторе кода**.  
  
3.  Откройте фрагмент файла под названием **Windows Form Designer generated code** и найдите там раздел **serializationDemoControl1**.  Под этой надписью находится код, представляющий состояние сериализации вашего элемента управления.  Введенные на шаге 5 строки отображаются назначении свойства `Strings`.  В следующем примере показан код, который вы увидели бы при вводе строк "red", "orange" и "yellow".  
  
4.  \[Visual Basic\]  
  
    ```  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```  
  
5.  \[C\#\]  
  
    ```  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
  
6.  В **редакторе кода** измените значение атрибута <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> в свойстве `Strings` на <xref:System.ComponentModel.DesignerSerializationVisibility>.  
  
7.  \[Visual Basic\]  
  
    ```  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
8.  \[C\#\]  
  
    ```  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
  
9. Пересоберите решение и повторите шаги с 4 по 8.  
  
> [!NOTE]
>  В этом случае **Конструктор Windows Forms** не выдает назначения свойству `Strings`.  
  
## Следующие действия  
 Ознакомившись с сериализацией коллекции стандартных типов, попробуйте более глубоко интегрировать ваши собственные элементы управления в среду на этапе разработки.  В следующих разделах описывается расширение интеграции пользовательских элементов управления на этапе разработки.  
  
-   [Design\-Time Architecture](../Topic/Design-Time%20Architecture.md)  
  
-   [Атрибуты в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)  
  
-   [Пошаговое руководство: Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## См. также  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>   
 [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)   
 [Пример. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)