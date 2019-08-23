---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 32aad3529ded6d0234b1bcb388ecbbc3b0a11c87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944275"
---
# <a name="trustedissuers"></a><span data-ttu-id="8a321-101">\<Трустедиссуерс ></span><span class="sxs-lookup"><span data-stu-id="8a321-101">\<trustedIssuers></span></span>
<span data-ttu-id="8a321-102">Настраивает список сертификатов доверенных издателей, используемых в реестре имен поставщиков на основе конфигурации<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>().</span><span class="sxs-lookup"><span data-stu-id="8a321-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="8a321-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="8a321-103">\<system.identityModel></span></span>  
<span data-ttu-id="8a321-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8a321-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8a321-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="8a321-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8a321-106">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="8a321-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="8a321-107">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="8a321-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="8a321-108">\<Трустедиссуерс ></span><span class="sxs-lookup"><span data-stu-id="8a321-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a321-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a321-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a321-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a321-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8a321-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8a321-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a321-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a321-112">Attributes</span></span>  
 <span data-ttu-id="8a321-113">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="8a321-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8a321-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a321-114">Child Elements</span></span>  
  
|<span data-ttu-id="8a321-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a321-115">Element</span></span>|<span data-ttu-id="8a321-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8a321-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="8a321-117">Добавляет сертификат в коллекцию доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="8a321-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="8a321-118">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="8a321-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="8a321-119">Этот атрибут является обязательным и должен содержать форму отпечатка сертификата в кодировке ASN. 1.</span><span class="sxs-lookup"><span data-stu-id="8a321-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="8a321-120">`name` Атрибут является необязательным и может использоваться для указания понятного имени сертификата.</span><span class="sxs-lookup"><span data-stu-id="8a321-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="8a321-121">Удаляет все сертификаты из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="8a321-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="8a321-122">Удаляет сертификат из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="8a321-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="8a321-123">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="8a321-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="8a321-124">Атрибут обязателен.</span><span class="sxs-lookup"><span data-stu-id="8a321-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a321-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a321-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8a321-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a321-126">Element</span></span>|<span data-ttu-id="8a321-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8a321-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a321-128">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="8a321-128">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="8a321-129">Настраивает реестр имен издателя.</span><span class="sxs-lookup"><span data-stu-id="8a321-129">Configures the issuer name registry.</span></span> <span data-ttu-id="8a321-130">**Важно!**  Атрибут элемента должен ссылаться на класс, чтобы элемент был допустимым. `<trustedIssuers>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `type` `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="8a321-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a321-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a321-131">Remarks</span></span>  
 <span data-ttu-id="8a321-132">Windows Identity Foundation (WIF) предоставляет единую реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса из Box <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> , класса.</span><span class="sxs-lookup"><span data-stu-id="8a321-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="8a321-133">В реестре имени издателя конфигурации хранится список доверенных издателей, которые загружаются из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8a321-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="8a321-134">Список всех имен издателей связывается с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных издателем.</span><span class="sxs-lookup"><span data-stu-id="8a321-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="8a321-135">Список сертификатов доверенных издателей указывается в `<trustedIssuers>` элементе.</span><span class="sxs-lookup"><span data-stu-id="8a321-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="8a321-136">Каждый элемент в списке связывает назначенное имя издателя с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных этим издателем.</span><span class="sxs-lookup"><span data-stu-id="8a321-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="8a321-137">Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1 и добавляются в коллекцию `<add>` с помощью элемента.</span><span class="sxs-lookup"><span data-stu-id="8a321-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="8a321-138">Можно удалить или удалить издателей (сертификаты) из списка с помощью `<clear>` элементов и. `<remove>`</span><span class="sxs-lookup"><span data-stu-id="8a321-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="8a321-139">Атрибут элемента должен ссылаться на класс, чтобы элемент был допустимым. `<trustedIssuers>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `type` `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="8a321-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a321-140">Пример</span><span class="sxs-lookup"><span data-stu-id="8a321-140">Example</span></span>  
 <span data-ttu-id="8a321-141">В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8a321-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a321-142">См. также</span><span class="sxs-lookup"><span data-stu-id="8a321-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
