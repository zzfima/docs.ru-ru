---
title: "Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NonVisualSelection"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], невидимые"
  - "невидимые элементы управления"
  - "невидимые элементы управления"
  - "элементы управления Windows Forms, добавление в форму"
  - "элементы управления Windows Forms, невидимые"
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms
Функциональные возможности приложения обеспечиваются невидимым элементом управления \(или компонентом\).  В отличие от других элементов управления, компоненты не предоставляют интерфейс пользователя и, таким образом, не нуждаются в отображении в рабочей области конструктора Windows Forms.  При добавлении компонента в форму конструктор Windows Forms отображает область изменяемого размера внизу формы, в которой отображаются все компоненты.  После добавления элемента управления в область компонентов можно выделить компонент и задать его свойства, как для любого другого элемента управления в форме.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы добавить компонент в форму Windows Forms, выполните следующие действия.  
  
1.  Откройте форму.  Дополнительные сведения см. в разделе [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/ru-ru/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  В **панели элементов** щелкните компонент и перетащите его в форму.  
  
     Компонент появится в области компонентов.  
  
 Более того, можно также добавлять компоненты в форму во время выполнения.  Это распространенный сценарий, особенно поскольку компоненты не имеют наглядного выражения в отличие от элементов управления, имеющих пользовательский интерфейс.  В следующем примере выполняется добавление компонента <xref:System.Windows.Forms.Timer> во время выполнения.  \(Обратите внимание, что [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] содержит ряд различных таймеров; в настоящем случае используется <xref:System.Windows.Forms.Timer>, компонент Windows Forms.  Дополнительные сведения о различных таймерах в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] см. в разделе [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ru-ru/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)\).  
  
> [!CAUTION]
>  Компоненты часто обладают особыми свойствами элементов управления, которые должны быть заданы для эффективной работы компонента.  В приведенном ниже случае с компонентом <xref:System.Windows.Forms.Timer> необходимо задать свойство `Interval`.  При добавлении компонентов в проект убедитесь, что все свойства, необходимые для добавляемого компонента, заданы.  
  
#### Чтобы добавить компонент в Windows Forms программными средствами, выполните следующие действия.  
  
1.  Создайте экземпляр класса <xref:System.Windows.Forms.Timer> в коде.  
  
2.  Задайте свойство `Interval` для определения квантов времени таймера.  
  
3.  Настройте другие нужные свойства компонента.  
  
     Следующий код демонстрирует создание объекта <xref:System.Windows.Forms.Timer> и задание его свойства `Interval`.  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Ссылка на пользовательский элемент управления, созданный злонамеренным пользователем, может сделать систему безопасности локального компьютера уязвимой из сети.  Это произойдет только в том случае, если злонамеренный пользователь создаст разрушающий пользовательский элемент управления, а разработчик по ошибке добавит его в проект.  
  
## См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [Практическое руководство. Копирование элементов управления между формами Windows Forms](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)   
 [Размещение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)