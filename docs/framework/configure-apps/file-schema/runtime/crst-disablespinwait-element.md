---
title: < Crst_DisableSpinWait > элемент
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a91e21120ecebbe7af2fb93798bc68d274fa92c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252714"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="9ffa4-102">\<Элемент > Crst_DisableSpinWait</span><span class="sxs-lookup"><span data-stu-id="9ffa4-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="9ffa4-103">Указывает, следует ли отключать режим ожидания для критической секции, если это не так.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="9ffa4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ffa4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ffa4-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ffa4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="9ffa4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**</span><span class="sxs-lookup"><span data-stu-id="9ffa4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ffa4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ffa4-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ffa4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ffa4-108">Attributes and Elements</span></span>

<span data-ttu-id="9ffa4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ffa4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ffa4-110">Attributes</span></span>  
  
|<span data-ttu-id="9ffa4-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9ffa4-111">Attribute</span></span>|<span data-ttu-id="9ffa4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9ffa4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ffa4-113">**доступной**</span><span class="sxs-lookup"><span data-stu-id="9ffa4-113">**enabled**</span></span>|<span data-ttu-id="9ffa4-114">Указывает, отключен ли режим ожидания для критических разделов, если они не включены.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9ffa4-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="9ffa4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9ffa4-116">Значение</span><span class="sxs-lookup"><span data-stu-id="9ffa4-116">Value</span></span>|<span data-ttu-id="9ffa4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9ffa4-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ffa4-118">1</span><span class="sxs-lookup"><span data-stu-id="9ffa4-118">1</span></span>|<span data-ttu-id="9ffa4-119">Отключите режим ожидания, если критическая секция не может быть получена.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="9ffa4-120">0</span><span class="sxs-lookup"><span data-stu-id="9ffa4-120">0</span></span>|<span data-ttu-id="9ffa4-121">Не отключайте режим ожидания, если критическая секция не может быть получена.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="9ffa4-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ffa4-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ffa4-123">Child Elements</span></span>  
 <span data-ttu-id="9ffa4-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ffa4-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ffa4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9ffa4-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ffa4-126">Element</span></span>|<span data-ttu-id="9ffa4-127">Описание</span><span class="sxs-lookup"><span data-stu-id="9ffa4-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9ffa4-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9ffa4-129">Содержит сведения о различных параметрах конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9ffa4-130">Пример</span><span class="sxs-lookup"><span data-stu-id="9ffa4-130">Example</span></span>  

<span data-ttu-id="9ffa4-131">В следующем примере отключается ожидание в критических разделах, если это не так.</span><span class="sxs-lookup"><span data-stu-id="9ffa4-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ffa4-132">См. также</span><span class="sxs-lookup"><span data-stu-id="9ffa4-132">See also</span></span>

- [<span data-ttu-id="9ffa4-133">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9ffa4-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9ffa4-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9ffa4-134">Configuration File Schema</span></span>](../index.md)
