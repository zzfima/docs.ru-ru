---
title: "Соглашения о схеме конфигурации WIF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ad367a14373487698cd13c710998f1a5e6ccb7cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="wif-configuration-schema-conventions"></a><span data-ttu-id="a9902-102">Соглашения о схеме конфигурации WIF</span><span class="sxs-lookup"><span data-stu-id="a9902-102">WIF Configuration Schema Conventions</span></span>
<span data-ttu-id="a9902-103">В этом разделе описываются соглашения, используемые в разделах конфигурации Windows Identity Foundation (WIF), и некоторые общие компоненты и атрибуты, применяемые в разделах [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) и [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="a9902-103">This topic discusses conventions used throughout the Windows Identity Foundation (WIF) configuration topics and describes some common features and attributes used in the [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) and the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) sections.</span></span>  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a><span data-ttu-id="a9902-104">Режимы</span><span class="sxs-lookup"><span data-stu-id="a9902-104">Modes</span></span>  
 <span data-ttu-id="a9902-105">Многие элементы конфигурации WIF имеют атрибут `mode`.</span><span class="sxs-lookup"><span data-stu-id="a9902-105">Many of the WIF configuration elements have a `mode` attribute.</span></span> <span data-ttu-id="a9902-106">Как правило, он определяет то, какой класс применяется для выполнения определенного этапа обработки и какие элементы конфигурации могут использоваться как дочерние элементы текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="a9902-106">This attribute typically controls which class is used to do a particular part of the processing and which configuration elements are allowed as child elements of the current element.</span></span> <span data-ttu-id="a9902-107">Если элементы, содержащиеся в файле конфигурации, игнорируются из-за настроек режима, возникает ошибка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a9902-107">A configuration error will be raised if elements that are included in the configuration file are ignored because of the mode settings.</span></span>  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a><span data-ttu-id="a9902-108">Значения временного диапазона</span><span class="sxs-lookup"><span data-stu-id="a9902-108">Timespan Values</span></span>  
 <span data-ttu-id="a9902-109">Если в качестве типа атрибута используется <xref:System.TimeSpan>, допустимый формат см. в описании метода <xref:System.TimeSpan.Parse%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="a9902-109">Where <xref:System.TimeSpan> is used as the type of an attribute, see the <xref:System.TimeSpan.Parse%28System.String%29> method to see the allowed format.</span></span> <span data-ttu-id="a9902-110">Этот формат соответствует следующей спецификации.</span><span class="sxs-lookup"><span data-stu-id="a9902-110">This format conforms to the following specification.</span></span>  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 <span data-ttu-id="a9902-111">Например, "30", "30.00:00" и "30.00:00:00" означают 30 дней, а "00:05", "00:05:00", "0.00:05:00.00" означают 5 минут.</span><span class="sxs-lookup"><span data-stu-id="a9902-111">For example, "30", "30.00:00", "30.00:00:00" all mean 30 days; and "00:05", "00:05:00", "0.00:05:00.00" all mean 5 minutes.</span></span>  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a><span data-ttu-id="a9902-112">Ссылки на сертификаты</span><span class="sxs-lookup"><span data-stu-id="a9902-112">Certificate References</span></span>  
 <span data-ttu-id="a9902-113">Некоторые элементы принимают ссылки на сертификаты посредством элемента `<certificateReference>`.</span><span class="sxs-lookup"><span data-stu-id="a9902-113">Several elements take references to certificates using the `<certificateReference>` element.</span></span> <span data-ttu-id="a9902-114">При указании ссылки на сертификат доступны перечисленные ниже атрибуты.</span><span class="sxs-lookup"><span data-stu-id="a9902-114">When referencing a certificate, the following attributes are available.</span></span>  
  
