---
title: Архитектура параметров приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 078b5f3fc1cd4273af282580f41e68ca9bd8ff51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182627"
---
# <a name="application-settings-architecture"></a>Архитектура параметров приложения
В этом разделе описываются принципы работы архитектуры параметров приложения и рассматриваются дополнительные возможности архитектуры, такие как сгруппированные параметры и ключи параметров.

 Архитектура параметров приложений позволяет определять строго типизированные параметры с областью приложения или пользователя и сохраняет параметры в сеансах приложения. Архитектура предоставляет механизм сохраняемости по умолчанию для сохранения параметров и их загрузки из локальной файловой системы. Она также определяет интерфейсы для предоставления пользовательских механизмов сохраняемости.

 Эти интерфейсы позволяют пользовательским компонентам сохранять свои параметры, когда они размещаются в приложении. Благодаря ключам параметров компоненты могут раздельно хранить параметры для нескольких экземпляров компонента.

## <a name="defining-settings"></a>Определение параметров
 Архитектура настроек приложения используется как в ASP.NET, так и в windows Forms и содержит ряд базовых классов, которые являются общими для обеих сред. Наиболее <xref:System.Configuration.SettingsBase>важным является , который обеспечивает доступ к настройкам через коллекцию, и обеспечивает низкоуровневые методы для загрузки и сохранения настроек. Каждая среда реализует свой собственный класс, полученный из, <xref:System.Configuration.SettingsBase> чтобы обеспечить дополнительные функциональные возможности настроек для этой среды. В приложении, основанном на Windows Forms, все настройки приложения <xref:System.Configuration.ApplicationSettingsBase> должны быть определены на классе, полученном из класса, который добавляет следующую функциональность к базовому классу:

- Операции загрузки и сохранения более высокого уровня

- Поддержка параметров области пользователя

- Возврат для параметров пользователя предопределенных значений по умолчанию

- Обновление параметров из предыдущей версии приложения

- Проверка параметров, либо до их изменения, либо до их сохранения

 Настройки можно описать с помощью ряда <xref:System.Configuration> атрибутов, определенных в пространстве имен; они описаны в [атрибутах атрибутов настройки приложений.](application-settings-attributes.md) При определении параметра необходимо применить <xref:System.Configuration.ApplicationScopedSettingAttribute> ее <xref:System.Configuration.UserScopedSettingAttribute>с помощью любого или с помощью такого параметра, который описывает, применяется ли параметр ко всему приложению или только к текущему пользователю.

 В следующем примере кода определяется пользовательский класс параметров с одним параметром `BackgroundColor`.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>Сохраняемость параметров
 Класс <xref:System.Configuration.ApplicationSettingsBase> сам по себе не сохраняется и не загружает настройки; эта работа относится к поставщику параметров, <xref:System.Configuration.SettingsProvider>класс, который вытекает из . Если производный <xref:System.Configuration.ApplicationSettingsBase> класс не указывает поставщика <xref:System.Configuration.SettingsProviderAttribute>настроек через, <xref:System.Configuration.LocalFileSettingsProvider>то используется поставщик по умолчанию.

 Система конфигурации, которая была первоначально выпущена с помощью .NET Framework, поддерживает предоставление статических `app.`данных конфигурации приложения либо через файл машины локального компьютера,config, либо в файлexex exe.config, который развертывается с помощью приложения. Класс <xref:System.Configuration.LocalFileSettingsProvider> расширяет эту родную поддержку следующим образом:

- Параметры области приложения могут храниться в файле machine.config или `app.`exe.config. Файл machine.config всегда предназначен только для чтения, тогда как `app`.exe.config для большинства приложений рекомендуется использовать только для чтения с точки зрения безопасности.

- Параметры области пользователя могут храниться в файлах `app`.exe.config. В этом случае они обрабатываются как статические значения по умолчанию.

