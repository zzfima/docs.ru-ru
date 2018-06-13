---
title: '&lt;remove&gt;'
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dfea0b0eb4b133308f10b523a659cc00f87252b8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755081"
---
# <a name="ltremovegt"></a><span data-ttu-id="2ba02-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="2ba02-102">&lt;remove&gt;</span></span>
<span data-ttu-id="2ba02-103">Удаляет обработчик маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="2ba02-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="2ba02-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="2ba02-104">\<system.identityModel></span></span>  
<span data-ttu-id="2ba02-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2ba02-105">\<identityConfiguration></span></span>  
<span data-ttu-id="2ba02-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="2ba02-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="2ba02-107">\<Удалите ></span><span class="sxs-lookup"><span data-stu-id="2ba02-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba02-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ba02-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ba02-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ba02-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ba02-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ba02-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ba02-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ba02-111">Attributes</span></span>  
  
|<span data-ttu-id="2ba02-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2ba02-112">Attribute</span></span>|<span data-ttu-id="2ba02-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2ba02-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ba02-114">type</span><span class="sxs-lookup"><span data-stu-id="2ba02-114">type</span></span>|<span data-ttu-id="2ba02-115">Имя типа CLR обработчик маркеров для удаления.</span><span class="sxs-lookup"><span data-stu-id="2ba02-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="2ba02-116">Дополнительные сведения о способах указания `type` см. в разделе [ссылок на пользовательские типы](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="2ba02-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="2ba02-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="2ba02-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ba02-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ba02-118">Child Elements</span></span>  
 <span data-ttu-id="2ba02-119">Нет</span><span class="sxs-lookup"><span data-stu-id="2ba02-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ba02-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ba02-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2ba02-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ba02-121">Element</span></span>|<span data-ttu-id="2ba02-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2ba02-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ba02-123">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="2ba02-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="2ba02-124">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="2ba02-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2ba02-125">Пример</span><span class="sxs-lookup"><span data-stu-id="2ba02-125">Example</span></span>  
 <span data-ttu-id="2ba02-126">Следующий XML-КОДЕ показано использование `<add>` и `<remove>` элементов для замены токенов обработчик сеанса по умолчанию обработчик маркеров пользовательского сеанса.</span><span class="sxs-lookup"><span data-stu-id="2ba02-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="2ba02-127">XML-код будет браться из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="2ba02-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
