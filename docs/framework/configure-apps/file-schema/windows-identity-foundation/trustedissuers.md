---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251759"
---
# <a name="trustedissuers"></a><span data-ttu-id="61324-101">\<Трустедиссуерс ></span><span class="sxs-lookup"><span data-stu-id="61324-101">\<trustedIssuers></span></span>
<span data-ttu-id="61324-102">Настраивает список сертификатов доверенных издателей, используемых в реестре имен поставщиков на основе конфигурации<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>().</span><span class="sxs-lookup"><span data-stu-id="61324-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
<span data-ttu-id="61324-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="61324-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="61324-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="61324-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="61324-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="61324-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="61324-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="61324-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="61324-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="61324-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="61324-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerNameRegistry >** ](issuernameregistry.md)</span><span class="sxs-lookup"><span data-stu-id="61324-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)</span></span>\
<span data-ttu-id="61324-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Трустедиссуерс >**</span><span class="sxs-lookup"><span data-stu-id="61324-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61324-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61324-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61324-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="61324-111">Attributes and Elements</span></span>  
 <span data-ttu-id="61324-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="61324-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61324-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="61324-113">Attributes</span></span>  
 <span data-ttu-id="61324-114">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="61324-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61324-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="61324-115">Child Elements</span></span>  
  
|<span data-ttu-id="61324-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="61324-116">Element</span></span>|<span data-ttu-id="61324-117">Описание</span><span class="sxs-lookup"><span data-stu-id="61324-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="61324-118">Добавляет сертификат в коллекцию доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="61324-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="61324-119">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="61324-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="61324-120">Этот атрибут является обязательным и должен содержать форму отпечатка сертификата в кодировке ASN. 1.</span><span class="sxs-lookup"><span data-stu-id="61324-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="61324-121">`name` Атрибут является необязательным и может использоваться для указания понятного имени сертификата.</span><span class="sxs-lookup"><span data-stu-id="61324-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="61324-122">Удаляет все сертификаты из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="61324-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="61324-123">Удаляет сертификат из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="61324-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="61324-124">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="61324-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="61324-125">Атрибут обязателен.</span><span class="sxs-lookup"><span data-stu-id="61324-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61324-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="61324-126">Parent Elements</span></span>  
  
|<span data-ttu-id="61324-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="61324-127">Element</span></span>|<span data-ttu-id="61324-128">Описание</span><span class="sxs-lookup"><span data-stu-id="61324-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61324-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="61324-129">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="61324-130">Настраивает реестр имен издателя.</span><span class="sxs-lookup"><span data-stu-id="61324-130">Configures the issuer name registry.</span></span> <span data-ttu-id="61324-131">**Важно!**  Атрибут элемента должен ссылаться на класс, чтобы элемент был допустимым. `<trustedIssuers>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `type` `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="61324-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61324-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="61324-132">Remarks</span></span>  
 <span data-ttu-id="61324-133">Windows Identity Foundation (WIF) предоставляет единую реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса из Box <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> , класса.</span><span class="sxs-lookup"><span data-stu-id="61324-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="61324-134">В реестре имени издателя конфигурации хранится список доверенных издателей, которые загружаются из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61324-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="61324-135">Список всех имен издателей связывается с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных издателем.</span><span class="sxs-lookup"><span data-stu-id="61324-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="61324-136">Список сертификатов доверенных издателей указывается в `<trustedIssuers>` элементе.</span><span class="sxs-lookup"><span data-stu-id="61324-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="61324-137">Каждый элемент в списке связывает назначенное имя издателя с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных этим издателем.</span><span class="sxs-lookup"><span data-stu-id="61324-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="61324-138">Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1 и добавляются в коллекцию `<add>` с помощью элемента.</span><span class="sxs-lookup"><span data-stu-id="61324-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="61324-139">Можно удалить или удалить издателей (сертификаты) из списка с помощью `<clear>` элементов и. `<remove>`</span><span class="sxs-lookup"><span data-stu-id="61324-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="61324-140">Атрибут элемента должен ссылаться на класс, чтобы элемент был допустимым. `<trustedIssuers>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `type` `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="61324-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61324-141">Пример</span><span class="sxs-lookup"><span data-stu-id="61324-141">Example</span></span>  
 <span data-ttu-id="61324-142">В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61324-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61324-143">См. также</span><span class="sxs-lookup"><span data-stu-id="61324-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
