---
title: '&lt;add&gt; для &lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 20e1052a0517bb170cf796dd40d58c298185a958
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="ced1a-102">&lt;add&gt; для &lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="ced1a-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="ced1a-103">Определяет учетную запись пользователя для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="ced1a-103">Specifies a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="ced1a-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="ced1a-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced1a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ced1a-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ced1a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ced1a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ced1a-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ced1a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ced1a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ced1a-108">Attributes</span></span>  
  
|<span data-ttu-id="ced1a-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ced1a-109">Attribute</span></span>|<span data-ttu-id="ced1a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ced1a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ced1a-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ced1a-111">securityIdentifier</span></span>|<span data-ttu-id="ced1a-112">Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="ced1a-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="ced1a-113">Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="ced1a-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ced1a-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ced1a-114">Child Elements</span></span>  
 <span data-ttu-id="ced1a-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ced1a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ced1a-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ced1a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ced1a-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ced1a-117">Element</span></span>|<span data-ttu-id="ced1a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ced1a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ced1a-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="ced1a-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="ced1a-120">Коллекция элементов конфигурации, которые содержат атрибут `securityIdentifier`, указывающий учетные записи пользователей для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="ced1a-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ced1a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="ced1a-121">Example</span></span>  
 <span data-ttu-id="ced1a-122">В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="ced1a-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ced1a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ced1a-123">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