- Параметры области пользователя не по умолчанию хранятся в новом файле — *пользователь*.config, где *пользователь* — имя пользователя, который в данный момент выполняет приложение. Можно указать значение по умолчанию для <xref:System.Configuration.DefaultSettingValueAttribute>настройки, с помощью которых пользователь сразилась с . Так как во время выполнения приложения параметры области пользователя часто изменяются, файл `user`.config всегда доступен для чтения и записи.

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

 Настройка приложения может быть привитана только к компоненту, поддерживающему <xref:System.Windows.Forms.IBindableComponent> интерфейс. Кроме того, компонент должен реализовать событие изменения для определенного связанного свойства или <xref:System.ComponentModel.INotifyPropertyChanged> уведомить настройки приложения, которые свойство изменило через интерфейс. Если компонент не <xref:System.Windows.Forms.IBindableComponent> реализуется и вы привязываетесь через Visual Studio, связанные свойства будут установлены с первого раза, но не будут обновляться. Если компонент реализует, <xref:System.Windows.Forms.IBindableComponent> но не поддерживает уведомления об изменении свойств, привязка не будет обновляться в файле настроек при изменении свойства.

 Некоторые компоненты Windows <xref:System.Windows.Forms.ToolStripItem>Forms, такие как , не поддерживают привязки настроек.

### <a name="settings-serialization"></a>Сериализация параметров
 Когда <xref:System.Configuration.LocalFileSettingsProvider> необходимо сохранить настройки на диске, он выполняет следующие действия:

1. Использует отражение для изучения всех свойств, определенных на вашем <xref:System.Configuration.ApplicationSettingsBase> производном классе, найдя те, которые применяются с любым <xref:System.Configuration.ApplicationScopedSettingAttribute> или <xref:System.Configuration.UserScopedSettingAttribute>.

2. Сериализует свойство на диск. Он первым пытается <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> вызвать <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> или на тип <xref:System.ComponentModel.TypeConverter>связанных . Если это не удается, использует XML-сериализацию.

3. Распределяет параметры по файлам на основе атрибута параметра.

 Если вы реализуете свой собственный класс <xref:System.Configuration.SettingsSerializeAsAttribute> настроек, вы можете использовать для <xref:System.Configuration.SettingsSerializeAs> обозначения параметра для двоичного или пользовательского сериализации с помощью перечисления. Дополнительные сведения о создании собственных классов параметров в коде см. в разделе [Практическое руководство. Создание параметров приложения](how-to-create-application-settings.md).

### <a name="settings-file-locations"></a>Расположение файлов параметров
 Расположение файлов `app`.exe.config и *user*.config зависит от способа установки приложения. Для приложения, скопированного на локальном `app`компьютере, приложения на основе Windows, .exe.config будет проживать в том же каталоге, что и базовый каталог основного исполняемого файла приложения, а *пользователь*.config будет проживать в месте, указанном <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> отелем. Для приложения, установленного с помощью ClickOnce, оба этих файла будут проживать в каталоге данных ClickOnce под %InstallRoot% »Документы и настройки\\имени*пользователя*«Местные настройки».

 Место хранения этих файлов немного отличается, если пользователь включил профили роуминга, что позволяет пользователю определять различные настройки Windows и приложений, когда они используют другие компьютеры в домене. В этом случае, как ClickOnce приложений и `app`не-ClickOnce приложения будут иметь их .exe.config и *пользователь*.config файлы, хранящиеся под %InstallRoot%% "Документы и настройки\\*пользователя*данных.

 Дополнительные сведения о том, как параметры приложения работают с новой технологией развертывания, см. в разделе [ClickOnce и параметры приложения](/visualstudio/deployment/clickonce-and-application-settings). Для получения дополнительной информации о каталоге данных ClickOnce [см. Доступ к локальным и удаленным данным в приложениях ClickOnce.](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)

## <a name="application-settings-and-security"></a>Параметры приложения и безопасность
 Параметры приложения предназначены для работы в режиме частичного доверия, то есть в среде с ограниченным доступом, которая используется по умолчанию для приложений Windows Forms, размещенных в Интернете или интрасети. Для использования параметров приложения с поставщиком параметров по умолчанию специальные разрешения, выходящие за рамки частичного доверия, не нужны.

 Когда настройки приложения используются в приложении ClickOnce, файл `user`.config хранится в каталоге данных ClickOnce. Размер файла .config приложения не может превышать квоту каталога `user`данных, установленную ClickOnce. Дополнительные сведения см. в разделе [ClickOnce и параметры приложения](/visualstudio/deployment/clickonce-and-application-settings).

