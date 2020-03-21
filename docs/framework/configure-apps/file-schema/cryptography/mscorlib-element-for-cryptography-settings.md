---
title: Элемент <mscorlib> для параметров шифрования
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: d1d805f7154c18dba2dcd4eb7228cc200d8da811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155185"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="6d28d-102">\<mscorlib> Элемент для настроек криптографии</span><span class="sxs-lookup"><span data-stu-id="6d28d-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="6d28d-103">Содержит [ \<криптографиюНастройки> элементом.](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d28d-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="6d28d-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="6d28d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6d28d-105">&nbsp;&nbsp;**\<мскориб>**</span><span class="sxs-lookup"><span data-stu-id="6d28d-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d28d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d28d-106">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d28d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6d28d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6d28d-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6d28d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d28d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6d28d-109">Attributes</span></span>  
 <span data-ttu-id="6d28d-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="6d28d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6d28d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6d28d-111">Child Elements</span></span>  
  
|<span data-ttu-id="6d28d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d28d-112">Element</span></span>|<span data-ttu-id="6d28d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6d28d-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="6d28d-114">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="6d28d-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d28d-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6d28d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6d28d-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d28d-116">Element</span></span>|<span data-ttu-id="6d28d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6d28d-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6d28d-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d28d-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6d28d-119">Пример</span><span class="sxs-lookup"><span data-stu-id="6d28d-119">Example</span></span>  
 <span data-ttu-id="6d28d-120">В следующем примере показано, как использовать \*\* \<>элемент мскорниба\*\* для ссылки на класс криптографии и для настройки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="6d28d-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="6d28d-121">Затем можно передать строку "RSA" <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> методу <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> и использовать `MyCryptoRSAClass` метод для возврата объекта.</span><span class="sxs-lookup"><span data-stu-id="6d28d-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d28d-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6d28d-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="6d28d-123">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="6d28d-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6d28d-124">Криптография Настройки Схема</span><span class="sxs-lookup"><span data-stu-id="6d28d-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6d28d-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6d28d-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="6d28d-126">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="6d28d-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
