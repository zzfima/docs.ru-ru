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
ms.openlocfilehash: 9f8176ca3ee2340100978aef044140dafdeb179b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082374"
---
# <a name="ltnameentrygt-element"></a><span data-ttu-id="e08b1-102">&lt;nameEntry&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="e08b1-102">&lt;nameEntry&gt; Element</span></span>
<span data-ttu-id="e08b1-103">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="e08b1-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="e08b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e08b1-104">\<configuration></span></span>  
<span data-ttu-id="e08b1-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="e08b1-105">\<mscorlib></span></span>  
<span data-ttu-id="e08b1-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="e08b1-106">\<cryptographySettings></span></span>  
<span data-ttu-id="e08b1-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="e08b1-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="e08b1-108">\<nameEntry ></span><span class="sxs-lookup"><span data-stu-id="e08b1-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08b1-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e08b1-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e08b1-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e08b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e08b1-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e08b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e08b1-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e08b1-112">Attributes</span></span>  
  
|<span data-ttu-id="e08b1-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e08b1-113">Attribute</span></span>|<span data-ttu-id="e08b1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e08b1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e08b1-115">**name**</span><span class="sxs-lookup"><span data-stu-id="e08b1-115">**name**</span></span>|<span data-ttu-id="e08b1-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e08b1-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e08b1-117">Указывает понятное имя алгоритма, который реализует криптографический класс.</span><span class="sxs-lookup"><span data-stu-id="e08b1-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="e08b1-118">**class**</span><span class="sxs-lookup"><span data-stu-id="e08b1-118">**class**</span></span>|<span data-ttu-id="e08b1-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e08b1-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="e08b1-120">Указывает значение для **имя** атрибут в [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="e08b1-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e08b1-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e08b1-121">Child Elements</span></span>  
 <span data-ttu-id="e08b1-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e08b1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e08b1-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e08b1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e08b1-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e08b1-124">Element</span></span>|<span data-ttu-id="e08b1-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e08b1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e08b1-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e08b1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="e08b1-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e08b1-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e08b1-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e08b1-128">Remarks</span></span>  
 <span data-ttu-id="e08b1-129">**Имя** атрибут может быть имя одного из абстрактных классов <xref:System.Security.Cryptography> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e08b1-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="e08b1-130">При вызове **создать** метода класса абстрактный криптографии, передается имя абстрактного класса <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e08b1-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="e08b1-131">**CreateFromName** возвращает экземпляр типа, указанного **класс** атрибута.</span><span class="sxs-lookup"><span data-stu-id="e08b1-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="e08b1-132">Если **имя** атрибут — это краткое имя, например RSA, можно использовать это имя при вызове **CreateFromName** метод.</span><span class="sxs-lookup"><span data-stu-id="e08b1-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e08b1-133">Пример</span><span class="sxs-lookup"><span data-stu-id="e08b1-133">Example</span></span>  
 <span data-ttu-id="e08b1-134">В следующем примере показано, как использовать  **\<nameEntry >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e08b1-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e08b1-135">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="e08b1-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e08b1-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e08b1-136">See Also</span></span>  
 [<span data-ttu-id="e08b1-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e08b1-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="e08b1-138">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="e08b1-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="e08b1-139">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="e08b1-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="e08b1-140">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="e08b1-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
