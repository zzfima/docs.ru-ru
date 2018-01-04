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
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="912c1-102">Параметры приложения для пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="912c1-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="912c1-103">Необходимо выполнить определенные задачи, чтобы предоставить пользовательским элементам управления возможность сохранять параметры приложения, когда элементы управления размещаются в сторонних приложениях.</span><span class="sxs-lookup"><span data-stu-id="912c1-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>  
  
 <span data-ttu-id="912c1-104">Большая часть документации о параметры приложения записывается в предположении, что вы создаете автономное приложение.</span><span class="sxs-lookup"><span data-stu-id="912c1-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="912c1-105">Тем не менее, при создании элемента управления, который другие разработчики будут размещать в своих приложениях, потребуются некоторые дополнительные действия для элемента управления для сохранения его параметры должным образом.</span><span class="sxs-lookup"><span data-stu-id="912c1-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>  
  
## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="912c1-106">Параметры приложения и пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="912c1-106">Application Settings and Custom Controls</span></span>  
 <span data-ttu-id="912c1-107">Элемент управления правильно сохранял свои параметры, он должен инкапсулировать процесс путем создания собственного выделенного приложений параметры класс-оболочку, производный от <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="912c1-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="912c1-108">Кроме того, необходимо реализовать класс основного элемента управления <xref:System.Configuration.IPersistComponentSettings>.</span><span class="sxs-lookup"><span data-stu-id="912c1-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="912c1-109">Интерфейс содержит несколько свойств, а также два метода <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> и <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="912c1-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="912c1-110">При добавлении элемента управления в форме с помощью **конструктор Windows Forms** Windows Forms в Visual Studio вызывает <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> автоматически при инициализации элемента управления, необходимо вызвать <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> самостоятельно в `Dispose` метод элемента управления.</span><span class="sxs-lookup"><span data-stu-id="912c1-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>  
  
 <span data-ttu-id="912c1-111">Кроме того чтобы параметры приложения для пользовательских элементов управления для правильной работы в среде разработки, такой как Visual Studio следует реализовать следующие:</span><span class="sxs-lookup"><span data-stu-id="912c1-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>  
  
1.  <span data-ttu-id="912c1-112">Пользовательский класс параметров приложения с конструктором, который принимает <xref:System.ComponentModel.IComponent> как один параметр.</span><span class="sxs-lookup"><span data-stu-id="912c1-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="912c1-113">Этот класс используется для сохранения и загрузки всех параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="912c1-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="912c1-114">При создании нового экземпляра этого класса, необходимо передайте пользовательский элемент управления с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="912c1-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>  
  
2.  <span data-ttu-id="912c1-115">Создайте этот пользовательский класс параметров после создания элемента управления и помещен в форму, например в форме <xref:System.Windows.Forms.Form.Load> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="912c1-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
 <span data-ttu-id="912c1-116">Инструкции по созданию пользовательского класса параметров см. в разделе [как: Создание параметров приложения](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span><span class="sxs-lookup"><span data-stu-id="912c1-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span></span>  
  
## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="912c1-117">Ключи параметров и общие параметры</span><span class="sxs-lookup"><span data-stu-id="912c1-117">Settings Keys and Shared Settings</span></span>  
 <span data-ttu-id="912c1-118">Некоторые элементы управления могут использоваться несколько раз в пределах той же форме.</span><span class="sxs-lookup"><span data-stu-id="912c1-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="912c1-119">В большинстве случаев, может потребоваться, эти элементы управления для сохранения своих собственных отдельных параметров.</span><span class="sxs-lookup"><span data-stu-id="912c1-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="912c1-120">С <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> свойство <xref:System.Configuration.IPersistComponentSettings>, можно указать уникальную строку, которая действует для однозначного определения нескольких версий элемента управления в форме.</span><span class="sxs-lookup"><span data-stu-id="912c1-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>  
  
 <span data-ttu-id="912c1-121">Самый простой способ реализации <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> заключается в использовании <xref:System.Windows.Forms.Control.Name%2A> свойства элемента управления для <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="912c1-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="912c1-122">При загрузке или сохранении параметров элемента управления, передается значение <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> на <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> свойство <xref:System.Configuration.ApplicationSettingsBase> класса.</span><span class="sxs-lookup"><span data-stu-id="912c1-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="912c1-123">Параметры приложения используют этот уникальный ключ для сохранения параметров пользователя в XML.</span><span class="sxs-lookup"><span data-stu-id="912c1-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="912c1-124">В следующем коде показано, как `<userSettings>` раздел может выполнять поиск экземпляра пользовательского элемента управления с именем `CustomControl1` , сохраняет параметр в его `Text` свойство.</span><span class="sxs-lookup"><span data-stu-id="912c1-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 <span data-ttu-id="912c1-125">Элемент управления, который нужно вводить значение для любых экземпляров <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> будут совместно использовать те же параметры.</span><span class="sxs-lookup"><span data-stu-id="912c1-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="912c1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="912c1-126">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [<span data-ttu-id="912c1-127">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="912c1-127">Application Settings Architecture</span></span>](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
