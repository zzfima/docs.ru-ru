---
title: '&lt;add&gt; для &lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 63f8e678b81838a25664180888e9e7a8eabd043d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722020"
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="caaca-102">&lt;add&gt; для &lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="caaca-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="caaca-103">Указывает учетную запись пользователя для процессов размещения служб WCF, которые предоставляются доступ при подключении к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="caaca-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="caaca-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="caaca-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caaca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caaca-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caaca-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="caaca-106">Attributes and Elements</span></span>  
 <span data-ttu-id="caaca-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="caaca-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caaca-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="caaca-108">Attributes</span></span>  
  
|<span data-ttu-id="caaca-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="caaca-109">Attribute</span></span>|<span data-ttu-id="caaca-110">Описание</span><span class="sxs-lookup"><span data-stu-id="caaca-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="caaca-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="caaca-111">securityIdentifier</span></span>|<span data-ttu-id="caaca-112">Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="caaca-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="caaca-113">Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="caaca-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="caaca-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="caaca-114">Child Elements</span></span>  
 <span data-ttu-id="caaca-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="caaca-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="caaca-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="caaca-116">Parent Elements</span></span>  
  
|<span data-ttu-id="caaca-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="caaca-117">Element</span></span>|<span data-ttu-id="caaca-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="caaca-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caaca-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="caaca-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="caaca-120">Коллекция элементов конфигурации, которые содержат `securityIdentifier` атрибут для указания учетных записей пользователей для процессов размещения служб WCF, которые предоставляются доступ при подключении к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="caaca-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="caaca-121">Пример</span><span class="sxs-lookup"><span data-stu-id="caaca-121">Example</span></span>  
 <span data-ttu-id="caaca-122">В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="caaca-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="caaca-123">См. также</span><span class="sxs-lookup"><span data-stu-id="caaca-123">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
