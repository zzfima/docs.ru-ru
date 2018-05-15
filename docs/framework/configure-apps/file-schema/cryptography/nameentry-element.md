---
title: '&lt;nameEntry&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1bffb72e7c68d10e2c0edd5ec3cb9bcff10cbc0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltnameentrygt-element"></a><span data-ttu-id="18c9d-102">&lt;nameEntry&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="18c9d-102">&lt;nameEntry&gt; Element</span></span>
<span data-ttu-id="18c9d-103">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="18c9d-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="18c9d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="18c9d-104">\<configuration></span></span>  
<span data-ttu-id="18c9d-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="18c9d-105">\<mscorlib></span></span>  
<span data-ttu-id="18c9d-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="18c9d-106">\<cryptographySettings></span></span>  
<span data-ttu-id="18c9d-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="18c9d-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="18c9d-108">\<nameEntry ></span><span class="sxs-lookup"><span data-stu-id="18c9d-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c9d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18c9d-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18c9d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18c9d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="18c9d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18c9d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18c9d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18c9d-112">Attributes</span></span>  
  
|<span data-ttu-id="18c9d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18c9d-113">Attribute</span></span>|<span data-ttu-id="18c9d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="18c9d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18c9d-115">**name**</span><span class="sxs-lookup"><span data-stu-id="18c9d-115">**name**</span></span>|<span data-ttu-id="18c9d-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="18c9d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="18c9d-117">Указывает понятное имя для алгоритма, который реализует криптографический класс.</span><span class="sxs-lookup"><span data-stu-id="18c9d-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="18c9d-118">**class**</span><span class="sxs-lookup"><span data-stu-id="18c9d-118">**class**</span></span>|<span data-ttu-id="18c9d-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="18c9d-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="18c9d-120">Указывает значение для **имя** атрибута в [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="18c9d-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18c9d-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18c9d-121">Child Elements</span></span>  
 <span data-ttu-id="18c9d-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="18c9d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18c9d-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18c9d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="18c9d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="18c9d-124">Element</span></span>|<span data-ttu-id="18c9d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="18c9d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="18c9d-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18c9d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="18c9d-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="18c9d-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18c9d-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="18c9d-128">Remarks</span></span>  
 <span data-ttu-id="18c9d-129">**Имя** атрибут может быть имя абстрактные классы, находящиеся в <xref:System.Security.Cryptography> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="18c9d-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="18c9d-130">При вызове **создать** метода криптографии абстрактного класса, абстрактный класс имя передается <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="18c9d-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="18c9d-131">**CreateFromName** возвращает экземпляр типа, указанного **класса** атрибута.</span><span class="sxs-lookup"><span data-stu-id="18c9d-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="18c9d-132">Если **имя** атрибут — это краткое имя, например RSA, можно использовать это имя при вызове **CreateFromName** метод.</span><span class="sxs-lookup"><span data-stu-id="18c9d-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18c9d-133">Пример</span><span class="sxs-lookup"><span data-stu-id="18c9d-133">Example</span></span>  
 <span data-ttu-id="18c9d-134">В следующем примере показано, как использовать  **\<nameEntry >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="18c9d-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="18c9d-135">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="18c9d-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18c9d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="18c9d-136">See Also</span></span>  
 [<span data-ttu-id="18c9d-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="18c9d-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="18c9d-138">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="18c9d-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="18c9d-139">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="18c9d-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="18c9d-140">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="18c9d-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
