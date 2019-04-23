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
ms.openlocfilehash: e035ff04a70a441f7f64bbc230ba6d8036fb2ace
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130615"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Отображение идентификаторов объектов на криптографические алгоритмы
Цифровые подписи убедитесь, что данные не подделаны отправки из одной программы в другую. Обычно цифровая подпись вычисляется путем применения математической функции к хэш данных должны быть подписаны. При форматировании хэш-значение подписываемых, некоторые алгоритмы цифровой подписи добавляют операция форматирования идентификатор объекта (OID) ASN.1. OID идентифицирует алгоритм, который использовался для вычисления хэша. Алгоритмы можно сопоставить с идентификаторами объектов расширения криптографического механизма для использования пользовательских алгоритмов. Приведенный ниже показано, как сопоставления идентификатора объекта новый хэш-алгоритма.  
  
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
  
 [ \<OidEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) содержит два атрибута. **OID** атрибут — номер идентификатора объекта. **Имя** атрибута является значение **имя** из атрибута [ \<nameEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Прежде чем идентификатор объекта можно сопоставить с простым именем необходимо сопоставление имени алгоритма к классу.  
  
## <a name="see-also"></a>См. также

- [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
