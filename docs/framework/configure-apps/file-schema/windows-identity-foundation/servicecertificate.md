---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 008d2269a72759117658e27ec130cc8cf62cfdfa
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47400417"
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="ffb81-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="ffb81-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="ffb81-103">Настраивает сертификат X.509, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="ffb81-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="ffb81-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="ffb81-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="ffb81-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ffb81-105">\<federationConfiguration></span></span>  
<span data-ttu-id="ffb81-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="ffb81-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb81-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffb81-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffb81-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ffb81-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ffb81-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ffb81-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffb81-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ffb81-110">Attributes</span></span>  
 <span data-ttu-id="ffb81-111">Нет</span><span class="sxs-lookup"><span data-stu-id="ffb81-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ffb81-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ffb81-112">Child Elements</span></span>  
  
|<span data-ttu-id="ffb81-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ffb81-113">Element</span></span>|<span data-ttu-id="ffb81-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ffb81-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffb81-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="ffb81-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="ffb81-116">Задает параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ffb81-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ffb81-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ffb81-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ffb81-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ffb81-118">Element</span></span>|<span data-ttu-id="ffb81-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ffb81-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffb81-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="ffb81-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="ffb81-121">Содержит параметры, определяющие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="ffb81-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ffb81-122">Пример</span><span class="sxs-lookup"><span data-stu-id="ffb81-122">Example</span></span>  
 <span data-ttu-id="ffb81-123">Следующий код XML показывает использование \<serviceCertificate > элемента.</span><span class="sxs-lookup"><span data-stu-id="ffb81-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="ffb81-124">XML-код взят из `CustomToken` образца.</span><span class="sxs-lookup"><span data-stu-id="ffb81-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