## <a name="custom-settings-providers"></a>Поставщики пользовательских настроек
 В архитектуре настройки приложений существует свободное соединение между классом настройки <xref:System.Configuration.ApplicationSettingsBase>приложений, полученным из , и связанными с ними поставщиками или поставщиками параметров, полученными из. <xref:System.Configuration.SettingsProvider> Эта связь определяется <xref:System.Configuration.SettingsProviderAttribute> только прикладной к классу обертки или ее индивидуальным свойствам. Если поставщик настроек явно не указан, <xref:System.Configuration.LocalFileSettingsProvider>используется поставщик по умолчанию. В результате такая архитектура позволяет создавать и использовать поставщиков настраиваемых параметров.

 Предположим, что требуется разработать и использовать `SqlSettingsProvider`, то есть поставщика, который будет хранить все данные параметров в базе данных Microsoft SQL Server. Ваш <xref:System.Configuration.SettingsProvider>класс, полученный из-под `Initialize` засена, <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>получит эту информацию в своем методе в качестве параметра типа. Затем <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> метод будет реализован для извлечения настроек <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> из хранилища данных и их сохранения. Поставщик может использовать <xref:System.Configuration.SettingsPropertyCollection> предоставленную информацию <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> для определения имени, типа и сферы действия объекта, а также любых других атрибутов параметров, определенных для этого свойства.

 Вашему поставщику будет необходимо реализовать одно свойство и один метод, реализация которых может оказаться сложной. Свойство <xref:System.Configuration.SettingsProvider.ApplicationName%2A> является абстрактным <xref:System.Configuration.SettingsProvider>свойством; Вы должны запрограммировать его, чтобы вернуть следующее:

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 Ваш производный класс также должен реализовать метод `Initialize`, который не принимает аргументы и не возвращает значения. Этот метод не <xref:System.Configuration.SettingsProvider>определен .

 Наконец, <xref:System.Configuration.IApplicationSettingsProvider> провайдер реализует поддержку освежающих настроек, возврата настроек к по умолчанию и обновления настроек от одной версии приложения к другой.

 После реализации и компиляции поставщика необходимо указать, что класс параметров должен использовать этого поставщика вместо значения по умолчанию. Вы достигаете <xref:System.Configuration.SettingsProviderAttribute>этого через . При применении ко всему классу параметров поставщик используется для каждого параметра, который определяет класс; при применении к отдельным параметрам архитектура параметров приложений <xref:System.Configuration.LocalFileSettingsProvider> использует этот поставщик только для этих настроек, а для остальных — для остальных. В следующем примере кода показано, как указать классу параметров, что необходимо использовать пользовательского поставщика.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 Поставщик можно вызывать одновременно из нескольких потоков, но он всегда будет выполнять запись данных в одно место хранения. Таким образом, архитектура параметров приложения будет всегда создавать только один экземпляр класса поставщика.

> [!IMPORTANT]
> Следует убедиться, что поставщик является потокобезопасным и позволяет выполнять запись в файлы конфигурации только одному потоку за раз.

 Поставщику не нужно поддерживать все атрибуты параметров, <xref:System.Configuration?displayProperty=nameWithType> определенные в пространстве имен, <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute>хотя он должен <xref:System.Configuration.DefaultSettingValueAttribute>иметь минимальную поддержку и, а также поддерживать. Для тех атрибутов, которые он не поддерживает, поставщик должен завершаться ошибкой без уведомления. Он не должен создавать исключение. Однако если класс настроек использует недействительную комбинацию <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> атрибутов, например, применяя и в том же параметре, поставщик должен выбросить исключение и прекратить работу.

## <a name="see-also"></a>См. также раздел

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Общие сведения о параметрах приложений](application-settings-overview.md)
- [Параметры приложения для пользовательских элементов управления](application-settings-for-custom-controls.md)
- [ClickOnce и настройки приложений](/visualstudio/deployment/clickonce-and-application-settings)
- [Схема параметров приложения](../../configure-apps/file-schema/application-settings-schema.md)