|||  
|-|-|  
|`storeLocation`|<span data-ttu-id="a9902-115">Значение из перечисления <xref:System.Security.Cryptography.X509Certificates.StoreLocation>: `CurrentUser` или `CurrentMachine`.</span><span class="sxs-lookup"><span data-stu-id="a9902-115">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreLocation> enumeration: `CurrentUser` or `CurrentMachine`.</span></span>|  
|`storeName`|<span data-ttu-id="a9902-116">Значение из перечисления <xref:System.Security.Cryptography.X509Certificates.StoreName>. Наиболее полезными в этом контексте являются значения `My` и `TrustedPeople`.</span><span class="sxs-lookup"><span data-stu-id="a9902-116">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreName> enumeration; the most useful for this context are `My` and `TrustedPeople`.</span></span>|  
|`x509FindType`|<span data-ttu-id="a9902-117">Значение из перечисления <xref:System.Security.Cryptography.X509Certificates.X509FindType>. Наиболее полезными в этом контексте являются значения `FindBySubjectName` и `FindByThumbprint`.</span><span class="sxs-lookup"><span data-stu-id="a9902-117">A value of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> enumeration; the most useful for this context are `FindBySubjectName` and `FindByThumbprint`.</span></span> <span data-ttu-id="a9902-118">Чтобы избежать ошибок, в рабочих средах рекомендуется использовать тип `FindByThumbprint`.</span><span class="sxs-lookup"><span data-stu-id="a9902-118">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span>|  
|`findValue`|<span data-ttu-id="a9902-119">Значение, используемое для поиска сертификата, в соответствии с атрибутом `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="a9902-119">The value used to find the certificate, based on the `x509FindType` attribute.</span></span> <span data-ttu-id="a9902-120">Чтобы избежать ошибок, в рабочих средах рекомендуется использовать тип `FindByThumbprint`.</span><span class="sxs-lookup"><span data-stu-id="a9902-120">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span> <span data-ttu-id="a9902-121">Если задано значение `FindByThumbPrint`, этот атрибут принимает значение, которое представляет собой отпечаток сертификата в виде шестнадцатеричной строки, например 97249e1a5fa6bee5e515b82111ef524a4c91583f.</span><span class="sxs-lookup"><span data-stu-id="a9902-121">When `FindByThumbPrint` is specified, this attribute takes a value that is the hexadecimal-string form of the certificate thumbprint; for example, "97249e1a5fa6bee5e515b82111ef524a4c91583f".</span></span>|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a><span data-ttu-id="a9902-122">Ссылки на пользовательские типы</span><span class="sxs-lookup"><span data-stu-id="a9902-122">Custom Type References</span></span>  
 <span data-ttu-id="a9902-123">Некоторые элементы ссылаются на пользовательские типы посредством атрибута `type`.</span><span class="sxs-lookup"><span data-stu-id="a9902-123">Several elements reference custom types using the `type` attribute.</span></span> <span data-ttu-id="a9902-124">В этом атрибуте должно указываться имя пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="a9902-124">This attribute should specify the name of the custom type.</span></span> <span data-ttu-id="a9902-125">Для ссылки на тип из глобального кэша сборок (GAC) следует использовать строгое имя.</span><span class="sxs-lookup"><span data-stu-id="a9902-125">To reference a type from the Global Assembly Cache (GAC), a strong name should be used.</span></span> <span data-ttu-id="a9902-126">Для ссылки на тип из сборки в каталоге Bin/ можно использовать простое имя с указанием сборки.</span><span class="sxs-lookup"><span data-stu-id="a9902-126">To reference a type from an assembly in the Bin/ directory, a simple assembly-qualified reference may be used.</span></span> <span data-ttu-id="a9902-127">На типы, определенные в каталоге App_Code/, можно также ссылаться просто по имени типа без указания сборки.</span><span class="sxs-lookup"><span data-stu-id="a9902-127">Types defined in the App_Code/ directory may also be referenced by simply specifying the type name with no qualifying assembly.</span></span>  
  
 <span data-ttu-id="a9902-128">Пользовательские типы должны быть производными от указанного типа и предоставлять конструктор `public` по умолчанию (аргумент 0).</span><span class="sxs-lookup"><span data-stu-id="a9902-128">Custom types must be derived from the type specified and they must provide a `public` default (0 argument) constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9902-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a9902-129">See Also</span></span>  
 [<span data-ttu-id="a9902-130">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a9902-130">\<system.identityModel></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)  
 [<span data-ttu-id="a9902-131">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="a9902-131">\<system.identityModel.services></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
