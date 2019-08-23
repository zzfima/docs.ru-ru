---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 254d34149892abeaf31b9227f7567eb0a66ec0b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943668"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="e756d-101">\<Сессионтокенрекуиремент ></span><span class="sxs-lookup"><span data-stu-id="e756d-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="e756d-102">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="e756d-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="e756d-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="e756d-103">\<system.identityModel></span></span>  
<span data-ttu-id="e756d-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e756d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e756d-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e756d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e756d-106">\<add></span><span class="sxs-lookup"><span data-stu-id="e756d-106">\<add></span></span>  
<span data-ttu-id="e756d-107">\<Сессионтокенрекуиремент ></span><span class="sxs-lookup"><span data-stu-id="e756d-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e756d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e756d-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e756d-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e756d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e756d-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e756d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e756d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e756d-111">Attributes</span></span>  
  
|<span data-ttu-id="e756d-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e756d-112">Attribute</span></span>|<span data-ttu-id="e756d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e756d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e756d-114">время существования</span><span class="sxs-lookup"><span data-stu-id="e756d-114">lifetime</span></span>|<span data-ttu-id="e756d-115">Указывает время существования маркеров сеанса.</span><span class="sxs-lookup"><span data-stu-id="e756d-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e756d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e756d-116">Child Elements</span></span>  
 <span data-ttu-id="e756d-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e756d-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e756d-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e756d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e756d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="e756d-119">Element</span></span>|<span data-ttu-id="e756d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e756d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e756d-121">\<add></span><span class="sxs-lookup"><span data-stu-id="e756d-121">\<add></span></span>](add.md)|<span data-ttu-id="e756d-122">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e756d-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e756d-123">Пример</span><span class="sxs-lookup"><span data-stu-id="e756d-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
