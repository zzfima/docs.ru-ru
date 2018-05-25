---
title: Высокий уровень поддержки DPI в Windows Forms
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbf2d7b61b34a2cd4641a77ee1f2fcdff7f3c3fe
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
---
# <a name="high-dpi-support-in-windows-forms"></a>Высокий уровень поддержки DPI в Windows Forms

Начиная с .NET Framework 4.7, Windows Forms включает улучшения для распространенных высокое разрешение и динамических сценариев точек на ДЮЙМ. Сюда входит следующее. 

- Усовершенствования в масштабировании и макет несколько форм Windows элементы управления, такие как <xref:System.Windows.Forms.MonthCalendar> управления и <xref:System.Windows.Forms.CheckedListBox> элемента управления. 

- Один с отрицательным масштабирования.  В .NET Framework 4.6 и более ранних версий масштабирование выполнялось через несколько проходов, которые вызвала некоторые элементы управления масштабировать больше, чем необходимо.

- Поддержка динамического DPI сценариев, в которых пользователь изменяет коэффициент DPI или масштаб после запуска приложения Windows Forms.

В версиях платформы .NET Framework, начиная с .NET Framework 4.7 расширенную поддержку высоким DPI является дополнительной функции. Необходимо настроить приложение, чтобы воспользоваться преимуществами его.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Настройка приложения Windows Forms с высоким DPI поддержки

Новые возможности Windows Forms, которые поддерживают высокого уровня осведомленности DPI, доступны только в приложения, предназначенные для .NET Framework 4.7, работающих под управлением операционных систем Windows, начиная с обновления создатели Windows 10. 

Кроме того для настройки высокого уровня поддержки DPI в приложении Windows Forms, выполните следующие действия.

- Объявите совместимости с Windows 10.

  Для этого добавьте следующее в файл манифеста:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Включение точек на ДЮЙМ на мониторе, поддерживающие *app.config* файла.

  Windows Forms появилось новое [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) для поддержки новых функций и добавлены сведения о настройках, начиная с .NET Framework 4.7. Чтобы воспользоваться преимуществами новых функций, которые поддерживают высокого Разрешения, добавьте следующее в файл конфигурации приложения.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > В предыдущих версиях платформы .NET Framework вы использовали для добавления поддержки высоким DPI манифест. Такой подход не рекомендуется, так как он переопределяет параметры, определенные в файле app.config.
   
- Вызовите статический <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.
   
  Это должен быть первый вызов метода в точку входа приложения. Пример:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Отказ от отдельных функций высоким DPI

Установка `DpiAwareness` значение `PerMonitorV2` включает в себя все высокого уровня осведомленности возможности DPI, поддерживается в версиях .NET Framework, начиная с .NET Framework 4.7. Как правило этого достаточно для большинства приложений Windows Forms. Однако можно отказаться от одного или нескольких отдельных функций. Таким образом наиболее важных причина заключается в том, что существующий код приложения уже обрабатывает эту функцию.  Например если приложение обрабатывает автоматическим масштабированием, может потребоваться отключить функцию автоподбора размера следующим образом:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

Список отдельных ключей и их значений см. в разделе [добавьте элемент конфигурации Windows Forms](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Новые события изменения точек на ДЮЙМ

Начиная с .NET Framework 4.7, три новые события позволяют программным образом обрабатывать динамические изменения точек на ДЮЙМ.

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, которая возникает, когда параметр точек на ДЮЙМ для элемента управления программным способом изменяется после событие изменения DPI для его родительского элемента управления или формы произошла.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, который возникает, когда параметр DPI для элемента управления изменяется программным образом перед событие изменения DPI для родительского элемента управления или формы произошла.
- <xref:System.Windows.Forms.Form.DpiChanged>, который возникает, когда параметр DPI меняется на устройстве отображения, где в настоящее время отображается форма.

## <a name="new-helper-methods-and-properties"></a>Новые вспомогательные методы и свойства

4.7 .NET Framework также добавляет ряд новых вспомогательные методы и свойства, которые предоставляют сведения о масштабирование и позволяют выполнять масштабирование. Сюда входит следующее.

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, который преобразует значение из логического устройства.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, который масштабирует точечный рисунок логических DPI для устройства.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, который возвращает DPI для текущего устройства.

## <a name="versioning-considerations"></a>Вопросы управления версиями

Наряду с выполнением на .NET Framework 4.7 и Windows 10 создатели обновление приложения также можно запускать в среде, в которой не совместимо с высоким DPI усовершенствования. В этом случае необходимо разработать переход на резервный ресурс для приложения. Этого можно выполнить [нестандартных операций рисования](./controls/user-drawn-controls.md) для обработки масштабирования.

Чтобы сделать это, необходимо также определить операционную систему, на котором выполняется приложение. Это можно сделать с помощью следующего кода:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Обратите внимание, что приложение не будет определять успешно Windows 10, если она не была указана как поддерживаемой операционной системы в манифесте приложения.

Можно также проверить версию платформы .NET Framework, в которой было создано приложение:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>См. также

[Windows Forms добавьте элемент конфигурации](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[Настройка размера и масштаба формы Windows Forms](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
