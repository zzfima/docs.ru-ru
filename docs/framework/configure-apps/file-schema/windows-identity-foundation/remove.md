---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: a54957458311e2d5941d1aa1c2486a2f66994d9b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288136"
---
# <a name="remove"></a><span data-ttu-id="808dd-101">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="808dd-101">\<remove></span></span>
<span data-ttu-id="808dd-102">Удаляет обработчик токенов безопасности из коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="808dd-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="808dd-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="808dd-103">\<system.identityModel></span></span>  
<span data-ttu-id="808dd-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="808dd-104">\<identityConfiguration></span></span>  
<span data-ttu-id="808dd-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="808dd-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="808dd-106">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="808dd-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="808dd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="808dd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="808dd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="808dd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="808dd-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="808dd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="808dd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="808dd-110">Attributes</span></span>  
  
|<span data-ttu-id="808dd-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="808dd-111">Attribute</span></span>|<span data-ttu-id="808dd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="808dd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="808dd-113">type</span><span class="sxs-lookup"><span data-stu-id="808dd-113">type</span></span>|<span data-ttu-id="808dd-114">Имя типа CLR обработчик токенов для удаления.</span><span class="sxs-lookup"><span data-stu-id="808dd-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="808dd-115">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="808dd-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="808dd-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="808dd-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="808dd-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="808dd-117">Child Elements</span></span>  
 <span data-ttu-id="808dd-118">Нет</span><span class="sxs-lookup"><span data-stu-id="808dd-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="808dd-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="808dd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="808dd-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="808dd-120">Element</span></span>|<span data-ttu-id="808dd-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="808dd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="808dd-122">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="808dd-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="808dd-123">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="808dd-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="808dd-124">Пример</span><span class="sxs-lookup"><span data-stu-id="808dd-124">Example</span></span>  
 <span data-ttu-id="808dd-125">Следующий код XML показывает использование `<add>` и `<remove>` элементов для замены маркера обработчик сеанса по умолчанию обработчик токенов пользовательского сеанса.</span><span class="sxs-lookup"><span data-stu-id="808dd-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="808dd-126">XML-код взят из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="808dd-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
