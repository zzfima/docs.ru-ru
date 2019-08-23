---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 11aeed0277fc13cbd9a65232311bd575a4a81ff7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942585"
---
# <a name="remove"></a><span data-ttu-id="acb3d-101">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="acb3d-101">\<remove></span></span>
<span data-ttu-id="acb3d-102">Удаляет указанный обработчик маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="acb3d-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="acb3d-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="acb3d-103">\<system.identityModel></span></span>  
<span data-ttu-id="acb3d-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="acb3d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="acb3d-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="acb3d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="acb3d-106">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="acb3d-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb3d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acb3d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acb3d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="acb3d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="acb3d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="acb3d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acb3d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="acb3d-110">Attributes</span></span>  
  
|<span data-ttu-id="acb3d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="acb3d-111">Attribute</span></span>|<span data-ttu-id="acb3d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="acb3d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acb3d-113">type</span><span class="sxs-lookup"><span data-stu-id="acb3d-113">type</span></span>|<span data-ttu-id="acb3d-114">Имя типа CLR удаляемого обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="acb3d-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="acb3d-115">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="acb3d-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="acb3d-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="acb3d-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acb3d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="acb3d-117">Child Elements</span></span>  
 <span data-ttu-id="acb3d-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="acb3d-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acb3d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="acb3d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="acb3d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="acb3d-120">Element</span></span>|<span data-ttu-id="acb3d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="acb3d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acb3d-122">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="acb3d-122">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="acb3d-123">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="acb3d-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="acb3d-124">Пример</span><span class="sxs-lookup"><span data-stu-id="acb3d-124">Example</span></span>  
 <span data-ttu-id="acb3d-125">В следующем коде XML показано использование `<add>` элементов и `<remove>` для замены обработчика токена сеанса по умолчанию обработчиком пользовательского маркера сеанса.</span><span class="sxs-lookup"><span data-stu-id="acb3d-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="acb3d-126">XML взят из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="acb3d-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
