---
title: "Параметры приложения для пользовательских элементов управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e21a49b26a7493aaec31d5a97e627ce7925f39b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="application-settings-for-custom-controls"></a>Параметры приложения для пользовательских элементов управления
Необходимо выполнить определенные задачи, чтобы предоставить пользовательским элементам управления возможность сохранять параметры приложения, когда элементы управления размещаются в сторонних приложениях.  
  
 Большая часть документации о параметры приложения записывается в предположении, что вы создаете автономное приложение. Тем не менее, при создании элемента управления, который другие разработчики будут размещать в своих приложениях, потребуются некоторые дополнительные действия для элемента управления для сохранения его параметры должным образом.  
  
## <a name="application-settings-and-custom-controls"></a>Параметры приложения и пользовательские элементы управления  
 Элемент управления правильно сохранял свои параметры, он должен инкапсулировать процесс путем создания собственного выделенного приложений параметры класс-оболочку, производный от <xref:System.Configuration.ApplicationSettingsBase>. Кроме того, необходимо реализовать класс основного элемента управления <xref:System.Configuration.IPersistComponentSettings>. Интерфейс содержит несколько свойств, а также два метода <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> и <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. При добавлении элемента управления в форме с помощью **конструктор Windows Forms** Windows Forms в Visual Studio вызывает <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> автоматически при инициализации элемента управления, необходимо вызвать <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> самостоятельно в `Dispose` метод элемента управления.  
  
 Кроме того чтобы параметры приложения для пользовательских элементов управления для правильной работы в среде разработки, такой как Visual Studio следует реализовать следующие:  
  
1.  Пользовательский класс параметров приложения с конструктором, который принимает <xref:System.ComponentModel.IComponent> как один параметр. Этот класс используется для сохранения и загрузки всех параметров приложения. При создании нового экземпляра этого класса, необходимо передайте пользовательский элемент управления с помощью конструктора.  
  
2.  Создайте этот пользовательский класс параметров после создания элемента управления и помещен в форму, например в форме <xref:System.Windows.Forms.Form.Load> обработчика событий.  
  
 Инструкции по созданию пользовательского класса параметров см. в разделе [как: Создание параметров приложения](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
## <a name="settings-keys-and-shared-settings"></a>Ключи параметров и общие параметры  
 Некоторые элементы управления могут использоваться несколько раз в пределах той же форме. В большинстве случаев, может потребоваться, эти элементы управления для сохранения своих собственных отдельных параметров. С <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> свойство <xref:System.Configuration.IPersistComponentSettings>, можно указать уникальную строку, которая действует для однозначного определения нескольких версий элемента управления в форме.  
  
 Самый простой способ реализации <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> заключается в использовании <xref:System.Windows.Forms.Control.Name%2A> свойства элемента управления для <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. При загрузке или сохранении параметров элемента управления, передается значение <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> на <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> свойство <xref:System.Configuration.ApplicationSettingsBase> класса. Параметры приложения используют этот уникальный ключ для сохранения параметров пользователя в XML. В следующем коде показано, как `<userSettings>` раздел может выполнять поиск экземпляра пользовательского элемента управления с именем `CustomControl1` , сохраняет параметр в его `Text` свойство.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Элемент управления, который нужно вводить значение для любых экземпляров <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> будут совместно использовать те же параметры.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [Архитектура параметров приложения](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
