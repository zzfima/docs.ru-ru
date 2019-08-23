---
title: Схема параметров приложения
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927764"
---
# <a name="application-settings-schema"></a><span data-ttu-id="046f3-102">Схема параметров приложения</span><span class="sxs-lookup"><span data-stu-id="046f3-102">Application Settings schema</span></span>

<span data-ttu-id="046f3-103">Параметры приложения позволяют Windows Forms или ASP.NET приложению сохранять и извлекать параметры приложения и области пользователя.</span><span class="sxs-lookup"><span data-stu-id="046f3-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="046f3-104">В этом контексте *параметр* — это любой фрагмент информации, который может быть специфичен для приложения или зависит от текущего пользователя — от строки подключения к базе данных до предпочитаемого пользователем размера окна по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="046f3-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="046f3-105">По умолчанию параметры приложения в Windows Formsном приложении используют <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения параметров в XML-файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="046f3-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="046f3-106">Дополнительные сведения о файлах, используемых параметрами приложения, см. в разделе [архитектура параметров приложения](../../winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="046f3-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="046f3-107">Параметры приложения определяют следующие элементы в составе файлов конфигурации, которые он использует.</span><span class="sxs-lookup"><span data-stu-id="046f3-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="046f3-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="046f3-108">Element</span></span>                    | <span data-ttu-id="046f3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="046f3-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="046f3-110">**\<applicationSettings >**</span><span class="sxs-lookup"><span data-stu-id="046f3-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="046f3-111">Содержит все  **\<параметры >** теги, относящиеся к приложению.</span><span class="sxs-lookup"><span data-stu-id="046f3-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="046f3-112">**\<userSettings >**</span><span class="sxs-lookup"><span data-stu-id="046f3-112">**\<userSettings>**</span></span>        | <span data-ttu-id="046f3-113">Содержит все  **\<параметры >** теги, относящиеся к текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="046f3-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="046f3-114">**\<Настройка >**</span><span class="sxs-lookup"><span data-stu-id="046f3-114">**\<setting>**</span></span>             | <span data-ttu-id="046f3-115">Определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="046f3-115">Defines a setting.</span></span> <span data-ttu-id="046f3-116">Дочерний элемент **> applicationSettingsили>UserSettings.\<**  **\<**</span><span class="sxs-lookup"><span data-stu-id="046f3-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="046f3-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="046f3-117">**\<value>**</span></span>               | <span data-ttu-id="046f3-118">Определяет значение параметра.</span><span class="sxs-lookup"><span data-stu-id="046f3-118">Defines a setting's value.</span></span> <span data-ttu-id="046f3-119">Дочерний элемент  **параметра>.\<**</span><span class="sxs-lookup"><span data-stu-id="046f3-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="046f3-120">\<applicationSettings >, элемент</span><span class="sxs-lookup"><span data-stu-id="046f3-120">\<applicationSettings> element</span></span>

<span data-ttu-id="046f3-121">Этот элемент содержит все  **\<параметры >** теги, характерные для экземпляра приложения на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="046f3-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="046f3-122">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="046f3-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="046f3-123">\<Элемент > userSettings</span><span class="sxs-lookup"><span data-stu-id="046f3-123">\<userSettings> element</span></span>

<span data-ttu-id="046f3-124">Этот элемент содержит все  **\<параметры >** теги, характерные для пользователя, который в настоящее время использует приложение.</span><span class="sxs-lookup"><span data-stu-id="046f3-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="046f3-125">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="046f3-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="046f3-126">\<Установка > элемента</span><span class="sxs-lookup"><span data-stu-id="046f3-126">\<setting> element</span></span>

<span data-ttu-id="046f3-127">Этот элемент определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="046f3-127">This element defines a setting.</span></span> <span data-ttu-id="046f3-128">Он имеет следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="046f3-128">It has the following attributes.</span></span>

| <span data-ttu-id="046f3-129">Атрибут</span><span class="sxs-lookup"><span data-stu-id="046f3-129">Attribute</span></span>        | <span data-ttu-id="046f3-130">Описание</span><span class="sxs-lookup"><span data-stu-id="046f3-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="046f3-131">**name**</span><span class="sxs-lookup"><span data-stu-id="046f3-131">**name**</span></span>         | <span data-ttu-id="046f3-132">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="046f3-132">Required.</span></span> <span data-ttu-id="046f3-133">Уникальный идентификатор параметра.</span><span class="sxs-lookup"><span data-stu-id="046f3-133">The unique ID of the setting.</span></span> <span data-ttu-id="046f3-134">Параметры, созданные в Visual Studio, сохраняются с именем `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="046f3-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="046f3-135">**сериализедас**</span><span class="sxs-lookup"><span data-stu-id="046f3-135">**serializedAs**</span></span> | <span data-ttu-id="046f3-136">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="046f3-136">Required.</span></span> <span data-ttu-id="046f3-137">Формат, используемый для сериализации значения в текст.</span><span class="sxs-lookup"><span data-stu-id="046f3-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="046f3-138">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="046f3-138">Valid values are:</span></span><br><br><span data-ttu-id="046f3-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="046f3-139">- `string`.</span></span> <span data-ttu-id="046f3-140">Значение сериализуется в виде строки с помощью <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="046f3-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="046f3-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="046f3-141">- `xml`.</span></span> <span data-ttu-id="046f3-142">Значение сериализуется с помощью сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="046f3-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="046f3-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="046f3-143">- `binary`.</span></span> <span data-ttu-id="046f3-144">Значение сериализуется как двоичный файл, закодированный в виде текста, с помощью двоичной сериализации.</span><span class="sxs-lookup"><span data-stu-id="046f3-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="046f3-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="046f3-145">- `custom`.</span></span> <span data-ttu-id="046f3-146">Поставщик параметров обладает знаниями об этом параметре и сериализует и десериализует его.</span><span class="sxs-lookup"><span data-stu-id="046f3-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="046f3-147">\<Элемент > value</span><span class="sxs-lookup"><span data-stu-id="046f3-147">\<value> element</span></span>

<span data-ttu-id="046f3-148">Этот элемент содержит значение параметра.</span><span class="sxs-lookup"><span data-stu-id="046f3-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="046f3-149">Пример</span><span class="sxs-lookup"><span data-stu-id="046f3-149">Example</span></span>

<span data-ttu-id="046f3-150">В следующем примере показан файл параметров приложения, который определяет два параметра области приложения и два параметра уровня пользователя:</span><span class="sxs-lookup"><span data-stu-id="046f3-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
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

## <a name="see-also"></a><span data-ttu-id="046f3-151">См. также</span><span class="sxs-lookup"><span data-stu-id="046f3-151">See also</span></span>

- [<span data-ttu-id="046f3-152">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="046f3-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="046f3-153">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="046f3-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
