---
title: Элемент <cryptographySettings>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: fe6de09213c6f980e8eb205a318aae50033b2a84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155236"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="026c4-102">\<криптографияНастройки> Элемент</span><span class="sxs-lookup"><span data-stu-id="026c4-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="026c4-103">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="026c4-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="026c4-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="026c4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="026c4-105">&nbsp;&nbsp;[**\<мскориб>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="026c4-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="026c4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<криптографияНастройки>**</span><span class="sxs-lookup"><span data-stu-id="026c4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="026c4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="026c4-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="026c4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="026c4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="026c4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="026c4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="026c4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="026c4-110">Attributes</span></span>  
 <span data-ttu-id="026c4-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="026c4-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="026c4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="026c4-112">Child Elements</span></span>  
  
|<span data-ttu-id="026c4-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="026c4-113">Element</span></span>|<span data-ttu-id="026c4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="026c4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="026c4-115">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="026c4-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="026c4-116">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="026c4-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="026c4-117">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="026c4-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="026c4-118">Содержит отображение идентификатора объектов ASN.1 (OID) для классов.</span><span class="sxs-lookup"><span data-stu-id="026c4-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="026c4-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="026c4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="026c4-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="026c4-120">Element</span></span>|<span data-ttu-id="026c4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="026c4-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="026c4-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="026c4-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="026c4-123">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="026c4-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="026c4-124">Пример</span><span class="sxs-lookup"><span data-stu-id="026c4-124">Example</span></span>  
 <span data-ttu-id="026c4-125">В следующем примере показано, как использовать \*\* \<cryptographySettings>\*\* элемент для содержания карт имен криптографов и отображений OID.</span><span class="sxs-lookup"><span data-stu-id="026c4-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="026c4-126">Этот пример настраивает время <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> выполнения `MyHashClass` так, `MyCryptoClass` чтобы вернуть объект и карты класса в идентификатор объекта 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="026c4-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="026c4-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="026c4-127">See also</span></span>

- [<span data-ttu-id="026c4-128">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="026c4-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="026c4-129">Криптография Настройки Схема</span><span class="sxs-lookup"><span data-stu-id="026c4-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="026c4-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="026c4-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
