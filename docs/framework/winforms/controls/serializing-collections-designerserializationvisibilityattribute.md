---
title: Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: a502ecc30911f2296bf48eaa195f5b6452b7588a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541302"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute
Пользовательские элементы управления, иногда будет предоставлять коллекции как свойство. В этом пошаговом руководстве демонстрируется использование <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> класса для управления способом сериализации коллекции во время разработки. Применение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> значение к свойству коллекции гарантирует, что будет сериализовано свойство.  
  
 Скопируйте код из этой темы, в разделе [как: сериализации коллекций из стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, где установлена среда Visual Studio.  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>Создание элемента управления с сериализуемой коллекцией  
 Первым шагом является создание элемента управления с сериализуемой коллекцией как свойство. Можно изменить содержимое этой коллекции с помощью **редактор коллекции**, к которому можно получить из **свойства** окна.  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>Создание элемента управления с сериализуемой коллекцией  
  
1.  Создайте проект библиотеки элементов управления Windows с именем `SerializationDemoControlLib`. Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Переименуйте `UserControl1` для `SerializationDemoControl`. Дополнительные сведения см. в разделе [как: переименовать идентификаторы](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  В **свойства** задайте значение <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> свойства `10`.  
  
4.  Место <xref:System.Windows.Forms.TextBox> управления `SerializationDemoControl`.  
  
5.  Выберите элемент управления <xref:System.Windows.Forms.TextBox>. В **свойства** задайте следующие свойства.  
  
    |Свойство.|Измените на|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**Закрепление**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**Полосы прокрутки**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6.  В **редактор кода**, объявите поле строкового массива с именем `stringsValue` в `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Определение `Strings` свойство `SerializationDemoControl`.  
  
> [!NOTE]
>  <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Значение используется для включения сериализации коллекции.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Нажмите клавишу F5, чтобы собрать проект и запустить элемент управления в **тестовом контейнере элементов управления**.  
  
2.  Найти `Strings` свойство в <xref:System.Windows.Forms.PropertyGrid> из **тестовый контейнер пользовательских элементов управления**. Нажмите кнопку `Strings` свойства, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.  
  
3.  Введите несколько строк в **редактор коллекции строк**. Разделите их, нажав клавишу ВВОД в конце каждой строки. Нажмите кнопку **ОК** завершении ввода строки.  
  
> [!NOTE]
>  Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.  
  
## <a name="serializing-a-collection-property"></a>Сериализация свойства коллекции  
 Для проверки сериализации элемента управления, будет разместить его в форме и изменить содержимое коллекции с **редактор коллекции**. Вы увидите состояния сериализации, просмотрев служит файл конструктора, в который **конструктор Windows Forms** выдает код.  
  
#### <a name="to-serialize-a-collection"></a>Для сериализации коллекции  
  
1.  Добавьте в решение проект приложения Windows. Задайте для проекта имя `SerializationDemoControlTest`.  
  
2.  В **элементов**, найти вкладка с именем **SerializationDemoControlLib компонентов**. На этой вкладке вы найдете `SerializationDemoControl`. Дополнительные сведения см. в разделе [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Место `SerializationDemoControl` в форме.  
  
4.  Найти `Strings` свойство в **свойства** окна. Нажмите кнопку `Strings` свойства, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.  
  
5.  Введите несколько строк в **редактор коллекции строк**. Разделите их, нажав клавишу ВВОД в конце каждой строки. Нажмите кнопку **ОК** завершении ввода строки.  
  
> [!NOTE]
>  Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.  
  
1.  В **обозревателе решений** нажмите кнопку **Показать все файлы**.  
  
2.  Откройте **Form1** узла. Ниже это файл с именем **Form1.Designer.cs** или **Form1.Designer.vb**. Это файл, в который **конструктор Windows Forms** выдает код, представляющий состояние вашей формы и ее дочерних элементов управления во время разработки. Откройте этот файл в **редакторе кода**.  
  
3.  Откройте область, называемую **код, автоматически созданный конструктором форм Windows** и найдите раздел **serializationDemoControl1**. Под этой надписью находится код, представляющий сериализованное состояние элемента управления. Строки, введенного в шаге 5, отображаются в назначении `Strings` свойство. В следующих примерах кода в C# и Visual Basic, Показать код, аналогичный тому, что будет при вводе строки «red», «оранжевый» и «желтый».  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  В **редактор кода**, измените значение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> на `Strings` свойства <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. Пересоберите решение и повторите шаги 3 и 4.  
  
> [!NOTE]
>  В этом случае **конструктор Windows Forms** не выдает назначения `Strings` свойство.  
  
## <a name="next-steps"></a>Следующие шаги  
 Если известно, как выполнять сериализацию коллекции стандартных типов, рассмотрите возможность более глубокий уровень интеграции пользовательских элементов управления в среду разработки. Следующие разделы описывают для улучшения интеграции пользовательских элементов управления во время разработки.  
  
-   [Архитектура времени разработки](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [Атрибуты в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Общие сведения о сериализации конструктора](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [Общие сведения о сериализации конструктора](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [Как: сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
