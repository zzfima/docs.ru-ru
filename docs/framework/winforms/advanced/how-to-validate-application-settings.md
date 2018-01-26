---
title: "Практическое руководство. Проверка параметров приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e12620a5079efaba4faa9101253a3a586965b7e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-application-settings"></a>Практическое руководство. Проверка параметров приложения
В этом разделе показано, как проверить параметры приложения перед их сохранением.  
  
 Поскольку параметры приложений являются строго типизированными, это дает некоторую уверенность в том, что пользователи не могут назначить тому или иному параметру данные неверного типа. Тем не менее, пользователь по-прежнему может попытаться присвоить значение вне допустимого диапазона, наприме указать дату рождения в будущем. <xref:System.Configuration.ApplicationSettingsBase>, родительским классом для всех классов параметров приложения предоставляет четыре события для поддержки проверки допустимости. Благодаря обработке этих событий весь код проверки размещается в одном месте, а не в разных частях проекта.  
  
 Используемое событие зависит от времени, когда необходимо проверить параметры, как описано в следующей таблице.  
  
|событие|Вхождение и использование|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Возникает после начальной загрузки группы свойств параметров.<br /><br /> Используйте это событие для проверки начальных значений для всей группы свойств перед их применением в приложении.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Происходит перед изменением значения одного свойства параметров.<br /><br /> Используйте это событие для проверки одного свойства до его изменения. Оно позволяет пользователям немедленно получить сведения о своих действиях и решениях.|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Происходит после изменения значения одного свойства параметра.<br /><br /> Используйте это событие для проверки одного свойства после его изменения. Это событие редко используется для проверки, если не требуется длительный процесс асинхронной проверки.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Возникает перед сохранением группы свойств параметров.<br /><br /> Используйте это событие для проверки значений для всей группы свойств перед их сохранением на диске.|  
  
 Как правило, в целях проверки все эти события внутри одного приложения не используются. Например, часто бывает невозможно выполнить все требования проверки, обрабатывая только <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> событий.  
  
 Обычно при обнаружении недопустимого значения обработчик событий выполняет одно из следующих действий.  
  
-   Автоматически предоставляет заведомо правильное значение, например значение по умолчанию.  
  
-   Повторно запрашивает сведения у пользователя серверного кода.  
  
-   Для событий, возникающих до связанных с ними действий, таких как <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> и <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, использует <xref:System.ComponentModel.CancelEventArgs> аргумент для отмены операции.  
  
 Дополнительные сведения об обработке событий см. в разделе [Общие сведения об обработчиках событий](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Следующие процедуры показывают, как проверить допустимость даты рождения с помощью <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> или <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> событий. В этих процедурах предполагается, что вы уже создали параметры приложения. В этом примере будет выполнена проверка границ для параметра с именем `DateOfBirth`. Дополнительные сведения о создании параметров см. в разделе [Практическое руководство. Создание параметров приложения](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### <a name="to-obtain-the-application-settings-object"></a>Получение объекта параметров приложения  
  
-   Для получения ссылки на объект параметров приложения (экземпляр программы-оболочки) выполните одно из следующих действий:  
  
    -   Если вы создали параметры в диалоговом окне «Параметры приложения Visual Studio» в **редакторе свойств**, объект параметров по умолчанию, созданный для вашего языка, можно получить с помощью следующего выражения.  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         - или -  
  
    -   Если вы являетесь разработчиком на Visual Basic и создали параметры приложения с помощью конструктора проектов, для извлечения параметров можно использовать [объект My.Settings](~/docs/visual-basic/language-reference/objects/my-settings-object.md).  
  
         - или -  
  
    -   Если параметры были созданы путем наследования от <xref:System.Configuration.ApplicationSettingsBase> напрямую, необходимо создать экземпляр класса вручную.  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 В следующих процедурах предполагается, что объект параметров приложения получен путем выполнения последнего действия в этой процедуре.  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a>Проверка параметров приложения при изменении параметра  
  
1.  Если разработка осуществляется на C#, в формы или элемента управления `Load` события, добавьте обработчик событий для <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> события.  
  
     - или -  
  
     Если вы являетесь разработчиком на Visual Basic, объявите переменную `Settings` с помощью ключевого слова `WithEvents`.  
  
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
  
2.  Определите обработчик событий и напишите внутри него код для выполнения проверки границ для даты рождения.  
  
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
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a>Проверка параметров приложения в ходе сохранения  
  
1.  В форме или элемента управления `Load` события, добавьте обработчик событий для <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> события.  
  
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
  
2.  Определите обработчик событий и напишите внутри него код для выполнения проверки границ для даты рождения.  
  
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
  
## <a name="see-also"></a>См. также  
 [Создание обработчиков событий в Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Практическое руководство. Создание параметров приложения](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)
