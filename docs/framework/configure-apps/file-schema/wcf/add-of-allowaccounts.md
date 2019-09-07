---
title: <add> из <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398379"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="b0e56-102">\<Добавление > \<> алловаккаунтс</span><span class="sxs-lookup"><span data-stu-id="b0e56-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="b0e56-103">Указывает учетную запись пользователя для процессов, на которых размещаются службы WCF, и им предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="b0e56-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="b0e56-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0e56-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b0e56-105">&nbsp;&nbsp;[ **\<> System. serviceModel. Activation**](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="b0e56-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="b0e56-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> NET. pipe**](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="b0e56-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="b0e56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Алловаккаунтс >** ](allowaccounts.md)</span><span class="sxs-lookup"><span data-stu-id="b0e56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)</span></span>\
<span data-ttu-id="b0e56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="b0e56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e56-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0e56-109">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0e56-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b0e56-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0e56-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b0e56-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0e56-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b0e56-112">Attributes</span></span>  
  
|<span data-ttu-id="b0e56-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b0e56-113">Attribute</span></span>|<span data-ttu-id="b0e56-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b0e56-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0e56-115">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b0e56-115">securityIdentifier</span></span>|<span data-ttu-id="b0e56-116">Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0e56-116">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="b0e56-117">Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="b0e56-117">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0e56-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b0e56-118">Child Elements</span></span>  
 <span data-ttu-id="b0e56-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="b0e56-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0e56-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b0e56-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b0e56-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b0e56-121">Element</span></span>|<span data-ttu-id="b0e56-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b0e56-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0e56-123">\<Алловаккаунтс ></span><span class="sxs-lookup"><span data-stu-id="b0e56-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="b0e56-124">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="b0e56-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b0e56-125">Пример</span><span class="sxs-lookup"><span data-stu-id="b0e56-125">Example</span></span>  
 <span data-ttu-id="b0e56-126">В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0e56-126">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0e56-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b0e56-127">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
