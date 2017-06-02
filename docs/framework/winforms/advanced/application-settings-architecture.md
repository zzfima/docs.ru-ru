---
title: "Application Settings Architecture | Microsoft Docs"
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
  - "application settings [Windows Forms], architecture"
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Application Settings Architecture
В этом разделе описывается архитектура параметров приложения и изучаются дополнительные возможности этой архитектуры, такие как сгруппированные параметры и ключи параметров.  
  
 Архитектура параметров приложений поддерживает определение строго типизированных параметров на уровне приложения или пользователя и сохранение параметров между сеансами приложения.  Эта архитектура обеспечивает стандартные механизмы сохранения для сохранения и загрузки параметров из локальной файловой системы.  Она также определяет интерфейсы для предоставления пользовательских механизмов сохранения.  
  
 Эти интерфейсы позволяют пользовательским компонентам сохранять собственные параметры, когда они размещены в приложении.  С помощью ключей параметров компоненты могут отдельно хранить параметры для нескольких экземпляров компонента.  
  
## Определение параметров  
 Архитектура параметров приложения используется как в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], так и в Windows Forms. Она содержит общие для обоих сред базовые классы.  Наиболее важным является класс <xref:System.Configuration.SettingsBase>, который предоставляет доступ к параметрам через коллекции и содержит методы низкого уровня для загрузки и сохранения параметров.  Каждая среда реализует свой собственный класс, производный от <xref:System.Configuration.SettingsBase> для обеспечения дополнительных функциональных возможностей параметров для этой среды.  В приложении Windows Forms все параметры приложения должны быть определенны в классе, производном от класса <xref:System.Configuration.ApplicationSettingsBase>, который добавляет следующие функции к базовому классу:  
  
-   Операции загрузки и сохранения более высокого уровня  
  
-   Поддержка параметров пользователей  
  
-   Возврат параметров пользователя к предопределенным значениям, используемым по умолчанию  
  
-   Обновление параметров из предыдущей версии приложения  
  
