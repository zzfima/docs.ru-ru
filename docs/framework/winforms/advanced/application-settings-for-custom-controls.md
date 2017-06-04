---
title: "Application Settings for Custom Controls | Microsoft Docs"
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
  - "custom controls [Windows Forms], application settings"
  - "application settings [Windows Forms], custom controls"
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Application Settings for Custom Controls
Чтобы предоставить пользовательским элементам управления, размещаемым в приложениях сторонних производителей, возможность сохранения параметров приложения, необходимо выполнить некоторые задачи.  
  
 Большинство документов, посвященных работе параметров приложения, написаны в предположении, что создается отдельное приложение.  Однако если создается элемент управления, который другие разработчики будут размещать в своих приложениях, то, чтобы этот элемент управления сохранял параметры приложения должным образом, необходимо выполнить некоторые дополнительные действия.  
  
## Параметры приложения и пользовательские элементы управления  
 Чтобы элемент управления правильно сохранял свои параметры, он должен инкапсулировать процесс путем создания собственного выделенного класса\-оболочки параметров приложений, производного от класса <xref:System.Configuration.ApplicationSettingsBase>.  Кроме того, основной класс элемента управления должен реализовывать интерфейс <xref:System.Configuration.IPersistComponentSettings>.  Этот интерфейс содержит несколько свойств, а также два метода — <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> и <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.  При добавлении элемента управления в форму с помощью конструктора **Windows Forms Designer** в Visual Studio форма Windows Forms будет автоматически вызывать метод <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> при инициализации элемента управления; необходимо вызвать метод <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> самостоятельно в методе  `Dispose` элемента управления.  
  
 Кроме того, для правильной работы параметров приложений для пользовательских элементов управления в среде разработки, такой как Visual Studio, следует реализовать следующие элементы.  
  
1.  Пользовательский класс параметров приложения с конструктором, который принимает интерфейс <xref:System.ComponentModel.IComponent> в качестве своего единственного параметра.  Этот класс используется для сохранения и загрузки всех параметров приложения.  При создании нового экземпляра этого класса передайте пользовательский элемент управления с помощью этого конструктора.  
  
2.  Создайте этот пользовательский класс параметров после того, как элемент управления создан и помещен в форму, например в обработчике событий <xref:System.Windows.Forms.Form.Load> формы.  
  
 Инструкции по созданию пользовательского класса параметров см. в разделе [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
## Ключи параметров и общие параметры  
 Некоторые элементы управления могут использоваться несколько раз в одной форме.  Большую часть времени необходимо, чтобы эти элементы управления сохраняли собственные индивидуальные параметры.  С помощью свойства <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> интерфейса <xref:System.Configuration.IPersistComponentSettings> можно предоставить уникальную строку, которая используется для устранения неоднозначности между несколькими версиями элемента управления в форме.  
  
 Самым простым способом реализации свойства <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> является использование для свойства <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> свойства <xref:System.Windows.Forms.Control.Name%2A> элемента управления.  При загрузке или сохранении параметров элемента управления значение свойства <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> передается свойству <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> класса <xref:System.Configuration.ApplicationSettingsBase>.  Параметры приложения используют этот уникальный ключ для сохранения параметров пользователя в XML\-файл.  В следующем примере кода показано, как раздел `<userSettings>` может выполнять поиск экземпляра пользовательского элемента управления с именем `CustomControl1` , который сохраняет параметр в своем свойстве  `Text` .  
  
```  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Все экземпляры элемента управления, которые не предоставляют значения для свойства <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>, будут использовать общие параметры.  
  
## См. также  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.IPersistComponentSettings>   
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)