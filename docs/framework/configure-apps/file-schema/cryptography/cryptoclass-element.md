---
title: Элемент <cryptoClass>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: 6a868f62c6a327012a6225b86bf0103d178d6ab7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921172"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="91c28-102">\<Элемент > cryptoClass</span><span class="sxs-lookup"><span data-stu-id="91c28-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="91c28-103">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="91c28-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="91c28-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="91c28-104">\<configuration></span></span>  
<span data-ttu-id="91c28-105">\<> mscorlib</span><span class="sxs-lookup"><span data-stu-id="91c28-105">\<mscorlib></span></span>  
<span data-ttu-id="91c28-106">\<Криптографисеттингс ></span><span class="sxs-lookup"><span data-stu-id="91c28-106">\<cryptographySettings></span></span>  
<span data-ttu-id="91c28-107">\<Криптонамемаппинг ></span><span class="sxs-lookup"><span data-stu-id="91c28-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="91c28-108">\<Криптоклассес ></span><span class="sxs-lookup"><span data-stu-id="91c28-108">\<cryptoClasses></span></span>  
<span data-ttu-id="91c28-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="91c28-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c28-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91c28-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91c28-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="91c28-111">Attributes and Elements</span></span>  
 <span data-ttu-id="91c28-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="91c28-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91c28-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="91c28-113">Attributes</span></span>  
  
|<span data-ttu-id="91c28-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="91c28-114">Attribute</span></span>|<span data-ttu-id="91c28-115">Описание</span><span class="sxs-lookup"><span data-stu-id="91c28-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="91c28-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91c28-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="91c28-117">Содержит сведения о классе шифрования.</span><span class="sxs-lookup"><span data-stu-id="91c28-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="91c28-118">Используйте этот атрибут, чтобы указать короткое имя для класса.</span><span class="sxs-lookup"><span data-stu-id="91c28-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="91c28-119">Необходимо указать строку, которая соответствует требованиям, указанным в [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="91c28-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91c28-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="91c28-120">Child Elements</span></span>  
 <span data-ttu-id="91c28-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="91c28-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91c28-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="91c28-122">Parent Elements</span></span>  
  
|<span data-ttu-id="91c28-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="91c28-123">Element</span></span>|<span data-ttu-id="91c28-124">Описание</span><span class="sxs-lookup"><span data-stu-id="91c28-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91c28-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91c28-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="91c28-126">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="91c28-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="91c28-127">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="91c28-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="91c28-128">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="91c28-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="91c28-129">Содержит элемент [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="91c28-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="91c28-130">Пример</span><span class="sxs-lookup"><span data-stu-id="91c28-130">Example</span></span>  
 <span data-ttu-id="91c28-131">В следующем примере показано, как использовать  **\<элемент cryptoClass >** для ссылки на криптографический класс и для настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="91c28-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="91c28-132">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> использовать метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="91c28-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91c28-133">См. также</span><span class="sxs-lookup"><span data-stu-id="91c28-133">See also</span></span>

- [<span data-ttu-id="91c28-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="91c28-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="91c28-135">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="91c28-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="91c28-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="91c28-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="91c28-137">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="91c28-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
