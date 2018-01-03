---
title: '&lt;serviceCertificate&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 1373d1e95a0e569f5e5cf433d305d008b4daf838
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="2b6d3-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="2b6d3-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="2b6d3-103">Настраивает сертификат X.509, используемый для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="2b6d3-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="2b6d3-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="2b6d3-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="2b6d3-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2b6d3-105">\<federationConfiguration></span></span>  
<span data-ttu-id="2b6d3-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="2b6d3-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b6d3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b6d3-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b6d3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2b6d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2b6d3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2b6d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b6d3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b6d3-110">Attributes</span></span>  
 <span data-ttu-id="2b6d3-111">Нет</span><span class="sxs-lookup"><span data-stu-id="2b6d3-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b6d3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b6d3-112">Child Elements</span></span>  
  
|<span data-ttu-id="2b6d3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b6d3-113">Element</span></span>|<span data-ttu-id="2b6d3-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="2b6d3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b6d3-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="2b6d3-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="2b6d3-116">Указывает параметры, используемые для поиска и проверки сертификатов в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="2b6d3-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b6d3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2b6d3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2b6d3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b6d3-118">Element</span></span>|<span data-ttu-id="2b6d3-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="2b6d3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b6d3-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="2b6d3-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="2b6d3-121">Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="2b6d3-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b6d3-122">Пример</span><span class="sxs-lookup"><span data-stu-id="2b6d3-122">Example</span></span>  
 <span data-ttu-id="2b6d3-123">Следующий XML-КОДЕ показано использование \<serviceCertificate > элемента.</span><span class="sxs-lookup"><span data-stu-id="2b6d3-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="2b6d3-124">XML-код будет браться из `CustomToken` образца.</span><span class="sxs-lookup"><span data-stu-id="2b6d3-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
