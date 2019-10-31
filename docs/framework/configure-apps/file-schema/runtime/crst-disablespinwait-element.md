---
title: < Crst_DisableSpinWait > элемент
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117642"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="136fc-102">\<Crst_DisableSpinWait > элемент</span><span class="sxs-lookup"><span data-stu-id="136fc-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="136fc-103">Указывает, следует ли отключать режим ожидания для критической секции, если это не так.</span><span class="sxs-lookup"><span data-stu-id="136fc-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="136fc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="136fc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="136fc-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="136fc-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="136fc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**</span><span class="sxs-lookup"><span data-stu-id="136fc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="136fc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="136fc-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="136fc-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="136fc-108">Attributes and Elements</span></span>

<span data-ttu-id="136fc-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="136fc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="136fc-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="136fc-110">Attributes</span></span>  
  
|<span data-ttu-id="136fc-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="136fc-111">Attribute</span></span>|<span data-ttu-id="136fc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="136fc-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="136fc-113">**доступной**</span><span class="sxs-lookup"><span data-stu-id="136fc-113">**enabled**</span></span>|<span data-ttu-id="136fc-114">Указывает, отключен ли режим ожидания для критических разделов, если они не включены.</span><span class="sxs-lookup"><span data-stu-id="136fc-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="136fc-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="136fc-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="136fc-116">значения</span><span class="sxs-lookup"><span data-stu-id="136fc-116">Value</span></span>|<span data-ttu-id="136fc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="136fc-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="136fc-118">1</span><span class="sxs-lookup"><span data-stu-id="136fc-118">1</span></span>|<span data-ttu-id="136fc-119">Отключите режим ожидания, если критическая секция не может быть получена.</span><span class="sxs-lookup"><span data-stu-id="136fc-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="136fc-120">0</span><span class="sxs-lookup"><span data-stu-id="136fc-120">0</span></span>|<span data-ttu-id="136fc-121">Не отключайте режим ожидания, если критическая секция не может быть получена.</span><span class="sxs-lookup"><span data-stu-id="136fc-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="136fc-122">Это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="136fc-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="136fc-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="136fc-123">Child Elements</span></span>  
 <span data-ttu-id="136fc-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="136fc-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="136fc-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="136fc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="136fc-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="136fc-126">Element</span></span>|<span data-ttu-id="136fc-127">Описание</span><span class="sxs-lookup"><span data-stu-id="136fc-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="136fc-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="136fc-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="136fc-129">Содержит сведения о различных параметрах конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="136fc-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="136fc-130">Пример</span><span class="sxs-lookup"><span data-stu-id="136fc-130">Example</span></span>  

<span data-ttu-id="136fc-131">В следующем примере отключается ожидание в критических разделах, если это не так.</span><span class="sxs-lookup"><span data-stu-id="136fc-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="136fc-132">См. также</span><span class="sxs-lookup"><span data-stu-id="136fc-132">See also</span></span>

- [<span data-ttu-id="136fc-133">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="136fc-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="136fc-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="136fc-134">Configuration File Schema</span></span>](../index.md)
