---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 33ef3ca88462595d81d269a92a643b43c9aea025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="109a9-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="109a9-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="109a9-103">Настраивает список доверенных издателей сертификатов, используемых реестр имен издателей на основе конфигурации (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="109a9-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="109a9-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="109a9-104">\<system.identityModel></span></span>  
<span data-ttu-id="109a9-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="109a9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="109a9-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="109a9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="109a9-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="109a9-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="109a9-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="109a9-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="109a9-109">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="109a9-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109a9-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="109a9-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="109a9-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="109a9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="109a9-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="109a9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="109a9-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="109a9-113">Attributes</span></span>  
 <span data-ttu-id="109a9-114">Нет</span><span class="sxs-lookup"><span data-stu-id="109a9-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="109a9-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="109a9-115">Child Elements</span></span>  
  
|<span data-ttu-id="109a9-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="109a9-116">Element</span></span>|<span data-ttu-id="109a9-117">Описание</span><span class="sxs-lookup"><span data-stu-id="109a9-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="109a9-118">Добавляет сертификат в коллекцию доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="109a9-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="109a9-119">Сертификат указан с `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="109a9-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="109a9-120">Этот атрибут является обязательным и должен содержать отпечаток сертификата в кодировке ASN.1 формы.</span><span class="sxs-lookup"><span data-stu-id="109a9-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="109a9-121">`name` Атрибут является необязательным и может использоваться для указания понятное имя для сертификата.</span><span class="sxs-lookup"><span data-stu-id="109a9-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="109a9-122">Очищает все сертификаты из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="109a9-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="109a9-123">Удаляет сертификат из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="109a9-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="109a9-124">Сертификат указан с `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="109a9-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="109a9-125">Атрибут обязателен.</span><span class="sxs-lookup"><span data-stu-id="109a9-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="109a9-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="109a9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="109a9-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="109a9-127">Element</span></span>|<span data-ttu-id="109a9-128">Описание</span><span class="sxs-lookup"><span data-stu-id="109a9-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="109a9-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="109a9-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="109a9-130">Настраивает реестр имен поставщиков.</span><span class="sxs-lookup"><span data-stu-id="109a9-130">Configures the issuer name registry.</span></span> <span data-ttu-id="109a9-131">**Важно:** `type` атрибут `<issuerNameRegistry>` должен ссылаться на элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.</span><span class="sxs-lookup"><span data-stu-id="109a9-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="109a9-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="109a9-132">Remarks</span></span>  
 <span data-ttu-id="109a9-133">Windows Identity Foundation (WIF) предоставляет одну реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класс готовые <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="109a9-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="109a9-134">В системном реестре имя издателя ведет список доверенных издателей, загруженная из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="109a9-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="109a9-135">Список связывает имя каждого издателя с сертификатом X.509, который необходим для проверки подписи токенов, полученных поставщиком.</span><span class="sxs-lookup"><span data-stu-id="109a9-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="109a9-136">Список доверенных издателей сертификатов, указанные в разделе `<trustedIssuers>` элемента.</span><span class="sxs-lookup"><span data-stu-id="109a9-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="109a9-137">Каждый элемент в списке связывает имя издателя, назначенный с сертификатом X.509, который необходим для проверки подписи токенов, созданных этим издателем.</span><span class="sxs-lookup"><span data-stu-id="109a9-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="109a9-138">Доверенных сертификатов задаются с помощью ASN.1 кодированной формы отпечатка сертификата и добавляются к коллекции с помощью `<add>` элемента.</span><span class="sxs-lookup"><span data-stu-id="109a9-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="109a9-139">Вы можете удалить или удалить из списка издателей (сертификатов), с помощью `<clear>` и `<remove>` элементы.</span><span class="sxs-lookup"><span data-stu-id="109a9-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="109a9-140">`type` Атрибут `<issuerNameRegistry>` должен ссылаться на элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.</span><span class="sxs-lookup"><span data-stu-id="109a9-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="109a9-141">Пример</span><span class="sxs-lookup"><span data-stu-id="109a9-141">Example</span></span>  
 <span data-ttu-id="109a9-142">Следующий код XML показано, как указать поставщика конфигурации на основе реестра имя.</span><span class="sxs-lookup"><span data-stu-id="109a9-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="109a9-143">См. также</span><span class="sxs-lookup"><span data-stu-id="109a9-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
