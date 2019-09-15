---
title: Практическое руководство. Проверка параметров приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
ms.openlocfilehash: b3b2447b570f0635942183dcc62c0e4ed73800d1
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972248"
---
# <a name="how-to-validate-application-settings"></a>Практическое руководство. Проверка параметров приложения

В этом разделе показано, как проверить параметры приложения перед их сохранением.

Поскольку параметры приложений являются строго типизированными, это дает некоторую уверенность в том, что пользователи не могут назначить тому или иному параметру данные неверного типа. Тем не менее, пользователь по-прежнему может попытаться присвоить значение вне допустимого диапазона, наприме указать дату рождения в будущем. <xref:System.Configuration.ApplicationSettingsBase>, родительский класс всех классов параметров приложения предоставляет четыре события, позволяющие проверить такие границы. Благодаря обработке этих событий весь код проверки размещается в одном месте, а не в разных частях проекта.

Используемое событие зависит от времени, когда необходимо проверить параметры, как описано в следующей таблице.

|событие|Вхождение и использование|
|-----------|------------------------|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Возникает после начальной загрузки группы свойств параметров.<br /><br /> Используйте это событие для проверки начальных значений для всей группы свойств перед их применением в приложении.|
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Происходит перед изменением значения одного свойства параметров.<br /><br /> Используйте это событие для проверки одного свойства до его изменения. Оно позволяет пользователям немедленно получить сведения о своих действиях и решениях.|
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Происходит после изменения значения одного свойства параметра.<br /><br /> Используйте это событие для проверки одного свойства после его изменения. Это событие редко используется для проверки, если не требуется длительный процесс асинхронной проверки.|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Возникает перед сохранением группы свойств параметров.<br /><br /> Используйте это событие для проверки значений для всей группы свойств перед их сохранением на диске.|

Как правило, в целях проверки все эти события внутри одного приложения не используются. Например, часто можно выполнить все требования проверки, обрабатывая только <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> событие.

Обычно при обнаружении недопустимого значения обработчик событий выполняет одно из следующих действий.

- Автоматически предоставляет заведомо правильное значение, например значение по умолчанию.

- Повторно запрашивает сведения у пользователя серверного кода.

- Для событий, вызванных до связанных действий, таких <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> как <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>и, использует <xref:System.ComponentModel.CancelEventArgs> аргумент для отмены операции.

Дополнительные сведения об обработке событий см. в разделе [Общие сведения об обработчиках событий](../event-handlers-overview-windows-forms.md).

В следующих процедурах показано, как проверить допустимость даты рождения с помощью либо <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> события, либо. В этих процедурах предполагается, что вы уже создали параметры приложения. В этом примере будет выполнена проверка границ для параметра с именем `DateOfBirth`. Дополнительные сведения о создании параметров см. в [разделе как Создание параметров](how-to-create-application-settings.md)приложения.

### <a name="to-obtain-the-application-settings-object"></a>Получение объекта параметров приложения

- Для получения ссылки на объект параметров приложения (экземпляр программы-оболочки) выполните одно из следующих действий:

  - Если вы создали параметры в диалоговом окне «Параметры приложения Visual Studio» в **редакторе свойств**, объект параметров по умолчанию, созданный для вашего языка, можно получить с помощью следующего выражения.

    ```csharp
    Configuration.Settings.Default
    ```

    ```vb
    MySettings.Default
    ```

    -или-

  - Если вы являетесь разработчиком на Visual Basic и создали параметры приложения с помощью конструктора проектов, для извлечения параметров можно использовать [объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).

    -или-

  - Если вы создали параметры, производя от <xref:System.Configuration.ApplicationSettingsBase> напрямую, необходимо создать экземпляр класса вручную.

    ```csharp
    MyCustomSettings settings = new MyCustomSettings();
    ```

    ```vb
    Dim Settings as New MyCustomSettings()
    ```

В следующих процедурах предполагается, что объект параметров приложения получен путем выполнения последнего действия в этой процедуре.

### <a name="to-validate-application-settings-when-a-setting-is-changing"></a>Проверка параметров приложения при изменении параметра

1. Если вы являетесь C# разработчиком, в форме или `Load` событии элемента управления добавьте обработчик <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> событий для события.

    -или-

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

2. Определите обработчик событий и напишите внутри него код для выполнения проверки границ для даты рождения.

    ```csharp
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)
    {
        if (e.SettingName.Equals("DateOfBirth"))
        {
            var newDate = (DateTime)e.NewValue;
            if (newDate > DateTime.Now)
            {
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

1. В форме или `Load` событии элемента управления добавьте обработчик событий <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> для события.

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

2. Определите обработчик событий и напишите внутри него код для выполнения проверки границ для даты рождения.

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

- [Создание обработчиков событий в Windows Forms](../creating-event-handlers-in-windows-forms.md)
- [Практическое руководство. Создание параметров приложения](how-to-create-application-settings.md)
