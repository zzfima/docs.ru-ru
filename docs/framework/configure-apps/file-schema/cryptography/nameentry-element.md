---
title: Элемент <nameEntry>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: b5f92ca2956f32382b12c9a1dec4e5d41ea4ee2a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285939"
---
# <a name="nameentry-element"></a><span data-ttu-id="21dee-102">\<nameEntry > элемент</span><span class="sxs-lookup"><span data-stu-id="21dee-102">\<nameEntry> Element</span></span>
<span data-ttu-id="21dee-103">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="21dee-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="21dee-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="21dee-104">\<configuration></span></span>  
<span data-ttu-id="21dee-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="21dee-105">\<mscorlib></span></span>  
<span data-ttu-id="21dee-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="21dee-106">\<cryptographySettings></span></span>  
<span data-ttu-id="21dee-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="21dee-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="21dee-108">\<nameEntry ></span><span class="sxs-lookup"><span data-stu-id="21dee-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21dee-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21dee-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21dee-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="21dee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="21dee-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="21dee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21dee-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="21dee-112">Attributes</span></span>  
  
|<span data-ttu-id="21dee-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="21dee-113">Attribute</span></span>|<span data-ttu-id="21dee-114">Описание</span><span class="sxs-lookup"><span data-stu-id="21dee-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21dee-115">**name**</span><span class="sxs-lookup"><span data-stu-id="21dee-115">**name**</span></span>|<span data-ttu-id="21dee-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="21dee-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="21dee-117">Указывает понятное имя алгоритма, который реализует криптографический класс.</span><span class="sxs-lookup"><span data-stu-id="21dee-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="21dee-118">**class**</span><span class="sxs-lookup"><span data-stu-id="21dee-118">**class**</span></span>|<span data-ttu-id="21dee-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="21dee-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="21dee-120">Указывает значение для **имя** атрибут в [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="21dee-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21dee-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="21dee-121">Child Elements</span></span>  
 <span data-ttu-id="21dee-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="21dee-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21dee-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="21dee-123">Parent Elements</span></span>  
  
|<span data-ttu-id="21dee-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="21dee-124">Element</span></span>|<span data-ttu-id="21dee-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="21dee-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="21dee-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21dee-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="21dee-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="21dee-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21dee-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="21dee-128">Remarks</span></span>  
 <span data-ttu-id="21dee-129">**Имя** атрибут может быть имя одного из абстрактных классов <xref:System.Security.Cryptography> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="21dee-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="21dee-130">При вызове **создать** метода класса абстрактный криптографии, передается имя абстрактного класса <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="21dee-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="21dee-131">**CreateFromName** возвращает экземпляр типа, указанного **класс** атрибута.</span><span class="sxs-lookup"><span data-stu-id="21dee-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="21dee-132">Если **имя** атрибут — это краткое имя, например RSA, можно использовать это имя при вызове **CreateFromName** метод.</span><span class="sxs-lookup"><span data-stu-id="21dee-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21dee-133">Пример</span><span class="sxs-lookup"><span data-stu-id="21dee-133">Example</span></span>  
 <span data-ttu-id="21dee-134">В следующем примере показано, как использовать  **\<nameEntry >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="21dee-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="21dee-135">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="21dee-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21dee-136">См. также</span><span class="sxs-lookup"><span data-stu-id="21dee-136">See also</span></span>
- [<span data-ttu-id="21dee-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="21dee-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="21dee-138">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="21dee-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="21dee-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="21dee-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="21dee-140">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="21dee-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
