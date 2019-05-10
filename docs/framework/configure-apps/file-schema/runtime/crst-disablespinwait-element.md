---
title: элемент < Crst_DisableSpinWait >
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f89f0558c11e229fef2ca3cd619e3c033f12c858
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754677"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="eb8e8-102">\<Crst_DisableSpinWait > элемент</span><span class="sxs-lookup"><span data-stu-id="eb8e8-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="eb8e8-103">Указывает, следует ли отключить спин ожидает критический раздел, если состязаний.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="eb8e8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eb8e8-104">\<configuration></span></span>  
<span data-ttu-id="eb8e8-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="eb8e8-105">\<runtime></span></span>  
<span data-ttu-id="eb8e8-106">\<Crst_DisableSpinWait ></span><span class="sxs-lookup"><span data-stu-id="eb8e8-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb8e8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb8e8-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb8e8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eb8e8-108">Attributes and Elements</span></span>

<span data-ttu-id="eb8e8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb8e8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb8e8-110">Attributes</span></span>  
  
|<span data-ttu-id="eb8e8-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eb8e8-111">Attribute</span></span>|<span data-ttu-id="eb8e8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="eb8e8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb8e8-113">**включен**</span><span class="sxs-lookup"><span data-stu-id="eb8e8-113">**enabled**</span></span>|<span data-ttu-id="eb8e8-114">Указывает, отключен ли спин ожидание критических секций, если они являются состязаний.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="eb8e8-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="eb8e8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="eb8e8-116">Значение</span><span class="sxs-lookup"><span data-stu-id="eb8e8-116">Value</span></span>|<span data-ttu-id="eb8e8-117">Описание</span><span class="sxs-lookup"><span data-stu-id="eb8e8-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb8e8-118">1</span><span class="sxs-lookup"><span data-stu-id="eb8e8-118">1</span></span>|<span data-ttu-id="eb8e8-119">Отключите ожидания спин, если не удается получить критический раздел.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="eb8e8-120">0</span><span class="sxs-lookup"><span data-stu-id="eb8e8-120">0</span></span>|<span data-ttu-id="eb8e8-121">Не отключайте спин ожидания, когда не удается получить критический раздел.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="eb8e8-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb8e8-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb8e8-123">Child Elements</span></span>  
 <span data-ttu-id="eb8e8-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb8e8-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb8e8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="eb8e8-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="eb8e8-126">Element</span></span>|<span data-ttu-id="eb8e8-127">Описание</span><span class="sxs-lookup"><span data-stu-id="eb8e8-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eb8e8-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="eb8e8-129">Содержит сведения о различных параметров конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eb8e8-130">Пример</span><span class="sxs-lookup"><span data-stu-id="eb8e8-130">Example</span></span>  

<span data-ttu-id="eb8e8-131">В следующем примере отключается спин ожидания в критических разделах при состязаний.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb8e8-132">См. также</span><span class="sxs-lookup"><span data-stu-id="eb8e8-132">See also</span></span>

- [<span data-ttu-id="eb8e8-133">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="eb8e8-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="eb8e8-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="eb8e8-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
