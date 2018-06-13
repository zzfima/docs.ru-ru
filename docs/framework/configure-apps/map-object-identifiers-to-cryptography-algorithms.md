---
title: Отображение идентификаторов объектов на криптографические алгоритмы
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7801c55cf6b3334347788013d9052038d5d2f3ec
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756622"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="95893-102">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="95893-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="95893-103">Цифровые подписи убедитесь, что данные не подделаны при отправке из одной программы в другую.</span><span class="sxs-lookup"><span data-stu-id="95893-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="95893-104">Обычно цифровая подпись вычисляется путем применения математической функции к хэш данных должны быть подписаны.</span><span class="sxs-lookup"><span data-stu-id="95893-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="95893-105">При форматировании хэш-значение подписываемых, некоторые алгоритмы цифровой подписи добавляют в операцию форматирования идентификатор объекта (OID) ASN.1.</span><span class="sxs-lookup"><span data-stu-id="95893-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="95893-106">OID идентифицирует алгоритм, использованный для вычисления хэш-код.</span><span class="sxs-lookup"><span data-stu-id="95893-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="95893-107">Алгоритмы можно сопоставить с идентификаторами объектов расширения криптографического механизма для применения пользовательских алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="95893-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="95893-108">В следующем примере показано, как для сопоставления идентификатора объекта с новым хэш-алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="95893-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="95893-109">[ \<OidEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) содержит два атрибута.</span><span class="sxs-lookup"><span data-stu-id="95893-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="95893-110">**OID** атрибут является числовой идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="95893-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="95893-111">**Имя** атрибута является значение **имя** атрибута из [ \<nameEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="95893-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="95893-112">Перед идентификатором объекта могут сопоставляться с простым именем необходимо сопоставление имени алгоритма к классу.</span><span class="sxs-lookup"><span data-stu-id="95893-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95893-113">См. также</span><span class="sxs-lookup"><span data-stu-id="95893-113">See Also</span></span>  
 [<span data-ttu-id="95893-114">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="95893-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="95893-115">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="95893-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
