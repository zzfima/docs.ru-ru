---
title: Раздел конфигурации Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4a54df0b6301f1aae14d5561c91c6792cb0a1620
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109813"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="013ac-102">Раздел конфигурации Windows Forms</span><span class="sxs-lookup"><span data-stu-id="013ac-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="013ac-103">Параметры конфигурации Windows Forms позволяют приложению Windows Forms хранить и извлекать сведения о настроенных параметрах приложения, таких как поддержка нескольких мониторов, поддержка высокого разрешения (DPI) и другие предопределенные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="013ac-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="013ac-104">Параметры конфигурации приложения Windows Forms хранятся в элементе `System.Windows.Forms.ApplicationConfigurationSection` файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="013ac-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="013ac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="013ac-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="013ac-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="013ac-106">Attributes and elements</span></span>

<span data-ttu-id="013ac-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="013ac-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="013ac-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="013ac-108">Attributes</span></span>

<span data-ttu-id="013ac-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="013ac-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="013ac-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="013ac-110">Child elements</span></span>

<span data-ttu-id="013ac-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="013ac-111">Element</span></span>  |<span data-ttu-id="013ac-112">Описание</span><span class="sxs-lookup"><span data-stu-id="013ac-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="013ac-113">Добавляет ключ параметра конфигурации с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="013ac-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="013ac-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="013ac-114">Parent elements</span></span>

<span data-ttu-id="013ac-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="013ac-115">Element</span></span>  |<span data-ttu-id="013ac-116">Описание</span><span class="sxs-lookup"><span data-stu-id="013ac-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="013ac-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="013ac-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="013ac-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="013ac-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="013ac-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="013ac-119">Remarks</span></span>

<span data-ttu-id="013ac-120">Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="013ac-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="013ac-121">Элемент `<System.Windows.Forms.ApplicationConfigurationSection>` может содержать один или несколько дочерних элементов [`<add>`](windows-forms-add-configuration-element.md), каждый из которых определяет конкретный параметр конфигурации.</span><span class="sxs-lookup"><span data-stu-id="013ac-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="013ac-122">См. также</span><span class="sxs-lookup"><span data-stu-id="013ac-122">See also</span></span>

- [<span data-ttu-id="013ac-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="013ac-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="013ac-124">Поддержка высокого DPI в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="013ac-124">High DPI Support in Windows Forms</span></span>](../../../winforms/high-dpi-support-in-windows-forms.md)
