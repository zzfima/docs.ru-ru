---
title: <add> из <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1ed0b5025ab969c45d7440f2a209426c5c87f549
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920279"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="23ce2-102">\<Добавление > \<> алловаккаунтс</span><span class="sxs-lookup"><span data-stu-id="23ce2-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="23ce2-103">Указывает учетную запись пользователя для процессов, на которых размещаются службы WCF, и им предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="23ce2-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="23ce2-104">\<> System. serviceModel. Activation</span><span class="sxs-lookup"><span data-stu-id="23ce2-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23ce2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23ce2-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23ce2-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="23ce2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="23ce2-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="23ce2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23ce2-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="23ce2-108">Attributes</span></span>  
  
|<span data-ttu-id="23ce2-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="23ce2-109">Attribute</span></span>|<span data-ttu-id="23ce2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="23ce2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23ce2-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="23ce2-111">securityIdentifier</span></span>|<span data-ttu-id="23ce2-112">Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="23ce2-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="23ce2-113">Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="23ce2-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23ce2-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="23ce2-114">Child Elements</span></span>  
 <span data-ttu-id="23ce2-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="23ce2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23ce2-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="23ce2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="23ce2-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="23ce2-117">Element</span></span>|<span data-ttu-id="23ce2-118">Описание</span><span class="sxs-lookup"><span data-stu-id="23ce2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23ce2-119">\<Алловаккаунтс ></span><span class="sxs-lookup"><span data-stu-id="23ce2-119">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="23ce2-120">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="23ce2-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23ce2-121">Пример</span><span class="sxs-lookup"><span data-stu-id="23ce2-121">Example</span></span>  
 <span data-ttu-id="23ce2-122">В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="23ce2-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23ce2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="23ce2-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
