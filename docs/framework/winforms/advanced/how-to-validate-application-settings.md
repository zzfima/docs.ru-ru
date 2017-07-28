---
title: "How to: Validate Application Settings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "validating application settings"
  - "application settings, Windows Forms"
  - "application settings, validating"
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# How to: Validate Application Settings
В этом разделе показано, как проверить параметры приложения перед их сохранением.  
  
 Поскольку параметры приложений являются строго типизированными, имеется некоторая уверенность, что пользователи не смогут назначить тому или иному параметру данные неверного типа.  Однако пользователь по\-прежнему может пытаться присвоить параметру значение, которое находится вне допустимых границ, — например, задать дату рождения, которая произойдет в будущем.  Родительский класс всех классов параметров приложений, <xref:System.Configuration.ApplicationSettingsBase>, предоставляет четыре события для поддержки проверки допустимости данных.  Обработка этих событий помещает весь код проверки в одном месте, а не разбрасывает его по всему проекту.  
  
 Используемое событие зависит от момента проверки параметров, как описано в следующей таблице.  
  
|Событие|Возникновение и использование|  
|-------------|-----------------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Возникает после начальной загрузки группы свойств параметров.<br /><br /> Используйте это событие для проверки начальных значений для всей группы свойств, прежде чем они будут использованы в приложении.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Возникает перед изменением значения одного свойства параметра.<br /><br /> Используйте это событие для проверки одного свойства до его изменения.  Это позволяет предоставить немедленный отклик пользователям относительно их действий и решений.|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Возникает после изменения значения одного свойства параметра.<br /><br /> Используйте это событие для проверки одного свойства после его изменения.  Это событие редко используется для проверки кроме случаев, когда требуется продолжительный процесс асинхронной проверки.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Возникает перед сохранением группы свойств параметров.<br /><br /> Используйте это событие для проверки значений для всей группы свойств, прежде чем они сохранятся на диске.|  
  
 Как правило, не требуется использовать все эти события для целей проверки в одном приложении.  Например, часто удается выполнить все требования проверки, обрабатывая только событие <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>.  
  
 Обычно при обнаружении недопустимого значения обработчик событий выполняет одно из следующих действий.  
  
-   Автоматически предоставляет значение, которое заведомо правильно, например значение по умолчанию.  
  
-   Повторно запрашивает сведения у пользователя серверного кода.  
  
-   Для событий, возникающих до связанных с ними действий, таких как <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> и <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, аргумент <xref:System.ComponentModel.CancelEventArgs> используется для отмены операции.  
  
 Дополнительные сведения об обработке событий см. в разделе [Event Handlers Overview](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Следующие процедуры показывают, как проверить допустимость даты рождения с помощью события <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> или <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>.  Процедуры были написаны в предположении, что параметры приложения уже созданы; в этом примере будет выполнена проверка границ для параметра с именем  `DateOfBirth`.  Дополнительные сведения о создании параметров см. в разделе [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### Для получения объекта параметров приложения выполните следующие действия.  
  
-   Получите ссылку на объект параметров приложения \(экземпляр класса\-оболочки\), выполнив один из следующих пунктов маркированного списка.  
  
    -   Если параметры были созданы с помощью диалогового окна "Параметры приложения" Visual Studio в **редакторе свойств**, можно получить объект параметров по умолчанию, созданный для текущего языка с помощью следующего выражения.  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         \-или\-  
  
    -   Разработчики на языке Visual Basic, создающие параметры приложения с помощью конструктора проектов, могут извлечь параметры настройки с помощью объекта [Объект My.Settings](../../../../ocs/visual-basic/language-reference/objects/my-settings-object.md).  
  
         \-или\-  
  
    -   Если параметры были созданы путем непосредственного наследования от класса <xref:System.Configuration.ApplicationSettingsBase>, необходимо создать экземпляр класса вручную.  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 Следующие процедуры были написаны в предположении, что объект параметров приложения был получен путем выполнения последнего пункта приведенного выше маркированного списка.  
  
### Чтобы проверить параметры приложения во время изменения параметра, выполните следующие действия.  
  
1.  Если разработка осуществляется на C\#, в событии `Load` формы или элемента управления добавьте обработчик событий для события <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>.  
  
     \-или\-  
  
     Если разработка осуществляется на Visual Basic, следует объявить переменную `Settings` с помощью зарезервированного слова `WithEvents`.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(sender as Object, e as EventArgs)  
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging  
    End Sub   
    ```  
  
2.  Определите обработчик событий и напишите внутри него код для выполнения проверки границ даты рождения.  
  
    ```csharp  
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)  
    {  
        if (e.SettingName.Equals("DateOfBirth")) {  
            Date newDate = (Date)e.NewValue;  
            If (newDate > Date.Now) {  
                e.Cancel = true;  
                // Inform the user.  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging  
        If (e.SettingName.Equals("DateOfBirth")) Then  
            Dim NewDate as Date = CType(e.NewValue, Date)  
            If (NewDate > Date.Now) Then  
                e.Cancel = True  
                ' Inform the user.  
            End If  
        End If  
    End Sub  
    ```  
  
### Чтобы проверить параметры приложения во время сохранения, выполните следующие действия.  
  
1.  В событии `Load` формы или элемента управления добавьте обработчик событий для события <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(Sender as Object, e as EventArgs)  
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving  
    End Sub  
    ```  
  
2.  Определите обработчик событий и напишите внутри него код для выполнения проверки границ даты рождения.  
  
    ```csharp  
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)  
    {  
        if (this["DateOfBirth"] > Date.Now) {  
            e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)  
        If (Me["DateOfBirth"] > Date.Now) Then  
            e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## См. также  
 [Creating Event Handlers in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)