-   Проверка параметров перед их изменением или сохранением  
  
 Параметры можно описать с помощью ряда атрибутов, определенных в пространстве имен <xref:System.Configuration>; эти атрибуты описаны в разделе [Application Settings Attributes](../../../../docs/framework/winforms/advanced/application-settings-attributes.md).  При определении параметра его необходимо применить вместе с атрибутом <xref:System.Configuration.ApplicationScopedSettingAttribute> или <xref:System.Configuration.UserScopedSettingAttribute>, который описывает область применения параметра: для всего приложения или только для текущего пользователя.  
  
 В следующем примере определяется пользовательский класс параметров с одним параметром  `BackgroundColor`.  
  
 [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
## Сохранение параметров  
 Сам по себе класс <xref:System.Configuration.ApplicationSettingsBase> не сохраняет и не загружает параметры; это выполняет поставщик параметров — класс, производный от <xref:System.Configuration.SettingsProvider>.  Если производный от <xref:System.Configuration.ApplicationSettingsBase> класс не указывает поставщик параметров посредством атрибута <xref:System.Configuration.SettingsProviderAttribute>, то используется поставщик по умолчанию, <xref:System.Configuration.LocalFileSettingsProvider>.  
  
 Система конфигурации, которая была первоначально выпущена с [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], поддерживает предоставление статических данных конфигурации приложения с помощью файла machine.config локального компьютера или с помощью файла `app.`exe.config, развертываемого вместе с приложением.  Класс <xref:System.Configuration.LocalFileSettingsProvider> расширяет эту встроенную поддержку перечисленными ниже способами.  
  
-   Параметры с областью действия приложения могут храниться в файле machine.config или `app.`exe.config.  Файл machine.config всегда доступен только для чтения. Из соображений безопасности для большинства приложений файл `app`.exe.config также доступен только для чтения.  
  
-   Параметры, имеющие область действия пользователя, могут сохраняться в файлы `app`.exe.config, в этом случае они рассматриваются как статические значения по умолчанию.  
  
-   Отличные от значений по умолчанию параметры пользователей хранятся в новом файле, *user*.config, где *user* является именем пользователя, выполняющего в данный момент приложение.  Значение по умолчанию для параметра пользователя можно указать с помощью атрибута <xref:System.Configuration.DefaultSettingValueAttribute>.  Поскольку параметры пользователя часто изменяются во время выполнения приложения, `user`.config всегда доступен для чтения и записи.  
  
 Все три файла конфигурации хранят параметры в формате XML.  XML\-элементом верхнего уровня для параметров приложения является `<appSettings>`, а для параметров пользователя используется элемент `<userSettings>`.  Файл `app`.exe.config, который содержит как параметры приложения, так и значения по умолчанию для параметров пользователя, выглядит следующим образом:  
  
```  
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
  
 Определение элементов в разделе параметров приложения файла конфигурации см. в разделе [Схема параметров приложения](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md).  
  
### Привязка параметров  
 Параметры приложений используют архитектуру привязки данных Windows Forms для предоставления двустороннего обмена данными обновлений параметров между объектом параметров и компонентами.  Если для создания параметров приложения и назначения их свойствам компонентов используется Visual Studio, эти привязки создаются автоматически.  
  
 Параметр можно привязать только к компоненту, который поддерживает интерфейс <xref:System.Windows.Forms.IBindableComponent>.  Кроме того, компонент должен реализовывать событие изменения для конкретного связанного свойства или уведомлять параметры приложений об изменении свойства с помощью интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>.  Если компонент не реализует интерфейс <xref:System.Windows.Forms.IBindableComponent> и при привязка осуществляется с помощью Visual Studio, связанные свойства будут установлены в первый раз, но не будут обновляться.  Если компонент реализует интерфейс <xref:System.Windows.Forms.IBindableComponent>, но не поддерживает уведомления об изменении свойств, привязка не будет обновлять файл параметров при изменении свойства.  
  
 Некоторые компоненты Windows Forms, например <xref:System.Windows.Forms.ToolStripItem>, не поддерживают привязку параметров.  
  
### Сериализация параметров  
 Если поставщику <xref:System.Configuration.LocalFileSettingsProvider> требуется сохранить параметры на диск, он выполняет перечисленные ниже действия.  
  
1.  Использует отражение для проверки всех свойств, определенных для производного от <xref:System.Configuration.ApplicationSettingsBase> класса, выявляя свойства, примененные с атрибутами <xref:System.Configuration.ApplicationScopedSettingAttribute> и <xref:System.Configuration.UserScopedSettingAttribute>.  
  
2.  Сериализует свойство на диск.  Сначала пытается вызвать метод <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> или <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> связанного с типом класса <xref:System.ComponentModel.TypeConverter>.  Если это не удается, использует XML\-сериализацию.  
  
3.  Распределяет параметры по файлам на основании атрибута параметра.  
  
 Если реализован собственный класс параметров, атрибут <xref:System.Configuration.SettingsSerializeAsAttribute> можно использовать для пометки свойства как предназначенного для двоичной или пользовательской сериализации с помощью перечисления <xref:System.Configuration.SettingsSerializeAs>.  Дополнительные сведения о создании собственных классов параметров в коде см. в разделе [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### Расположения файлов параметров  
 Расположение файлов `app`.exe.config и *user*.config зависит от способа установки приложения.  Для приложения Windows Forms, скопированного на локальный компьютер, файл `app`.exe.config будет находиться в базовом каталоге основного исполняемого файла, а *user*.config будет располагаться в папке, указанной в свойстве <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=fullName>.  Для приложения, установленного с помощью [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], оба этих файла будут находиться в каталоге данных [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], расположенном в каталоге %InstallRoot%\\Documents and Settings\\*имя\_пользователя*\\Local Settings.  
  
 Место хранения этих файлов немного отлично, если пользователь использует перемещаемые профили, что позволяет пользователю определять различные параметры приложения и Windows при работе на других компьютерах в домене.  В этом случае приложения, которые устанавливались как с помощью [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], так и без помощи [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], будут хранить свои файлы `app`.exe.config и *user*.config в папке %InstallRoot%\\Documents и Settings\\*имя\_пользователя*\\Application Data.  
  
 Дополнительные сведения о том, как параметры приложения работают с новой технологией развертывания, см. в разделе [ClickOnce и параметры приложения](../Topic/ClickOnce%20and%20Application%20Settings.md).  Дополнительные сведения о каталоге данных [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] см. в разделе [Доступ к локальным и удаленным данным в приложениях ClickOnce](../Topic/Accessing%20Local%20and%20Remote%20Data%20in%20ClickOnce%20Applications.md).  
  
## Параметры приложений и безопасность  
 Параметры приложения предназначены для работы в среде с частичным доверием — ограниченной среде, которая используется по умолчанию для приложений Windows Forms, расположенных в Интернете или интрасети.  Для использования параметров приложения с поставщиком параметров по умолчанию не требуются специальных разрешений, выходящих за пределы частичного доверия.  
  
 При использовании параметров приложений в приложении [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] файл `user`.config хранится в каталоге данных [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)].  Размер файла `user`.config приложения не может превышать квоту каталога данных, заданную в [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)].  Дополнительные сведения см. в разделе [ClickOnce и параметры приложения](../Topic/ClickOnce%20and%20Application%20Settings.md).  
  
## Пользовательские поставщики параметров  
 В архитектуре параметров приложений имеется свободная связь между производным от класса <xref:System.Configuration.ApplicationSettingsBase> классом\-оболочкой параметров приложения, и связанным поставщиком или поставщиками параметров, производными от класса <xref:System.Configuration.SettingsProvider>.  Эта связь определяется только при применении атрибута <xref:System.Configuration.SettingsProviderAttribute> к классу\-оболочке или его отдельным свойствам.  Если поставщик параметров не указан явно, используется поставщик по умолчанию — <xref:System.Configuration.LocalFileSettingsProvider>.  В результате эта архитектура поддерживает создание и использование пользовательских поставщиков параметров.  
  
 Предположим, например, что требуется разработать и использовать поставщик `SqlSettingsProvider`, который будет хранить все данные параметров в базе данных Microsoft SQL Server.  Класс, производный от <xref:System.Configuration.SettingsProvider>, получит эти сведения в методе  `Initialize`  в качестве параметра типа <xref:System.Collections.Specialized.NameValueCollection?displayProperty=fullName>.  Затем будет реализован метод <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> для получения параметров из хранилища данных и метод <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> для их сохранения.  Поставщик может использовать класс <xref:System.Configuration.SettingsPropertyCollection>, передаваемый методу <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> для определения имени, типа и области свойства, а так же любых других атрибутов параметров, определенных для этого свойства.  
  
 Поставщику необходимо реализовать одно свойство и один метод, реализация которых может оказаться не очевидной.  Свойство <xref:System.Configuration.SettingsProvider.ApplicationName%2A> является абстрактным свойством класса <xref:System.Configuration.SettingsProvider>; оно должно возвращать следующее:  
  
 [!code-csharp[ApplicationSettings.Architecture#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]  
  
 Производный класс должен также реализовать метод `Initialize`, который не принимает аргументы и не возвращает значение.  Этот метод не определен классом <xref:System.Configuration.SettingsProvider>.  
  
 Наконец, необходимо реализовать для поставщика интерфейс <xref:System.Configuration.IApplicationSettingsProvider>, который будет обеспечивать поддержку обновления параметров, возврата параметров к значениям по умолчанию и обновления параметров с одной версий приложения до другой.  
  
 После реализации и компиляции поставщика необходимо указать классу параметров, что необходимо использовать этот поставщик вместо поставщика по умолчанию.  Сделать это можно с помощью атрибута <xref:System.Configuration.SettingsProviderAttribute>.  Если применить его ко всему классу параметров, поставщик используется для каждого параметра, который определяется в классе; если атрибут применяется к отдельным параметрам, то архитектура параметров приложения использует этот поставщик только для этих параметров, а для остальных использует поставщик <xref:System.Configuration.LocalFileSettingsProvider>.  В следующем примере показано, как указать классу параметров использовать пользовательский поставщик.  
  
 [!code-csharp[ApplicationSettings.Architecture#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]  
  
 Поставщик может быть вызван из нескольких потоков одновременно, но он всегда будет записывать данные в одно место хранения; таким образом, архитектура параметров приложения будет всегда создавать только один экземпляр класса поставщика.  
  
> [!IMPORTANT]
>  Следует убедиться, что поставщик не создает конфликтов между потоками и позволяет одновременно выполнять запись в файлы конфигурации только одному потоку.  
  
 Поставщику не обязательно поддерживать все атрибуты параметров, определенные в пространстве имен <xref:System.Configuration?displayProperty=fullName>, хотя необходимо по меньшей мере поддерживать атрибуты <xref:System.Configuration.ApplicationScopedSettingAttribute>, <xref:System.Configuration.UserScopedSettingAttribute>, а также <xref:System.Configuration.DefaultSettingValueAttribute>.  Для тех атрибутов, которые не поддерживаются, поставщик должен давать сбой без уведомления; он не должен создавать исключение.  Однако, если класс параметров использует недопустимое сочетание атрибутов — как, например, применение атрибутов <xref:System.Configuration.ApplicationScopedSettingAttribute> и <xref:System.Configuration.UserScopedSettingAttribute> к одному и тому же параметру, — поставщик должен создавать исключение и прерывать операцию.  
  
## См. также  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 <xref:System.Configuration.LocalFileSettingsProvider>   
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [Application Settings for Custom Controls](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md)   
 [ClickOnce и параметры приложения](../Topic/ClickOnce%20and%20Application%20Settings.md)   
 [Схема параметров приложения](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)