---
title: '&lt;cryptoClass&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 726f13d778fc4cff9bdafed4518e9dee3eeab6b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501286"
---
# <a name="ltcryptoclassgt-element"></a><span data-ttu-id="d5f38-102">&lt;cryptoClass&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="d5f38-102">&lt;cryptoClass&gt; Element</span></span>
<span data-ttu-id="d5f38-103">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="d5f38-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="d5f38-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d5f38-104">\<configuration></span></span>  
<span data-ttu-id="d5f38-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="d5f38-105">\<mscorlib></span></span>  
<span data-ttu-id="d5f38-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="d5f38-106">\<cryptographySettings></span></span>  
<span data-ttu-id="d5f38-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="d5f38-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="d5f38-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="d5f38-108">\<cryptoClasses></span></span>  
<span data-ttu-id="d5f38-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="d5f38-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f38-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5f38-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5f38-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5f38-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5f38-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5f38-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5f38-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5f38-113">Attributes</span></span>  
  
|<span data-ttu-id="d5f38-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d5f38-114">Attribute</span></span>|<span data-ttu-id="d5f38-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d5f38-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="d5f38-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5f38-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="d5f38-117">Содержит сведения для класса шифрования.</span><span class="sxs-lookup"><span data-stu-id="d5f38-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="d5f38-118">Этот атрибут используется для предоставления краткого имени класса.</span><span class="sxs-lookup"><span data-stu-id="d5f38-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="d5f38-119">Необходимо указать строку, которая соответствует требованиям, перечисленным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="d5f38-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5f38-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5f38-120">Child Elements</span></span>  
 <span data-ttu-id="d5f38-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5f38-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5f38-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5f38-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d5f38-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5f38-123">Element</span></span>|<span data-ttu-id="d5f38-124">Описание</span><span class="sxs-lookup"><span data-stu-id="d5f38-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d5f38-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5f38-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="d5f38-126">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="d5f38-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="d5f38-127">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="d5f38-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="d5f38-128">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="d5f38-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="d5f38-129">Содержит элемент [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="d5f38-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d5f38-130">Пример</span><span class="sxs-lookup"><span data-stu-id="d5f38-130">Example</span></span>  
 <span data-ttu-id="d5f38-131">Приведенный ниже, показано, как использовать  **\<cryptoClass >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5f38-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="d5f38-132">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="d5f38-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d5f38-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d5f38-133">See also</span></span>
- [<span data-ttu-id="d5f38-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d5f38-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d5f38-135">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="d5f38-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="d5f38-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="d5f38-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="d5f38-137">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="d5f38-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
