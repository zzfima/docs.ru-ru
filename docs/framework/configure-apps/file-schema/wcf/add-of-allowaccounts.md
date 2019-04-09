---
title: <add> из <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1c6764b37b2aa5349b8ccf63e6b7c2bc580b69b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186606"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="82a22-102">\<Добавить > из \<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="82a22-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="82a22-103">Указывает учетную запись пользователя для процессов размещения служб WCF, которые предоставляются доступ при подключении к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="82a22-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="82a22-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="82a22-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a22-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82a22-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82a22-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82a22-106">Attributes and Elements</span></span>  
 <span data-ttu-id="82a22-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82a22-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82a22-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82a22-108">Attributes</span></span>  
  
|<span data-ttu-id="82a22-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="82a22-109">Attribute</span></span>|<span data-ttu-id="82a22-110">Описание</span><span class="sxs-lookup"><span data-stu-id="82a22-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82a22-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="82a22-111">securityIdentifier</span></span>|<span data-ttu-id="82a22-112">Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="82a22-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="82a22-113">Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="82a22-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82a22-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82a22-114">Child Elements</span></span>  
 <span data-ttu-id="82a22-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="82a22-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82a22-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82a22-116">Parent Elements</span></span>  
  
|<span data-ttu-id="82a22-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="82a22-117">Element</span></span>|<span data-ttu-id="82a22-118">Описание</span><span class="sxs-lookup"><span data-stu-id="82a22-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82a22-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="82a22-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="82a22-120">Коллекция элементов конфигурации, которые содержат `securityIdentifier` атрибут для указания учетных записей пользователей для процессов размещения служб WCF, которые предоставляются доступ при подключении к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="82a22-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="82a22-121">Пример</span><span class="sxs-lookup"><span data-stu-id="82a22-121">Example</span></span>  
 <span data-ttu-id="82a22-122">В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="82a22-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82a22-123">См. также</span><span class="sxs-lookup"><span data-stu-id="82a22-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
