---
title: Параметры приложения для пользовательских элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: a4e477ce1c171b514482623595b2c5565564a2cb
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040463"
---
# <a name="application-settings-for-custom-controls"></a>Параметры приложения для пользовательских элементов управления
Необходимо выполнить определенные задачи, чтобы предоставить настраиваемым элементам управления возможность сохранять параметры приложения при размещении элементов управления в сторонних приложениях.

 Большая часть документации о параметрах приложения записывается с учетом предположения о создании автономного приложения. Однако при создании элемента управления, который другие разработчики будут размещать в своих приложениях, необходимо выполнить несколько дополнительных действий, чтобы элемент управления правильно сохранял свои параметры.

## <a name="application-settings-and-custom-controls"></a>Параметры приложения и пользовательские элементы управления
 Чтобы ваш элемент управления правильно сохранял свои параметры, он должен инкапсулировать процесс, создав собственный класс-оболочку с параметрами выделенных приложений, производный от <xref:System.Configuration.ApplicationSettingsBase>. Кроме того, главный класс элементов управления должен реализовывать <xref:System.Configuration.IPersistComponentSettings>. Интерфейс содержит несколько свойств, а также два метода, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> и. <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> При добавлении элемента управления в форму с помощью **конструктор Windows Forms** в Visual Studio Windows Forms будет вызываться <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> автоматически при инициализации элемента управления; необходимо `Dispose` вызвать <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> себя в методе элемента управления.

 Кроме того, для правильной работы пользовательских элементов управления в средах разработки, таких как Visual Studio, необходимо реализовать следующие параметры.

1. Пользовательский класс параметров приложения с конструктором, принимающим <xref:System.ComponentModel.IComponent> в качестве одного параметра. Этот класс используется для сохранения и загрузки всех параметров приложения. При создании нового экземпляра этого класса передайте пользовательский элемент управления с помощью конструктора.

2. Создайте этот класс настраиваемых параметров после создания и размещения элемента управления в форме, например в обработчике <xref:System.Windows.Forms.Form.Load> событий формы.

 Инструкции по созданию класса пользовательских параметров см. в разделе [как Создание параметров](how-to-create-application-settings.md)приложения.

## <a name="settings-keys-and-shared-settings"></a>Параметры ключи и общие параметры
 Некоторые элементы управления могут использоваться несколько раз в одной форме. В большинстве случаев эти элементы управления должны сохранять свои индивидуальные параметры. С помощью <xref:System.Configuration.IPersistComponentSettings>свойства в можно указать уникальную строку, которая действует для устранения неоднозначности нескольких версий элемента управления в форме. <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>

 Самым простым способом реализации <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> является <xref:System.Windows.Forms.Control.Name%2A> использование свойства элемента управления для <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. При загрузке или сохранении параметров элемента управления значение <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> параметра передается свойству <xref:System.Configuration.ApplicationSettingsBase> класса. Параметры приложения используют этот уникальный ключ, если он сохраняет параметры пользователя в XML. В следующем примере кода показано, как `<userSettings>` раздел может искать экземпляр пользовательского элемента управления с именем `CustomControl1` , который сохраняет параметр для его `Text` свойства.

```xml
<userSettings>
    <CustomControl1>
        <setting name="Text" serializedAs="string">
            <value>Hello, World</value>
        </setting>
    </CustomControl1>
</userSettings>
```

 Все экземпляры элемента управления, которые не предоставляют значение для <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> , будут совместно использовать одни и те же параметры.

## <a name="see-also"></a>См. также

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [Архитектура параметров приложения](application-settings-architecture.md)
