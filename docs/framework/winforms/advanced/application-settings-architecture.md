---
title: Архитектура параметров приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: c3858cfab59b63761f43f6b3eaad9bf8ca4c1dbc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916698"
---
# <a name="application-settings-architecture"></a>Архитектура параметров приложения
В этом разделе описываются принципы работы архитектуры параметров приложения и рассматриваются дополнительные возможности архитектуры, такие как сгруппированные параметры и ключи параметров.

 Архитектура параметров приложений позволяет определять строго типизированные параметры с областью приложения или пользователя и сохраняет параметры в сеансах приложения. Архитектура предоставляет механизм сохраняемости по умолчанию для сохранения параметров и их загрузки из локальной файловой системы. Она также определяет интерфейсы для предоставления пользовательских механизмов сохраняемости.

 Эти интерфейсы позволяют пользовательским компонентам сохранять свои параметры, когда они размещаются в приложении. Благодаря ключам параметров компоненты могут раздельно хранить параметры для нескольких экземпляров компонента.

## <a name="defining-settings"></a>Определение параметров
 Архитектура параметров приложения используется как в ASP.NET, так и в Windows Forms и содержит ряд базовых классов, совместно используемых в обеих средах. Наиболее важным является <xref:System.Configuration.SettingsBase>, который предоставляет доступ к параметрам через коллекцию и предоставляет низкоуровневые методы для загрузки и сохранения параметров. Каждая среда реализует собственный класс, производный <xref:System.Configuration.SettingsBase> от, чтобы предоставить дополнительные параметры для этой среды. В приложении на основе Windows Forms все параметры приложения должны быть определены в классе, производном от <xref:System.Configuration.ApplicationSettingsBase> класса, который добавляет следующие функциональные возможности в базовый класс:

- Операции загрузки и сохранения более высокого уровня

- Поддержка параметров области пользователя

- Возврат для параметров пользователя предопределенных значений по умолчанию

- Обновление параметров из предыдущей версии приложения

- Проверка параметров, либо до их изменения, либо до их сохранения

 Параметры можно описать с помощью нескольких атрибутов, <xref:System.Configuration> определенных в пространстве имен. они описаны в разделе [атрибуты параметров приложения](application-settings-attributes.md). При определении параметра необходимо применить его с <xref:System.Configuration.ApplicationScopedSettingAttribute> помощью или <xref:System.Configuration.UserScopedSettingAttribute>, который описывает, применяется ли параметр ко всему приложению или только к текущему пользователю.

 В следующем примере кода определяется пользовательский класс параметров с одним параметром `BackgroundColor`.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>Сохраняемость параметров
 Сам класс не сохраняет и не загружает параметры. это задание принадлежит поставщику параметров, классу, производному от <xref:System.Configuration.SettingsProvider>. <xref:System.Configuration.ApplicationSettingsBase> Если в производном классе <xref:System.Configuration.ApplicationSettingsBase> не указан поставщик параметров <xref:System.Configuration.SettingsProviderAttribute>через, то используется поставщик <xref:System.Configuration.LocalFileSettingsProvider>по умолчанию,.

 Система конфигурации, изначально выпущенная с .NET Framework, поддерживает предоставление статических данных конфигурации приложения с помощью файла Machine. config локального компьютера или в `app.`файле exe. config, развертываемом с помощью приложение. <xref:System.Configuration.LocalFileSettingsProvider> Класс расширяет эту встроенную поддержку следующими способами.

- Параметры области приложения могут храниться в файле machine.config или `app.`exe.config. Файл machine.config всегда предназначен только для чтения, тогда как `app`.exe.config для большинства приложений рекомендуется использовать только для чтения с точки зрения безопасности.

- Параметры области пользователя могут храниться в файлах `app`.exe.config. В этом случае они обрабатываются как статические значения по умолчанию.

- Параметры области пользователя не по умолчанию хранятся в новом файле — *пользователь*.config, где *пользователь* — имя пользователя, который в данный момент выполняет приложение. Можно указать значение по умолчанию для параметра с областью действия пользователя <xref:System.Configuration.DefaultSettingValueAttribute>с помощью. Так как во время выполнения приложения параметры области пользователя часто изменяются, файл `user`.config всегда доступен для чтения и записи.

 Во всех трех файлах конфигурации параметры хранятся в формате XML. Элементом XML верхнего уровня для параметров области приложения является `<appSettings>`, а `<userSettings>` используется для параметров области пользователя. Файл `app`.exe.config, содержащий как параметры области приложения, так и значения по умолчанию для параметров области пользователя, выглядит следующим образом:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </sectionGroup>
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
        </sectionGroup>
    </configSections>
    <applicationSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="Cursor" serializeAs="String">
                <value>Default</value>
            </setting>
            <setting name="DoubleBuffering" serializeAs="String">
                <value>False</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </applicationSettings>
    <userSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="FormTitle" serializeAs="String">
                <value>Form1</value>
            </setting>
            <setting name="FormSize" serializeAs="String">
                <value>595, 536</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </userSettings>
