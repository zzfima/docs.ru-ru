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
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Отображение идентификаторов объектов на криптографические алгоритмы
Цифровые подписи убедитесь, что данные не подделаны при отправке из одной программы в другую. Обычно цифровая подпись вычисляется путем применения математической функции к хэш данных должны быть подписаны. При форматировании хэш-значение подписываемых, некоторые алгоритмы цифровой подписи добавляют в операцию форматирования идентификатор объекта (OID) ASN.1. OID идентифицирует алгоритм, использованный для вычисления хэш-код. Алгоритмы можно сопоставить с идентификаторами объектов расширения криптографического механизма для применения пользовательских алгоритмов. В следующем примере показано, как для сопоставления идентификатора объекта с новым хэш-алгоритмом.  
  
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
  
 [ \<OidEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) содержит два атрибута. **OID** атрибут является числовой идентификатор объекта. **Имя** атрибута является значение **имя** атрибута из [ \<nameEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Перед идентификатором объекта могут сопоставляться с простым именем необходимо сопоставление имени алгоритма к классу.  
  
## <a name="see-also"></a>См. также  
 [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
