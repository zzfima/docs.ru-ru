---
title: "Раздел конфигурации Windows Forms | Документы Майкрософт"
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
ms.translationtype: Human Translation
ms.sourcegitcommit: 39e8e757a446b30ab18914465853138e1c239e40
ms.openlocfilehash: dedf9497a684c4b11f84b60de21ec73b563c6d19
ms.contentlocale: ru-ru
ms.lasthandoff: 05/03/2017

---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="ef284-102">Раздел конфигурации Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef284-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="ef284-103">Параметры конфигурации Windows Forms позволяют приложению Windows Forms хранить и извлекать сведения о настроенных параметрах приложения, таких как поддержка нескольких мониторов, поддержка высокого разрешения (DPI) и другие предопределенные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ef284-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="ef284-104">Параметры конфигурации приложения Windows Forms хранятся в элементе `System.Windows.Forms.ConfigurationSection` файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="ef284-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef284-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef284-105">Syntax</span></span>

```xml
<configuration>
  \<System.Windows.Forms.ConfigurationSection>
  ...
  \</System.Windows.Forms.ConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ef284-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="ef284-106">Attributes and elements</span></span>

<span data-ttu-id="ef284-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ef284-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef284-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ef284-108">Attributes</span></span>

<span data-ttu-id="ef284-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ef284-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ef284-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ef284-110">Child elements</span></span>

<span data-ttu-id="ef284-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef284-111">Element</span></span>  |<span data-ttu-id="ef284-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ef284-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="ef284-113">Добавляет ключ параметра конфигурации с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="ef284-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="ef284-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ef284-114">Parent elements</span></span>

<span data-ttu-id="ef284-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef284-115">Element</span></span>  |<span data-ttu-id="ef284-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ef284-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="ef284-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ef284-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="ef284-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ef284-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="ef284-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef284-119">Remarks</span></span>

<span data-ttu-id="ef284-120">Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef284-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="ef284-121">Элемент `<System.Windows.Forms.ConfigurationSection>` может содержать один или несколько дочерних элементов [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md), каждый из которых определяет конкретный параметр конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ef284-121">The `<System.Windows.Forms.ConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef284-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ef284-122">See also</span></span>

<span data-ttu-id="ef284-123">[Схема файлов конфигурации для .NET Framework](../index.md)
[High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md) (Поддержка высокого разрешения (DPI) в Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ef284-123">[Configuration File Schema](../index.md)
[High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)</span></span>