</configuration>
```

 Определение элементов в разделе параметров приложения файла конфигурации см. в разделе [Схема параметров приложения](../../configure-apps/file-schema/application-settings-schema.md).

### <a name="settings-bindings"></a>Привязки параметров
 Параметры приложения используют архитектуру привязки данных Windows Forms для обеспечения двустороннего обмена обновлениями параметров между объектом параметров и компонентами. Если для создания параметров приложения и их назначения свойствам компонентов используется Visual Studio, эти привязки создаются автоматически.

 Параметр приложения можно привязать только к компоненту, который поддерживает <xref:System.Windows.Forms.IBindableComponent> интерфейс. Кроме того, компонент должен реализовать событие изменения для определенного привязанного свойства или уведомлять параметры приложения об изменении свойства через <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс. Если компонент не реализует <xref:System.Windows.Forms.IBindableComponent> и привязка выполняется с помощью Visual Studio, привязанные свойства будут установлены в первый раз, но не будут обновлены. Если компонент реализует <xref:System.Windows.Forms.IBindableComponent> , но не поддерживает уведомления об изменении свойств, привязка не будет обновляться в файле параметров при изменении свойства.

 Некоторые Windows Forms компоненты, такие как <xref:System.Windows.Forms.ToolStripItem>, не поддерживают привязки параметров.

### <a name="settings-serialization"></a>Сериализация параметров
 Когда <xref:System.Configuration.LocalFileSettingsProvider> параметр должен сохранять параметры на диске, он выполняет следующие действия:

1. Использует отражение для проверки всех свойств, определенных в <xref:System.Configuration.ApplicationSettingsBase> производном классе, <xref:System.Configuration.ApplicationScopedSettingAttribute> путем поиска тех, которые применяются с или <xref:System.Configuration.UserScopedSettingAttribute>.

2. Сериализует свойство на диск. Сначала он пытается вызвать метод <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> или <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> для связанного <xref:System.ComponentModel.TypeConverter>типа. Если это не удается, использует XML-сериализацию.

3. Распределяет параметры по файлам на основе атрибута параметра.

 При реализации собственного класса параметров можно использовать, <xref:System.Configuration.SettingsSerializeAsAttribute> чтобы пометить параметр для двоичной или настраиваемой сериализации <xref:System.Configuration.SettingsSerializeAs> с помощью перечисления. Дополнительные сведения о создании собственного класса параметров в коде см. в разделе [как Создание параметров](how-to-create-application-settings.md)приложения.

### <a name="settings-file-locations"></a>Расположение файлов параметров
 Расположение файлов `app`.exe.config и *user*.config зависит от способа установки приложения. Для приложения на основе Windows Forms, скопированного на локальный компьютер, `app`файл. exe. config будет находиться в том же каталоге, что и базовый каталог основного исполняемого файла приложения, а файл *User*. config будет находиться в расположении, указанном параметром <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> свойство. Для приложения, установленного с помощью ClickOnce, оба этих файла будут находиться в каталоге данных ClickOnce под%InstallRoot%\Documents и параметры\\*username*\Local Settings.

 Место хранения этих файлов будет другим, если пользователь включил перемещаемые профили, что позволит ему определять разные настройки Windows и приложения в случае использования им других компьютеров в домене. В этом случае как приложения ClickOnce, так и приложения, не относящиеся к ClickOnce `app`, будут иметь файлы. exe. config и *User*. config, хранящиеся в разделе%InstallRoot%\Documents and Settings\\*username*\Application Data.

 Дополнительные сведения о том, как параметры приложения работают с новой технологией развертывания, см. в разделе [ClickOnce и параметры приложения](/visualstudio/deployment/clickonce-and-application-settings). Дополнительные сведения о каталоге данных ClickOnce см. в разделе [доступ к локальным и удаленным данным в приложениях ClickOnce](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).

## <a name="application-settings-and-security"></a>Параметры приложения и безопасность
 Параметры приложения предназначены для работы в режиме частичного доверия, то есть в среде с ограниченным доступом, которая используется по умолчанию для приложений Windows Forms, размещенных в Интернете или интрасети. Для использования параметров приложения с поставщиком параметров по умолчанию специальные разрешения, выходящие за рамки частичного доверия, не нужны.

 Если параметры приложения используются в приложении ClickOnce, `user`файл config хранится в каталоге данных ClickOnce. Размер файла конфигурации приложения `user`не может превышать квоту каталога данных, установленную ClickOnce. Дополнительные сведения см. в разделе [ClickOnce и параметры приложения](/visualstudio/deployment/clickonce-and-application-settings).

## <a name="custom-settings-providers"></a>Поставщики пользовательских настроек
 В архитектуре параметров приложения существует слабая связь между классом-оболочкой параметров приложения, производной <xref:System.Configuration.ApplicationSettingsBase>от, а также поставщиком и поставщиками связанных параметров, <xref:System.Configuration.SettingsProvider>производными от. Эта ассоциация определяется только компонентом, <xref:System.Configuration.SettingsProviderAttribute> примененным к классу-оболочке или его отдельным свойствам. Если поставщик параметров не указан явно, используется поставщик <xref:System.Configuration.LocalFileSettingsProvider>по умолчанию. В результате такая архитектура позволяет создавать и использовать поставщиков настраиваемых параметров.

 Предположим, что требуется разработать и использовать `SqlSettingsProvider`, то есть поставщика, который будет хранить все данные параметров в базе данных Microsoft SQL Server. Класс, производный от класса, получит эти `Initialize` сведения в своем методе как <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>параметртипа. <xref:System.Configuration.SettingsProvider> Затем необходимо реализовать <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> метод для получения параметров из хранилища данных и <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> их сохранения. Поставщик может использовать переданный <xref:System.Configuration.SettingsPropertyCollection> объект для <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> определения имени свойства, типа и области, а также всех других атрибутов параметров, определенных для этого свойства.

 Вашему поставщику будет необходимо реализовать одно свойство и один метод, реализация которых может оказаться сложной. Свойство является абстрактным <xref:System.Configuration.SettingsProvider>свойством; необходимо запрограммировать его, чтобы он возвращал следующее: <xref:System.Configuration.SettingsProvider.ApplicationName%2A>

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 Ваш производный класс также должен реализовать метод `Initialize`, который не принимает аргументы и не возвращает значения. Этот метод не определен в <xref:System.Configuration.SettingsProvider>.

 Наконец, вы реализуете <xref:System.Configuration.IApplicationSettingsProvider> поставщик, чтобы обеспечить поддержку обновления параметров, возврат параметров к значениям по умолчанию и обновление параметров из одной версии приложения в другую.

 После реализации и компиляции поставщика необходимо указать, что класс параметров должен использовать этого поставщика вместо значения по умолчанию. Это можно сделать с помощью <xref:System.Configuration.SettingsProviderAttribute>. Если применяется ко всему классу параметров, поставщик используется для каждого параметра, определяемого классом. При применении к отдельным параметрам архитектура параметров приложения использует этот поставщик только для этих параметров и использует <xref:System.Configuration.LocalFileSettingsProvider> для остальных. В следующем примере кода показано, как указать классу параметров, что необходимо использовать пользовательского поставщика.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 Поставщик можно вызывать одновременно из нескольких потоков, но он всегда будет выполнять запись данных в одно место хранения. Таким образом, архитектура параметров приложения будет всегда создавать только один экземпляр класса поставщика.

> [!IMPORTANT]
> Следует убедиться, что поставщик является потокобезопасным и позволяет выполнять запись в файлы конфигурации только одному потоку за раз.

 Поставщик не обязан поддерживать все атрибуты параметров <xref:System.Configuration?displayProperty=nameWithType> , определенные в пространстве имен, хотя он должен поддерживаться как <xref:System.Configuration.ApplicationScopedSettingAttribute> минимум <xref:System.Configuration.UserScopedSettingAttribute>, а также должен поддерживать <xref:System.Configuration.DefaultSettingValueAttribute>. Для тех атрибутов, которые он не поддерживает, поставщик должен завершаться ошибкой без уведомления. Он не должен создавать исключение. Если класс параметров использует недопустимое сочетание атрибутов, например применение <xref:System.Configuration.ApplicationScopedSettingAttribute> и к одному и <xref:System.Configuration.UserScopedSettingAttribute> тому же параметру, поставщик должен вызвать исключение и прекратить операцию.

## <a name="see-also"></a>См. также

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Общие сведения о параметрах приложений](application-settings-overview.md)
- [Application Settings for Custom Controls](application-settings-for-custom-controls.md)
- [ClickOnce и параметры приложения](/visualstudio/deployment/clickonce-and-application-settings)
- [Схема параметров приложения](../../configure-apps/file-schema/application-settings-schema.md)
