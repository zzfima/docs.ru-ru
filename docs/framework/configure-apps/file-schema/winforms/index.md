---
title: Раздел конфигурации Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18d8e1e24af73c9521b3a5bb45f1c86fc52ff1e9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="b162b-102">Раздел конфигурации Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b162b-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="b162b-103">Параметры конфигурации Windows Forms позволяют приложению Windows Forms хранить и извлекать сведения о настроенных параметрах приложения, таких как поддержка нескольких мониторов, поддержка высокого разрешения (DPI) и другие предопределенные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b162b-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="b162b-104">Параметры конфигурации приложения Windows Forms хранятся в элементе `System.Windows.Forms.ApplicationConfigurationSection` файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b162b-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="b162b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b162b-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b162b-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="b162b-106">Attributes and elements</span></span>

<span data-ttu-id="b162b-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b162b-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b162b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b162b-108">Attributes</span></span>

<span data-ttu-id="b162b-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b162b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b162b-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b162b-110">Child elements</span></span>

<span data-ttu-id="b162b-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="b162b-111">Element</span></span>  |<span data-ttu-id="b162b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b162b-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="b162b-113">Добавляет ключ параметра конфигурации с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="b162b-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="b162b-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b162b-114">Parent elements</span></span>

<span data-ttu-id="b162b-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="b162b-115">Element</span></span>  |<span data-ttu-id="b162b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b162b-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="b162b-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b162b-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="b162b-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b162b-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="b162b-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="b162b-119">Remarks</span></span>

<span data-ttu-id="b162b-120">Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b162b-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="b162b-121">Элемент `<System.Windows.Forms.ApplicationConfigurationSection>` может содержать один или несколько дочерних элементов [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md), каждый из которых определяет конкретный параметр конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b162b-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="b162b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b162b-122">See also</span></span>

<span data-ttu-id="b162b-123">[Схема файлов конфигурации для .NET Framework](../index.md) </span><span class="sxs-lookup"><span data-stu-id="b162b-123">[Configuration File Schema](../index.md) </span></span>  
[<span data-ttu-id="b162b-124">Поддержка высокого DPI в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b162b-124">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
