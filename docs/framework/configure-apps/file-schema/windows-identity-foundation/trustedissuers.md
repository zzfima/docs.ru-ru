---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790485"
---
# <a name="trustedissuers"></a><span data-ttu-id="8077f-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="8077f-101">\<trustedIssuers></span></span>
<span data-ttu-id="8077f-102">Настраивает список доверенных издателей сертификатов, используемых реестр имен издателей на основе конфигурации (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="8077f-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="8077f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8077f-103">\<system.identityModel></span></span>  
<span data-ttu-id="8077f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8077f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8077f-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="8077f-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8077f-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="8077f-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="8077f-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="8077f-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="8077f-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="8077f-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8077f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8077f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8077f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8077f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8077f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8077f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8077f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8077f-112">Attributes</span></span>  
 <span data-ttu-id="8077f-113">Нет</span><span class="sxs-lookup"><span data-stu-id="8077f-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8077f-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8077f-114">Child Elements</span></span>  
  
|<span data-ttu-id="8077f-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="8077f-115">Element</span></span>|<span data-ttu-id="8077f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8077f-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="8077f-117">Добавляет сертификат в коллекцию доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="8077f-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="8077f-118">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="8077f-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="8077f-119">Этот атрибут является обязательным и должен содержать формы в кодировке ASN.1 отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="8077f-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="8077f-120">`name` Атрибут является необязательным и может использоваться для указания понятное имя для сертификата.</span><span class="sxs-lookup"><span data-stu-id="8077f-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="8077f-121">Очищает все сертификаты из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="8077f-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="8077f-122">Удаляет сертификат из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="8077f-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="8077f-123">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="8077f-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="8077f-124">Атрибут обязателен.</span><span class="sxs-lookup"><span data-stu-id="8077f-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8077f-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8077f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8077f-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8077f-126">Element</span></span>|<span data-ttu-id="8077f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8077f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8077f-128">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="8077f-128">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="8077f-129">Настраивает реестр имен издателей.</span><span class="sxs-lookup"><span data-stu-id="8077f-129">Configures the issuer name registry.</span></span> <span data-ttu-id="8077f-130">**Внимание!**  `type` Атрибут `<issuerNameRegistry>` должен ссылаться элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.</span><span class="sxs-lookup"><span data-stu-id="8077f-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8077f-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="8077f-131">Remarks</span></span>  
 <span data-ttu-id="8077f-132">Windows Identity Foundation (WIF) обеспечивает единую реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класс по умолчанию, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="8077f-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="8077f-133">Конфигурация реестр имен издателей ведет список доверенных издателей, загруженный из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8077f-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="8077f-134">Список связывает каждое имя издателя с сертификатом X.509, который необходим для проверки подписи токенов, создаваемых издателем.</span><span class="sxs-lookup"><span data-stu-id="8077f-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="8077f-135">Список доверенных издателей сертификатов, указанные в разделе `<trustedIssuers>` элемент.</span><span class="sxs-lookup"><span data-stu-id="8077f-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="8077f-136">Каждый элемент в списке связывает имя мнемонический издателя с сертификатом X.509, который необходим для проверки подписи токенов, создаваемых этим издателем.</span><span class="sxs-lookup"><span data-stu-id="8077f-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="8077f-137">Доверенные сертификаты указываются с помощью ASN.1 кодированной формы отпечатка сертификата и добавляются к коллекции с помощью `<add>` элемент.</span><span class="sxs-lookup"><span data-stu-id="8077f-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="8077f-138">Вы можете удалить или удалить из списка издателей (сертификаты), с помощью `<clear>` и `<remove>` элементы.</span><span class="sxs-lookup"><span data-stu-id="8077f-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="8077f-139">`type` Атрибут `<issuerNameRegistry>` должен ссылаться элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.</span><span class="sxs-lookup"><span data-stu-id="8077f-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8077f-140">Пример</span><span class="sxs-lookup"><span data-stu-id="8077f-140">Example</span></span>  
 <span data-ttu-id="8077f-141">Следующий код XML показано, как указать поставщика конфигурации на основе реестра имен.</span><span class="sxs-lookup"><span data-stu-id="8077f-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8077f-142">См. также</span><span class="sxs-lookup"><span data-stu-id="8077f-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
