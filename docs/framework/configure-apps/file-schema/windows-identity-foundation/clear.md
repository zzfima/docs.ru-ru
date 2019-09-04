---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252042"
---
# <a name="clear"></a><span data-ttu-id="0f80c-101">\<очистить ></span><span class="sxs-lookup"><span data-stu-id="0f80c-101">\<clear></span></span>
<span data-ttu-id="0f80c-102">Удаляет все обработчики маркеров безопасности из текущей коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="0f80c-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
<span data-ttu-id="0f80c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f80c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f80c-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="0f80c-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="0f80c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0f80c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="0f80c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="0f80c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="0f80c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**</span><span class="sxs-lookup"><span data-stu-id="0f80c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f80c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f80c-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f80c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f80c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0f80c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0f80c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f80c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f80c-111">Attributes</span></span>  
 <span data-ttu-id="0f80c-112">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0f80c-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f80c-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f80c-113">Child Elements</span></span>  
 <span data-ttu-id="0f80c-114">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0f80c-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f80c-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f80c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0f80c-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f80c-116">Element</span></span>|<span data-ttu-id="0f80c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0f80c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f80c-118">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="0f80c-118">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="0f80c-119">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="0f80c-119">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
